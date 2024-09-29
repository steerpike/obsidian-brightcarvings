#observability 
The first thing we need to sort out I reckon is logging. How the hell are we supposed to manage the sheer amount of log data the company wants to capture?

Even if we turned as much of the existing logs as we can into metrics to try and bring down both the noise and the sheer quantity of logs we’re still going to be faced with requests from parts of the business that “no, we just need to capture all the logs, thanks.” Take CDN data for example, even if we figure out a way to minimise the amount we collect over fastly, yospace, akamai and cloudfront it’s still going to be an enormous amount of data. Then we’ll still have security coming to us and wanting to capture vast amounts of event and activity logs from every single running system and application we have.

We have to figure out:

- How to process enormous amounts of data
- What our data retention policy for that data is as a base and how teams might be able to change that based on need?
- How do teams interact with the collected data?
- How we can normalise the logs as much as possible to make correlation across captured data useful (ie, normalise what our CDN logs capture)

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdFOovyQWXwcti6HEDxasH45tvJwhXmZBuVt9HAfKndxnsprl6VhyfzJiQfBvpJumK-ki8lOcCcL0N8CVEXHjXB8gll6oSCfngs2gG8Qjox8wiMqD9hWqC5VbYmFvYkoC-C2bXo3QODZ0ZeFGYFHZUWAr49?key=DcN3ut3u8zBlQV2zEz-rVg)

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXean4D4DC554Km8yqsBtNgoRXFscktLK12MaISF1lGGmyAnWk-oWt4n7Kp3bxctxnBDhdVfzqq39iAOnnMGJ4vgojCk_rH0KBIdLoSuXptHLqsBaBXv4ebmUGJHLXtdqLCxiSuiS4zuJ1wNbsJToz1Hh6kK?key=DcN3ut3u8zBlQV2zEz-rVg)

## Issues:

- Observability dashboards all over the place
- Using, but also avoiding the provided platforms
- Engineer’s working on undifferentiated heavy lifting
- Alert spam
- Observability not helping in Incidents
- Over reliance on Logging
- Collect everything mentality
- Varying maturity levels    
- Scaling is costly

## What do we want?

- We want to reduce the number of platforms we are reliant on
- We want to reduce cost
- Reduce complexity for users
- We want to adhere to open standards and not subject ourselves to vendor lock-in
- We want to provide solutions for both low and high maturity teams working towards observability

  

## Principles of Observability

- You shouldn’t have to be an expert in a system in order to be able to debug it
-   

## Questions

1. What does good observability look like? What’s our north star?
2. What if we burnt the whole thing down and started from scratch?
	- What if we just went with New Relic? How do we decide?
	- Are there parts of our existing stack we could replace with SaaS/PaaS products? Which ones? How?

3. How do we currently manage and process our existing CDN logs for all our CDNs (fastly, cloudfront, akamai)
- How do we manage the sheer quantity of logs we receive? 
- How much data do we get per day?
- How much does it cost us to run, maintain and store?
- How long do we store data for?
- What is the right method for processing and storing the amount of data we have?

4. What are the baseline metrics and observability posture we expect on every service deployed to production? How do developers create the dashboards we expect of them?

- Initially scope this to online serving systems that are interested in a request/response lifecycle for a user (so ignore offline processing/batch jobs)
- Start with the four golden signals
- Latency (time taken to serve a request)
- Traffic (how much demand is placed on your system)
- Errors (rate of requests that are failing)
- Saturation (how “full” your service is)

5. How do application teams get started with adding tracing to their applications?

## Existing System

Architecture document here:

[https://drive.google.com/file/d/1qc5qO1enhMeajNVmSqHsnIZGGa3FZzgS/view?ts=66a994e8](https://drive.google.com/file/d/1qc5qO1enhMeajNVmSqHsnIZGGa3FZzgS/view?ts=66a994e8)

## Resources

- [https://aparker.io/2024/01/otel-til-what-the-heck-is-instrumentation-anyway/](https://aparker.io/2024/01/otel-til-what-the-heck-is-instrumentation-anyway/)
    
- [https://www.youtube.com/watch?v=h9JNVGvUExI](https://www.youtube.com/watch?v=h9JNVGvUExI) - Things I wish I knew before we decided to migrate our metrics infrastructure
    
- [https://github.com/grafana/intro-to-mltp](https://github.com/grafana/intro-to-mltp) - Introduction to Metrics, Logs, Traces and Profiles in Grafana
    
- [https://youtu.be/5rjTdA6BM1E?feature=shared](https://youtu.be/5rjTdA6BM1E?feature=shared) - What is OpenTelemetry
    
- [https://youtu.be/0MPDPFt-t4I?feature=shared](https://youtu.be/0MPDPFt-t4I?feature=shared) - OpenTelemetry looks good to me
    
- [https://medium.com/mercadolibre-tech/building-a-large-scale-observability-ecosystem-1edf654b249e](https://medium.com/mercadolibre-tech/building-a-large-scale-observability-ecosystem-1edf654b249e) - Building a large scale Observability Ecosystem
## Epics

- Understand the cost of existing observability stacks used throughout Nine
    

- New Relic contract costs (Commercial, Streaming, Publishing)
    
- Opensearch clusters used by various teams
    
- Running and maintaining the Publishing stack
    
- AWS cloudwatch logs across all accounts
    
- Other resources used for observability (athena, others?)
    
- Data retention across accounts
    

- Understand the maturity and existing landscape of current observability across Nine
    

- Streaming
    
- Commercial
    
- Publishing
    
- Security
    
- Infrastructure & Networks
    

- Create a dashboard detailing the current resource and monetary costs of the existing publishing platform