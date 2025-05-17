# Signoz Docker Monitoring — Hypothesis 1

## Problem

Signoz is expected to monitor Docker containers, collecting logs and metrics. However, in the [rhildred/signoz](https://github.com/rhildred/signoz) setup, this does not seem to work as expected.

---

## Hypothesis 1

> Docker monitoring does not work because the OpenTelemetry Collector configuration is missing required receivers such as:
>
> - `tcplog/docker` for logs
> - `docker_stats` for container metrics

---

##  What We Changed

- We commented out or removed the `tcplog/docker` and `docker_stats` receivers in the `otel-collector-config.yaml` file.
- This simulates a misconfigured setup to confirm whether Docker logs and metrics are missing due to the absence of these receivers.

---

## How to Run This Test

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/signoz.git
cd signoz
