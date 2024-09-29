## Overview
We want to investigate auto-instrumentation with Streaming applications combined with the grafana stack to determine exactly what we would get out-of-the-box in terms of quick and dirty observability.
We want to evaluate:

1. Spin up an observability cluster for Streaming applications to point to
2. Ease of implementation - how quick and easy is it to convert existing apps from using New Relic to grafana
3. Application and infrastructure observability - New Relic offers an APM for applications and an APM for infrastructure each of which provides detailed information. 
4. Dashboard replication - how much of the existing functionality Streaming teams use in New Relic can we replicate easily for them in grafana dashboards
5. APM monitoring - Streaming makes extensive use of a New Relic feature for configuring alerts on services based around a New Relic APM value which is an automatically generated value based on a number of automated metrics (error rate, throughput, etc)
6. We would like to try and see what options are available from a frontend auto-instrumentation perspective, but that should likely be a stretch goal.
7. We need to validate auto-instrumentation in both kube and beanstalks

