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


## Creating SLIs and SLOs
SLI:
- In the previous 24 hours, we received fewer than 10 incorrect responses.
- The average response time was around 2000 milliseconds per minute.
- In 99% of our responses, the data was formatted correctly.
- We received 75% more correct responses than incorrect responses.

SLO:
- 99.9% uptime per month.
- 99.9% of responses to our front-service will return 2xx, 3xx or 4xx HTTP code within 2000 ms.
- 99.99% of transaction requests will succeed over any calendar month.
- 99.9% of backend service requests will succeed on their first attempt.

## Building KPIs for our plan

1. In the previous 24 hours, we received fewer than 10 incorrect responses.
    Successful requests per minute: this KPI demonstrates how well our system performs.
    Error requests per minute: this KPI corresponds to this SLI.

2. We received 75% more correct responses than incorrect responses.
    Successful requests per minute: this KPI indicates the number of successful request.

## Final Dashboard

![GeneralDashboard](./answer-img/application%20dashboard.jpg)