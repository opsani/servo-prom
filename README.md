# servo-prom
Optune servo driver for Prometheus

## Deployment caveats
1. This driver requires `measure.py` base class from the Optune servo core.  It
   can be copied or symlinked here as part of packaging.
2. The default Prometheus endpoint is `http://prometheus:9090/metrics`; you must
   set the environment variable `PROMETHEUS_ENDPOINT` in the servo's container
   if you want to use a different endpoint.
3. Alternatively, Prometheus endpoint may be specified in `prometheus_endpoint` key
   of driver configuration. If this key exists and is not empty, value specified will
   override `PROMETHEUS_ENDPOINT`.
4. If environment variable `PROMETHEUS_USE_DRIVER_NAME` is set to True, then 
   the driver will use configuration matching driver filename in config.yaml instead
   of a standard `prom`. This allows querying multiple Prometheus server via `servo-magg`
   driver.

**Notes**
* You can define multiple metrics.
* The measurement precision is 1 minute.
* You may get for. ex. for requested duration of 10 minutes 11 data points due to Prometheus returning datapoints for a requested time range inclusively.
