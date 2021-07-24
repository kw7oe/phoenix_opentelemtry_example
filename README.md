# Phoenix OpenTelemetry Example

This is a sample repository that demo how to setup OpenTelemetry for Phoenix application
with `opentelemetry_phoenix` and `opentelemetry_ecto`.

Here, we are using `opentelemetry_exporter` to export the traces to [
OpenTelemetry Collector][0]. The collector in turn export the traces to [Zipkin][1] and [
Jaeger][2] respectively.

## Getting Stated

Assuming you already have Docker and Docker Compose installed:

1. Run `docker-compose up` to start the application, OpenTelemetry Collector,
   Zipkin and Jaeger.
2. Run migration on another terminal with:
  ```
  docker exec -it demo_phoenix_1 /bin/ash ./bin/demo eval 'Demo.Release.migrate()'
  ```
3. Browse to http://localhost:4000 and play around with
   http://localhost:4000/posts.
4. Visit Zipkin at http://localhost:9411 and hit `Run Query` to look the the sample trace.
5. Visit Jaeger UI at http://localhost:16686, select `demo` under Service  and click `Find Trace` to
look at the sample trace.

## Example Screenshot

### Zipkin

![Zipkin Index](./images/zipkin_index.png)
![Zipkin Traces](./images/zipkin_traces.png)

### Jaeger

![Jaeger Index](./images/jaeger_index.png)
![Jaeger Traces](./images/zipkin_traces.png)


[0]: https://github.com/open-telemetry/opentelemetry-collector/
[1]: https://zipkin.io/
[2]: https://www.jaegertracing.io/

