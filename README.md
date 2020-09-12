Open-census instrumentation with golang web service to gather distributed traces

Service A ------(sends request to)------> Service B

Simultaneously capture and export traces to oc-collector.
Oc-collector sends the traces to jaeger tracing backend (jaeger-all-in-one)
traces are visualised using Jaeger dashboard running on localhost:16686  

Docker compose to spin up
1. jaeger-all-in-one container `Exposes port 16686 to view dashboard. port 14268 to receive trace data`
2. oc-collector `Exposes 55678 port to receive trace data from golang microservices`
3. golang service A `POST /hello-service-A endpoint {"sender":"XYZ"}`
4. golang service B `POST /hello-service-B endpoint {"sender":"XYZ" , "message": "hi !"}`

Steps
1. cd to project root directory 
2. Run the following command
   `docker-compose up`
3. Open browser and hit `localhost:16686` to see the traces 
