### {{ .Title }}
{{ .RawContent }}
Recent Content:
{{- range first 5 .Site.RegularPages }}
  * {{ printf "%s" (partial "section-emoji" .) }}{{ .Title }}{{ with .Date }} ({{.Format "2 Jan, 2006"}}){{ end }}
{{- end }}
