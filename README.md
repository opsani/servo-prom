# servo-prom
Optune servo driver for Prometheus

## Deployment caveats
1. This driver requires `measure.py` base class from the Optune servo core.  It
   can be copied or symlinked here as part of packaging.
2. The default Prometheus endpoint is `http://prometheus:9090/metrics`; you must
   set the environment variable `PROMETHEUS_ENDPOINT` in the servo's container
   if you want to use a different endpoint.
