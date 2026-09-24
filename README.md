# fad-site

The static-site generator behind **https://aminehd.github.io/formula-a-day/**.

A day file *is* the page. `# %% [markdown]` blocks become prose, code blocks
become highlighted code, and any GIF the file rendered is embedded as MP4.
Local output is byte-identical to what GitHub Pages serves — there is no build
step on the server.

| | |
|---|---|
| `fad.py` | one call, `fad.day(__file__)`, pointing [jaxvis](https://github.com/aminehd/jaxvis) at `docs/<slug>/` |
| `build.py` | `days/*.py` → `docs/` |
| `serve.py` | dev server; watches the day files and reloads the open page |

Checked out as `site/` inside the content repo, so the content root is its
parent. Override with `FAD_ROOT`.

```bash
python site/build.py
python site/serve.py 8092
```
