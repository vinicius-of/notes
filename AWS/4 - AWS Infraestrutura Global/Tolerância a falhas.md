## Tolerância a falhas

### O que é um domínio falho? (fault domain)

- É uma seção na rede que é vulnerável a danos se o dispositivo ou sistema crítico falhar.
- O propósito de um domínio é que se uma falha ocorrer, <mark style="background: #FF5582A6; color: white;">não irá se propagar para fora do domínio</mark>, limitando o dano possível.
- Você pode ter domínios falhos aninhados dentro de outros domínios.

### O que é um nível falho? (fault level)

- É uma coleção de domínios falhos.
- O escopo de um domínio falho pode ser :
	- Servidores específicos de um *rack*.
	- Uma *rack* inteiro dentro de um datacenter.
	- Uma sala inteira em um datacenter.
	- Todo o datacenter.

![[Pasted image 20251001002643.png]]
