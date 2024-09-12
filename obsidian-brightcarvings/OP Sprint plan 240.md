## Overview
We want to investigate auto-instrumentation with Streaming applications combined with the grafana stack to determine exactly what we would get out-of-the-box in terms of quick and dirty observability.
We want to evaluate:
1. Ease of implementation - how quick and easy is it to convert existing apps from using New Relic to grafana
2. Application and infrastructure observability - New Relic offers an APM for applications and an APM for infrastructure each of which provides detailed information. 
3. Dashboard replication - how much of the existing functionality Streaming teams use in New Relic can we replicate easily for them in grafana dashboards
4. APM monitoring - Streaming makes extensive use of a New Relic feature for configuring alerts on services based around a New Relic APM value which is an automatically generated value based on a number of automated metrics (error rate, throughput, etc)
5. We would like to try and see 
