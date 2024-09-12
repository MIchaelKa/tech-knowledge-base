
Monitoring
Observability
Мониторинг

# External Links

Moved
https://www.notion.so/Monitoring-213b398d5ad34c9894ba95832a1a41a0

https://chatgpt.com/c/66e0dfb6-b878-8000-aa78-e9b318683d0a

# Links

[[ML System Design]]

[[Chip. DMLS.]]
[[Курс по ML System Design]]

# Overview

Observability
- Наблюдаемость
- Observability is a measure of how well internal states of a system can be inferred from knowledge of its external outputs. wiki
- Control theory

Metrics
- Monitoring metrics
- Monitoring is all about metrics.
- Implicit or explicit feedback from users

Operational metrics
- не связано с ML напрямую
- inference time
- uptime
	- AWS, SLA

Мониторинг сдвига в данных
- [[Data Distribution Shifts (DDS)]]

Вторая модель которая прогнозирует ошибочность.

# ML Metrics

4 stages
- accuracy-related metrics
- predictions
- features
- raw inputs

the lower the harder to monitor

Monitoring accuracy-related metrics
- Close relation to collecting Natural labels
- Examples
	- Mobile phone scanning / successful transaction,  ratio

Monitoring predictions
- You can monitor predictions for distribution shifts.

Monitoring features
- compared to raw input data, features are well structured following a predefined schema
- predefined schema for features
- unit tests for data

GX
great expectations
[https://github.com/great-expectations/great_expectations](https://github.com/great-expectations/great_expectations)

Concerns abount feature monitoring
- Есть минусы
- Read the book

# Toolbox

Instrumentation
- Вспомни Instruments в XCode

Logs
- Как собирать и где хранить все логи?
- Единая база данных для всех логов
- Kafka

Alerts
- Notification channels: e-mail, slack topic, etc.
- Alert fatigue

Grafana
Kibana