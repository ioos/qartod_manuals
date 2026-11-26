# Markdown version of the QARTOD manuals

This repository hosts Markdown versions of the [QARTOD manuals PDFs](https://ioos.noaa.gov/project/qartod/).

The markdow is published as [HTML pages](https://ioos.github.io/qartod_manuals/latest/) and can be converted to `docx` or `pdf` using `pixi` [1].

```
pixi run docx  # convert to docx
pixi run pdf  # convert to pdf
pixi run mkdocs  # Create the HTML
pixi run serve  # Serve the HTML pages locally
```

[1] https://pixi.prefix.dev/latest/installation/
