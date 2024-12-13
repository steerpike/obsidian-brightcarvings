#observability 

Focus is on incident management, not observability as a bigger picture towards improvement
We're firehosing a large amount of telemetry that isn't particularly clean or useful
It's currently only used by Core Services teams within Streaming which means that Streaming doesn't actually have a consistent, clear observability partner available to all teams.


Steps:
1. Deploy OpenTelemetry to Production so that we are getting telemetry directly for applications that can be sent elsewhere
2. Stand-up a Grafana LGTM stack in an appropriate cluster
3. Point existing Streaming apps at the new stack
4. Create new dashboards for managing applications
5. Define and configure alerts under new stack
6. Training for application team on new dashboards and Grafana functionality
7. Training for application team on manual instrumentation to improve the new platform
