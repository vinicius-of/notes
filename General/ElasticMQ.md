## What is Amazon SQS?

- It's a message queue as a service, MQ-as-service. It offers some basic message queue operations like through its interface.
- You can send the message to the queue and other components can later receive the message.
- You can delete the message.
- Amazon SQS offers at least once delivery to receive for sure.

## How to test SQS apps?

- You could use the real SQS implementation, but it could bring some drawbacks such as:
	- You would need an internet connection, which it's not always available and any test could fail just because of instability.
	- If you have several developers testing the application concurrently, it could cause different results due to share the same resource/real queue (Amazon SQS).

- A solution is to use a local SQS server like ElasticMQ.

## ElasticMQ

- Relevant subset of SQS.
- In-memory
	- It is a memory-implemented queue.
- Lightweight