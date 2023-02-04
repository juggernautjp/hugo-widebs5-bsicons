
# hugo-widebs5-bsicons

Hugo Modules for Hugo Widebs5 Theme to use [Bootstrap Icons](https://icons.getbootstrap.com/#icons).

This repository is a fork of [writeonlyhugo/hugo-module-bootstrap-icons](https://gitlab.com/writeonlyhugo/hugo-module-bootstrap-icons),
which is for [writeonlyhugo-theme](https://gitlab.com/writeonlyhugo/writeonlyhugo-theme) to use [Bootstrap Icons](https://icons.getbootstrap.com/#icons).

This module is for [twbs/icons](https://github.com/twbs/icons) v1.10.3.



## Use

Add the component to your Hugo site's config:

```yaml
module:
  imports:
    - path: "gitlab.com/writeonlyhugo/hugo-module-bootstrap-icons"
```

Now you can use the partial `bs-icon.html` to insert the icons anywhere:

```go
{{ partial "bs-icon.html" "clock" }}
```

If you want to use the font and classes, you need something like this:

```go
{{- $bsi := resources.Get "bootstrap-icons/font/bootstrap-icons.scss" -}}
{{- $bsi := $bsi | resources.ToCSS (dict "outputStyle" "compressed" "includePaths" (slice "assets")) -}}
<link rel="stylesheet" href="{{ $bsi.Permalink }}" type="text/css" media="all">

{{- $bsifont := resources.Match "bootstrap-icons/font/fonts/*" -}}
{{ range $bsifont }} {{- .Publish -}} {{ end }}
```

