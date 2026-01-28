---
title: "Design Documents"
---

# Design Documents

{{ range resources.Match "docs/*.pdf" }}
- [{{ .Name }}]({{ .Permalink }})
{{ end }}