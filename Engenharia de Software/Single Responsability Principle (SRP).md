---
tags:
  - design-pattern
aliases:
  - SRP
---
Fonte: https://github.com/nahidulhasan/solid-principles/blob/master/README.md

> Um módulo deve ser responsável por apenas um ator.

- Isso quer dizer que métodos e propriedades devem trabalhar para alcançar o mesmo objetivo.
- Quando uma classe serve para múltiplos propósitos or responsabilidades, então deve-se fazer um novo módulo ou class

```php
namespace Demo;
use DB;
class OrdersReport
{
    public function getOrdersInfo($startDate, $endDate)  {
        $orders = $this->queryDBForOrders($startDate, $endDate);
        return $this->format($orders);
    }
    protected function queryDBForOrders($startDate, $endDate) {
        return DB::table('orders')->whereBetween('created_at', [$startDate, $endDate])->get();
    }
    protected function format($orders) { 
        return '<h1>Orders: ' . $orders . '</h1>';
    }
}
```

- Acima existe a classe/módulo que viola o princípio explicado.  Podemos ver que no contexto da classe é dada a responsabilidade da camada de persistência de dados (buscar/receber dados), sendo a função `queryDBForOrders`, e a responsabilidade de como o dado deve ser visualizado, sendo a função `format`. Se houver qualquer mudança exigida que envolva este módulo, ele necessitará de refatoração.

- Para resolver este problema, precisamos separar em classes/módulos diferentes para cada um lidar com sua responsabilidade. 

```php
namespace Report;
use Report\Repositories\OrdersRepository;
class OrdersReport
{
    protected $repo;
    protected $formatter;
    public function __construct(OrdersRepository $repo, OrdersOutPutInterface $formatter) {
        $this->repo = $repo;
        $this->formatter = $formatter;
    }
    public function getOrdersInfo($startDate, $endDate) {
        $orders = $this->repo->getOrdersWithDate($startDate, $endDate);
        return $this->formatter->output($orders);
    }
}

namespace Report;
interface OrdersOutPutInterface {
	public function output($orders);
}
namespace Report;
class HtmlOutput implements OrdersOutPutInterface {
    public function output($orders) {
        return '<h1>Orders: ' . $orders . '</h1>';
    }
}

namespace Report\Repositories;
use DB;
class OrdersRepository {
    public function getOrdersWithDate($startDate, $endDate) {
        return DB::table('orders')->whereBetween('created_at', [$startDate, $endDate])->get();
    }
}
```

