# servo-prom
Optune servo driver for Prometheus

## Deployment caveats
1. This driver requires `measure.py` base class from the Optune servo core.  It
   can be copied or symlinked here as part of packaging.
2. The default Prometheus endpoint is `http://prometheus:9090/metrics`; you must
   set the environment variable `PROMETHEUS_ENDPOINT` in the servo's container
   if you want to use a different endpoint.

**Notes**
* You can define multiple metrics.
* The measurement precision is 1 minute.
* You may get for. ex. for requested duration of 10 minutes 11 data points due to Prometheus returning datapoints for a requested time range inclusively.
