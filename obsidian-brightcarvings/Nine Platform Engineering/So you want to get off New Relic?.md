#observability 

- Focus is on incident management, not observability as a bigger picture towards improvement
- We're firehosing a large amount of telemetry that isn't particularly clean or useful
- Inspecting the firehose comes with pretty limited tooling within New Relic
- It's currently only used by Core Services teams within Streaming which means that Streaming doesn't actually have a consistent, clear observability partner available to all teams.
- No clear path for adoption for other teams
	- Video avoids New Relic for the most part because of the data consumption costs and a flow of effect of that is that the don't really use it for their myriad lambdas or internal tooling apps
	- Client apps don't really have a clear adoption path for any observability capabilities (frankly this is true for publishing too so ideally work here can benefit both business units)
	- Mobile apps also have no clear observability adoption path (although Publishing mobile apps are looking to run an Otel spike)


Steps:
1. Deploy OpenTelemetry to Production so that we are getting telemetry directly for applications that can be sent elsewhere
2. Stand-up a Grafana LGTM stack in an appropriate cluster
3. Point existing Streaming apps at the new stack
4. Create new dashboards for managing applications
5. Define and configure alerts under new stack
6. Training for application team on new dashboards and Grafana functionality
7. Training for application team on manual instrumentation to improve the new platform

