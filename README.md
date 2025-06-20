# mi-rabbitmq-failover

An example of resilient messaging with WSO2 Micro Integrator and RabbitMQ.

It demonstrates how to handle backend failures using message stores, scheduled failover processing, and dead-letter queues.

📝 [Medium article with full explanation](https://medium.com/@bernardolrodrigues/resilient-messaging-with-rabbitmq-failover-in-wso2-micro-integrator-b7ba7610c59e)

## 📁 Files and Folders

- `docker-compose.yml` — Spins up RabbitMQ and NGINX for local testing
- `nginx.conf` — NGINX configuration acting as a reverse proxy for simulating backend failure
- `rabbitmq-defs.json` — Preconfigured queue and user setup for RabbitMQ
- `rabbitmqfailover_1.0.0/` — Built Synapse artifact of the proxy service

## ✅ How to Use

1. Start RabbitMQ and NGINX with `docker-compose up`.
2. Deploy the contents of `rabbitmqfailover_1.0.0/` to your WSO2 Micro Integrator (e.g., drop into the `deployment` directory).
3. Send test messages to RabbitMQ.
4. Stop the backend (NGINX target) to simulate a failure.
5. Observe how messages are stored and retried using the configured processor and dead-letter handling.

This setup helps ensure message durability even during backend or broker interruptions.
