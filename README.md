# app-maven-fails-at-source-scan

## Creating the Workload

```
tanzu apps workload create app-maven-fails-at-source-scan \
  --namespace dev \
  --git-branch main \
  --git-repo https://github.com/carto-run/app-maven-fails-at-source-scan \
  --label apps.tanzu.vmware.com/has-tests=true \
  --label app.kubernetes.io/part-of=app-maven-fails-at-source-scan \
  --type web \
  --yes
```

## Logs

```
tanzu apps workload tail app-maven-fails-at-source-scan
```

## Configuration

| Item            | Config                                                                                |
| --------------- | ------------------------------------------------------------------------------------- |
| Scan Policy     | [default](resources/scan-policy.yaml)                                                 |
| Pipeline        | [developer-defined-tekton-pipeline](resources/developer-defined-tekton-pipeline.yaml) |
| tap-values.yaml | na                                                                                    |
| Supply Chain    | source-test-scan-to-url                                                               |

