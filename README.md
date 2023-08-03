**Note:** For the screenshots, you can store all of your answer images in the `answer-img` directory.

## Verify the monitoring installation

*TODO:* run `kubectl` command to show the running pods and services for all components. Take a screenshot of the output and include it here to verify the installation
<img src="https://raw.githubusercontent.com/rajaitusa/Project_Starter_Files-Building_a_Metrics_Dashboard/main/answer-img/pods_all_rj.png">

<img src="https://raw.githubusercontent.com/rajaitusa/Project_Starter_Files-Building_a_Metrics_Dashboard/main/answer-img/services_all_rj.png">

<img src="https://raw.githubusercontent.com/rajaitusa/Project_Starter_Files-Building_a_Metrics_Dashboard/main/answer-img/monitoring_observability_rj.png">

## Setup the Jaeger and Prometheus source
*TODO:* Expose Grafana to the internet and then setup Prometheus as a data source. Provide a screenshot of the home page after logging into Grafana.

<img src="https://raw.githubusercontent.com/rajaitusa/Project_Starter_Files-Building_a_Metrics_Dashboard/main/answer-img/dash1_rj.png">


## Create a Basic Dashboard
*TODO:* Create a dashboard in Grafana that shows Prometheus as a source. Take a screenshot and include it here.

<img src="https://raw.githubusercontent.com/rajaitusa/Project_Starter_Files-Building_a_Metrics_Dashboard/main/answer-img/dash1_2_rj.png">

## Describe SLO/SLI
*TODO:* Describe, in your own words, what the SLIs are, based on an SLO of *monthly uptime* and *request response time*.

1. SLI's, or Service-Level Indicators, represent specific metrics utilized to evaluate the performance of an application or service.
2. On the other hand, SLOs, or Service Level Objectives, typically define the organization's desired measurements, such as aiming for 99.9% application uptime and an average web request response time of less than 1 second.

## Creating SLI metrics.
*TODO:* It is important to know why we want to measure certain metrics for our customer. Describe in detail 5 metrics to measure these SLIs. 

1. **Response Time (Latency)**: Response time is a crucial SLI metric as it directly impacts user experience. A shorter response time ensures that users receive prompt feedback, enhancing satisfaction and engagement with the service. Lower latency leads to quicker interactions and improved user perception of system performance.

2. **Error Rate**: Measuring the proportion of erroneous or failed requests is vital for assessing the reliability of a service. A high error rate indicates potential issues in the application or infrastructure, helping teams identify and resolve problems before they impact user experience. Maintaining a low error rate ensures a stable and dependable service.

3. **Availability**: The percentage of time a service is operational and accessible is a fundamental SLI metric that reflects its reliability. Monitoring availability helps track the service's uptime, ensuring that it remains accessible to users. A high availability rate ensures that users can access the service consistently, building trust and meeting user expectations.

4. **Service Response Time**: Similar to response time, service response time focuses on the time it takes for a system to process a request and provide a complete response. This metric is crucial for assessing the efficiency of the service's backend processes. Optimizing service response time contributes to faster user interactions and a smoother overall experience.

5. **Throughput**: Throughput, measured as the number of operations or requests processed within a given time period, is essential for understanding the system's capacity and scalability. Monitoring throughput helps ensure that the service can handle increasing user demands without performance degradation. Maintaining a high throughput supports seamless user interactions during peak usage times.


## Create a Dashboard to measure our SLIs
*TODO:* Create a dashboard to measure the uptime of the frontend and backend services We will also want to measure to measure 40x and 50x errors. Create a dashboard that show these values over a 24 hour period and take a screenshot.

<img src="https://raw.githubusercontent.com/rajaitusa/Project_Starter_Files-Building_a_Metrics_Dashboard/main/answer-img/dash1_3_rj.png">

## Tracing our Flask App
*TODO:*  We will create a Jaeger span to measure the processes on the backend. Once you fill in the span, provide a screenshot of it here. Also provide a (screenshot) sample Python file containing a trace and span code used to perform Jaeger traces on the backend service.

<img src="https://raw.githubusercontent.com/rajaitusa/Project_Starter_Files-Building_a_Metrics_Dashboard/main/answer-img/python_trace1_rj.png">

<img src="https://raw.githubusercontent.com/rajaitusa/Project_Starter_Files-Building_a_Metrics_Dashboard/main/answer-img/tracing-jaeger_rj.png">

## Jaeger in Dashboards
*TODO:* Now that the trace is running, let's add the metric to our current Grafana dashboard. Once this is completed, provide a screenshot of it here.

<img src="https://raw.githubusercontent.com/rajaitusa/Project_Starter_Files-Building_a_Metrics_Dashboard/main/answer-img/jaeger_dash_rj.png">

## Report Error
*TODO:* Using the template below, write a trouble ticket for the developers, to explain the errors that you are seeing (400, 500, latency) and to let them know the file that is causing the issue also include a screenshot of the tracer span to demonstrate how we can user a tracer to locate errors easily.

TROUBLE TICKET

Name: 500 Internal server error

Date: 02/08/2023

Subject: Getting 500 error while adding using "/star" service route

Affected Area: Backend service of adding to database is affected.

Severity: Critical

Description: While executing "/star" endpoint of the backend service, getting 500 internal server error.

<img src="https://raw.githubusercontent.com/rajaitusa/Project_Starter_Files-Building_a_Metrics_Dashboard/main/answer-img/500errors_rj.png">


## Creating SLIs and SLOs
*TODO:* We want to create an SLO guaranteeing that our application has a 99.95% uptime per month. Name four SLIs that you would use to measure the success of this SLO.

SLOs:
1. Response error: HTTP status codes in the 4xx and 5xx range. 
2. Service availability: accessibility of both backend and frontend components. 
3. Service response: volume of requests and the time taken to receive responses.
4. Evaluate Uptime: maintain the application's uptime, availability and resource utilization, aligning with the goal of achieving 99.95% uptime per month.

## Building KPIs for our plan
*TODO*: Now that we have our SLIs and SLOs, create a list of 2-3 KPIs to accurately measure these metrics as well as a description of why those KPIs were chosen. We will make a dashboard for this, but first write them down here.


1. Evaluate the frequency of non-HTTP 200 responses per second to gauge service health.
    a. Measure 4xx error.
    b. Measure 5xx error.

2. To maintain service availability, it is essential to manage server CPU and memory usage at optimal levels.

    a. Monitor and manage server CPU utilization.
    b. Monitor and manage server memory consumption.

3. Track service request and response metrics to monitor incoming pings.

    a. Calculate total requests per minute.
    b. Calculate average response times.

    

## Final Dashboard
*TODO*: Create a Dashboard containing graphs that capture all the metrics of your KPIs and adequately representing your SLIs and SLOs. Include a screenshot of the dashboard here, and write a text description of what graphs are represented in the dashboard.  

<img src="https://raw.githubusercontent.com/rajaitusa/Project_Starter_Files-Building_a_Metrics_Dashboard/main/answer-img/final_dash_rj.png">

1. Monitor CPU and Memory usage to avoid any overload and memory leak
2. Measure HTTP errors - monitor the HTTP errors (5xx and 4xx) and fix accordingly
3. Monitor service availability - checking requests and response time to improve the accessibility for the services