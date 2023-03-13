## Verify the monitoring installation

**Default namespace**:  
![Cluster resources](./answer-img/kubectl%20default%20namespace.jpg)

**Monitoring namespace**  
![Cluster resources](./answer-img/kubectl%20monitoring%20namespace.jpg)

**Observability namespace**  
![Cluster resources](./answer-img/kuibectl%20observability%20namespace.jpg)

## Setup the Jaeger and Prometheus source

![Jaeger-Prometheus](./answer-img/grafana%20datasources.jpg)

## Create a Basic Dashboard

![Basic Bashboard](./answer-img/prometheus%20dashboard.jpg)

## Describe SLO/SLI
Assuming the following SLO for monthly uptime and request response time

    99.99% uptime in the year.
    95% of requests completed in < 100 ms.

We can describe SLIs as:

    We got 99.98% uptime in the current year.
    94% of the requests were completed in < 100 ms.

## Creating SLI metrics.
1. Number of error responses in a period of time - This measure might assist us in identifying potential bottlenecks and issues.
2. The average time taken to return a response - This metric might enable us to find areas where we can improve the performance of our services.
3. The average time taken recover a service if it goes down - This metric may be used to assess our ability to recover from potential failovers.
4. Total uptime in a period of time - This metric could help us to measure the health & availability of our services
5. Average percentage of memory or CPU used by a service in a period of time - This metric could aid us in assessing the effect of our services on system maintenance expenses and aid in our search for effective services.

## Create a Dashboard to measure our SLIs

![Application dashboard](./answer-img/application%20dashboard.jpg)

## Tracing our Flask App

Please refere to the screenshots in answer-img folder.
File name: "jaeger tracing the application.jpg"
![Jaeger](./answer-img/jaeger%20tracing%20the%20application.jpg)

Also, please refer to : "flask with span.jpg"
![FlaskWithSpan](./answer-img/flask%20with%20span.jpg)

## Jaeger in Dashboards

![JaegerGrafana](./answer-img/traces%20in%20grafana.jpg)

## Report Error

TROUBLE TICKET

Name: Hamed Salameh

Date: March 8th, 2023

Subject: !Urgent! - Multiple errors of 40x and 50x coming from our services (frontend/backend)

Affected Area: User interface, API endpoints, application stability

Severity: High

Description: Many calls are failing to process with sucess and failing with either 40x and 50x errors. please look into asap.

Attached is Jaeger's sample for error trace:
![JaegerError](./answer-img/jaeger%20tracing%20the%20application%20-%20fix.jpg)


## Creating SLIs and SLOs

SLI:
- Monthly Uptime Percentage  
  The percentage of time that the service was available and ready to serve requests during a particular month.

- Request Success Rate  
  The percentage of service requests that are successfully executed without error.

- Service Latency  
  The time it takes for a request to be performed after it is received by the API.

- Service Error Rate
  The percentage of service requests that result in an error, i.e, returs http error 40x or 50x.


## Building KPIs for our plan

KPI's:
- Request Success Rate: KPI is a threshold of 99.9%
  It was selected because it has a very high success rate and a low percentage of failures, indicating that the service is working well and offering an excellent customer experience.

- Latency: KPI is a threshold of 500 ms
  reflects a pretty low latency that would be regarded acceptable for many sorts of online applications. This also suggests that the service is highly responsive and performant.


## Final Dashboard

![GeneralDashboard](./answer-img/mainboard-final.jpg)

The final dashboard offers the following panels and information:
|Panel|Purpose|  
|-|-|
|Total Requests per minute|The total number of request per minutes per response type|
|Error Per second|The error rate we are getting poer second|
|Requests Per seond|The rate of the incoming requests coming in per second|
|Average response time|The average time ir takes the backend service to respond|
|Request duration p-90|The 90th percentile of request durations over the last 30 seconds|
|Request duration p-50|The 50th percentile of request durations over the last 30 seconds|
|Traces|Application traces as caputred by Jaeger|
