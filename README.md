---

## 🔬 Hypothesis 2 — Fix Docker Monitoring by Adding Receivers

### What We Did

- Enabled `tcplog/docker` and `docker_stats` receivers in `otel-collector-config.yaml`
- Updated the pipelines for `logs` and `metrics`

### How to Test

1. `git checkout test/fix-dockerstats-working`
2. Run: `docker-compose up --build`
3. Go to [http://localhost:3301](http://localhost:3301)
4. Verify:
   - Container logs appear in **Logs tab**
   - CPU, memory usage appear in **Metrics tab**

### Conclusion

This confirms that enabling the correct receivers in OpenTelemetry Collector fixes Docker monitoring in Signoz.
