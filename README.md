# Collectord configurations

The flat manifests for Collectord on Kubernetes and OpenShift, one commit per release: the same
files [outcoldsolutions.com](https://www.outcoldsolutions.com) serves for that release. Each release
is the commit `Version <version>`, tagged with the version (`26.10.1`). Since 26.10.1 the
release itself commits them, and they are rendered from the Helm charts in
[collectord-helm-charts](https://github.com/outcoldsolutions/collectord-helm-charts).

| File | Deploys |
| --- | --- |
| `collectorforkubernetes/collectorforkubernetes.yaml` | Monitoring Kubernetes, to Splunk |
| `collectorforkubernetes/collectorforkubernetes-elasticsearch.yaml` | Kubernetes logs and metrics to Elasticsearch |
| `collectorforkubernetes/collectorforkubernetes-opensearch.yaml` | Kubernetes logs and metrics to OpenSearch |
| `collectorforkubernetes/collectorforkubernetes-syslog.yaml` | Kubernetes logs to syslog |
| `collectorforopenshift/collectorforopenshift.yaml` | Monitoring OpenShift, to Splunk |
| `collectorforopenshift/collectorforopenshift-rhel.yaml` | The same, with the Red Hat certified image |
| `collectorforopenshift/collectorforopenshift-syslog.yaml` | OpenShift logs to syslog |
| `collectorforopenshift/collectorforopenshift-rhel-syslog.yaml` | The same, with the Red Hat certified image |

The Elasticsearch, OpenSearch and syslog manifests start at 26.10.1. Tags up to 5.24 hold one
directory per cluster version instead (`collectorforopenshift/4.2/`, ...).

## Comparing versions

Compare two tags to see what an upgrade changes in the configuration, on GitHub
(`https://github.com/outcoldsolutions/collectord-configurations/compare/26.04.5...26.10.1`) or
in a clone:

```bash
git diff 26.04.5 26.10.1 -- collectorforkubernetes/collectorforkubernetes.yaml
```

Installing and upgrading are documented for
[Kubernetes](https://www.outcoldsolutions.com/docs/monitoring-kubernetes/) and
[OpenShift](https://www.outcoldsolutions.com/docs/monitoring-openshift/).
