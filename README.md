Service A ------(sends request to)------> Service B

Simultaneously capture and export traces to oc-collector.
Oc-collector sends the traces to jaeger tracing backend (jaeger-all-in-one)
traces are visualised using Jaeger dashboard running on localhost:16686  

Docker compose to spin up
1. jaeger-all-in-one container [Exposes port 16686 to view dashboard. port 14268 to receive trace data]
