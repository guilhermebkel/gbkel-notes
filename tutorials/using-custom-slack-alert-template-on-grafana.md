# Using Custom Slack Alert Template on Grafana

### Title

```
[{{ .Status | toUpper }}] {{ .CommonLabels.alertname }}
```

### Text Body

```
{{ if .Alerts.Firing }}
  {{ range .Alerts}}
    {{ .Annotations.summary }}
  {{ end }}
{{ end }}
```