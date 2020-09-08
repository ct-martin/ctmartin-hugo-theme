### {{ .Title }}
{{ .RawContent }}
{{ if .Site.Params.titleEmojis }}📰 {{ end }}Recent Content:
{{- range first 5 .Site.RegularPages }}
{{- if .Permalink }}
  * [{{ printf "%s" (partial "section-emoji" .) }}{{ .Title }}{{ with .Date }} ({{.Format "2 Jan, 2006"}}){{ end }}]({{ .Permalink }})
{{- else }}
  * {{ printf "%s" (partial "section-emoji" .) }}{{ .Title }}{{ with .Date }} ({{.Format "2 Jan, 2006"}}){{ end }}
{{- end }}
{{- end }}
{{- with .Site.Params.readme_github_stats_username }}

<!-- Stats badges -->
![profile stats](https://github-readme-stats.vercel.app/api?username={{ . }}&show_icons=true&count_private=true&include_all_commits=true&hide_rank=true&hide=stars)
{{- end }}
{{- if .Site.Params.readmeAboutGenerated }}

This README was auto-generated! [See the code here]({{ .Site.Params.sourceurl }})
{{- end }}