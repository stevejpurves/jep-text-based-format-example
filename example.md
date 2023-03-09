---
metadata:
  kernelspec:
    display_name: 'Python 3'
    langauge: 'python'
    name: 'python3'
  langauge_info:
    codemirror_mode:
      name: 'ipython'
      version: 3
    file_extension: 'py'
    mimetype: 'test/x-python'
    name: 'python'
    nbconvert_exporter: 'python'
    pygments_lexer: 'ipython3'
    version: '3.8.10'
nbformat: 4
nbformat_minor: 5
---

+++ { id="9b818e95-48f7-4dd3-b0fd-9f3e91f63d6b" }

# An Example Notebook

This is an example notebook to help describe the jupyter text-based notebook format that was developed during the [Juptyer Notebook Format Community Workshop](https://blog.jupyter.org/jupyter-community-workshop-the-notebook-file-format-8133ed606118) in Massy, Feb 2023. This proposal will be formalized in a [JEP](https://github.com/jupyter/enhancement_proposals).

+++ { id="3bb109c4-dbb4-43f5-aa1c-bb9c1f010d7b" }
The notebook is intented to include all major elements being considered in the proposal, including:

- Markdown content split accross multiple cells
- Raw cells
- Cell attachments
- Code cells
- Code cell outputs
  - stream
  - error
  - execute_result
  - display_data
- Cell metadata

```{jupyter.raw-cell id="3f11da3f-dfe0-4d40-a569-c43d6d403e00"}
This is the content of a RAW cell
```

+++ { id="fa415560-f20c-4726-ad58-5c90002395fd", "slideshow": { "slide_type": "slide" }, "tags": ["method"] }

## Attachments

This is a Markdown cell with two (tiny) attachments: ![orange_dot.png](attachment:cf220f8c-b64b-464d-b6c0-f213fbe81e4a.png) ![green_dot.png](attachment:58a0b827-f4b0-48cb-899f-08e3b607e7b4.png)

**and** has `tags` and `slide` metadata

```{jupyter.attachment}
:label: 58a0b827-f4b0-48cb-899f-08e3b607e7b4.png
{ "image/png": "iVBORw0KGgoAAAANSUhEUgAAAAMAAAADCAIAAADZSiLoAAABhWlDQ1BJQ0MgcHJvZmlsZQAAKJF9kT1Iw0AcxV9TpVoqDnYQcchQnSyIFhFctApFqBBqhVYdTC79giYNSYqLo+BacPBjserg4qyrg6sgCH6AuLo4KbpIif9rCi1iPDjux7t7j7t3gFAvM83qGgc03TZTibiYya6KgVf40YsgYpiRmWXMSVISnuPrHj6+3kV5lve5P0efmrMY4BOJZ5lh2sQbxFObtsF5nzjMirJKfE48ZtIFiR+5rrj8xrnQZIFnhs10ap44TCwWOljpYFY0NeIYcUTVdMoXMi6rnLc4a+Uqa92TvzCU01eWuU5zGAksYgkSRCioooQybERp1UmxkKL9uId/qOmXyKWQqwRGjgVUoEFu+sH/4He3Vn5ywk0KxYHuF8f5GAECu0Cj5jjfx47TOAH8z8CV3vZX6sD0J+m1thY5Avq3gYvrtqbsAZc7wOCTIZtyU/LTFPJ54P2MvikLDNwCwTW3t9Y+Th+ANHWVvAEODoHRAmWve7y7p7O3f8+0+vsBvYNyxURpgWsAAAAJcEhZcwAALiMAAC4jAXilP3YAAAAHdElNRQfnAwkKOiGZav8xAAAAGXRFWHRDb21tZW50AENyZWF0ZWQgd2l0aCBHSU1QV4EOFwAAABdJREFUCNdjDHkewsDAwMDAwMQAAwgWACwcAZVTjMnZAAAAAElFTkSuQmCC" }
```

```{jupyter.attachment}
:label: cf220f8c-b64b-464d-b6c0-f213fbe81e4a.png
{ "image/png": "iVBORw0KGgoAAAANSUhEUgAAAAMAAAADCAIAAADZSiLoAAABhWlDQ1BJQ0MgcHJvZmlsZQAAKJF9kT1Iw0AcxV9TpVoqDnYQcchQnSyIFhFctApFqBBqhVYdTC79giYNSYqLo+BacPBjserg4qyrg6sgCH6AuLo4KbpIif9rCi1iPDjux7t7j7t3gFAvM83qGgc03TZTibiYya6KgVf40YsgYpiRmWXMSVISnuPrHj6+3kV5lve5P0efmrMY4BOJZ5lh2sQbxFObtsF5nzjMirJKfE48ZtIFiR+5rrj8xrnQZIFnhs10ap44TCwWOljpYFY0NeIYcUTVdMoXMi6rnLc4a+Uqa92TvzCU01eWuU5zGAksYgkSRCioooQybERp1UmxkKL9uId/qOmXyKWQqwRGjgVUoEFu+sH/4He3Vn5ywk0KxYHuF8f5GAECu0Cj5jjfx47TOAH8z8CV3vZX6sD0J+m1thY5Avq3gYvrtqbsAZc7wOCTIZtyU/LTFPJ54P2MvikLDNwCwTW3t9Y+Th+ANHWVvAEODoHRAmWve7y7p7O3f8+0+vsBvYNyxURpgWsAAAAJcEhZcwAALiMAAC4jAXilP3YAAAAHdElNRQfnAwkKOgY8YEpaAAAAGXRFWHRDb21tZW50AENyZWF0ZWQgd2l0aCBHSU1QV4EOFwAAABdJREFUCNdj/DovioGBgYGBgYkBBhAsADb/AfM4ZRkyAAAAAElFTkSuQmCC" }
```

```{jupyter.code-cell execution_count=2 id="3b0fc308-633a-4322-9dcb-ff0d06fe70dc"}
# a python code cell with no outputs
x = 1;
```

```{jupyter.code-cell execution_count=5 id="7566aa84-cbd8-4d5a-8324-e850c5c03b64"}
# # a python code cell producing a stream
print('hello markdown!')
```

```{jupyter.cell-output output_type="stream" name="stdout"}
hello markdown!
```

```{jupyter.code-cell execution_count=3 id="54d3c313-37c3-4a61-9240-60f4f3bd6f18"}
# a python code cell procuding an execute_result (text/plain)
1 + 1
```

```{jupyter.cell-output output_type="execute_result"}
{ "text/plain": "2" }
```

```{jupyter.code-cell execution_count=18 id="d72a6c1d-011f-4667-9dd0-0d71ec3a9d8f"}
# a python code cell producing a display_data (text/plain, text/html, image/png)
from IPython.display import display, TextDisplayObject, HTML, Image

display(HTML(\"<div>hello html!</div>\"));
display(Image(filename=\"./blue_dot.png\", embed=True))
```

```{jupyter.cell-output output_type="display_data"}
{ "text/html": "<div>hello html!</div>" }
{ "txt/plain": "<IPython.core.display.HTML object>" }
```

```{jupyter.cell-output output_type="display_data"}
{ "image/png": "iVBORw0KGgoAAAANSUhEUgAAAAMAAAADCAIAAADZSiLoAAABhWlDQ1BJQ0MgcHJvZmlsZQAAKJF9kT1Iw0AcxV9TpVoqDnYQcchQnSyIFhFctApFqBBqhVYdTC79giYNSYqLo+BacPBjserg4qyrg6sgCH6AuLo4KbpIif9rCi1iPDjux7t7j7t3gFAvM83qGgc03TZTibiYya6KgVf40YsgYpiRmWXMSVISnuPrHj6+3kV5lve5P0efmrMY4BOJZ5lh2sQbxFObtsF5nzjMirJKfE48ZtIFiR+5rrj8xrnQZIFnhs10ap44TCwWOljpYFY0NeIYcUTVdMoXMi6rnLc4a+Uqa92TvzCU01eWuU5zGAksYgkSRCioooQybERp1UmxkKL9uId/qOmXyKWQqwRGjgVUoEFu+sH/4He3Vn5ywk0KxYHuF8f5GAECu0Cj5jjfx47TOAH8z8CV3vZX6sD0J+m1thY5Avq3gYvrtqbsAZc7wOCTIZtyU/LTFPJ54P2MvikLDNwCwTW3t9Y+Th+ANHWVvAEODoHRAmWve7y7p7O3f8+0+vsBvYNyxURpgWsAAAAJcEhZcwAALiMAAC4jAXilP3YAAAAHdElNRQfnAwkLCxV/QWYBAAAAGXRFWHRDb21tZW50AENyZWF0ZWQgd2l0aCBHSU1QV4EOFwAAABdJREFUCNdjDIl6zsDAwMDAwMQAAwgWACwxAZsfBT8MAAAAAElFTkSuQmCC" }
{ "text/plain": "<IPython.core.display.Image object>" }
```

```{jupyter.code-cell execution_count=27 id="d641c232-7511-455d-a6b4-437465bc8b18"}
# a python code cell the produces an error, with a traceback
x = two_x
```

```{jupyter.code-output output_type="error"}
\u001b[0;31m---------------------------------------------------------------------------\u001b[0m
\u001b[0;31mNameError\u001b[0m                                 Traceback (most recent call last)
Cell \u001b[0;32mIn[27], line 2\u001b[0m\n\u001b[1;32m      1\u001b[0m \u001b[38;5;66;03m# a python code cell the produces an error, with a traceback\u001b[39;00m\n\u001b[0;32m----> 2\u001b[0m x \u001b[38;5;241m=\u001b[39m \u001b[43mtwo_x\u001b[49m
\u001b[0;31mNameError\u001b[0m: name 'two_x' is not defined
```

## Empty

The following two cells are intentionally empty

```{jupyter.raw id="d9332d23-16af-48d1-a858-f41e7e6e5c82"}

```

```{jupyter.code-cell id="3f9a10ae-b36c-4ae8-a0ae-69453f671047"}

```
