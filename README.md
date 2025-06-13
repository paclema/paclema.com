### paclema.com
This repository contains the source code for my personal website. 
It is built using [Hugo](https://gohugo.io/) and is hosted on GitHub Pages.

To install Hugo, follow the instructions on the [Hugo installation page](https://gohugo.io/getting-started/installing/).

Run hugo server with: 
```bash
hugo server --buildDrafts --bind "0.0.0.0" --disableFastRender
```

### To create new hugo site:

```bash
hugo new site mysite
cd mysite
```

And create a new page:
```bash
hugo new posts/my-new-post.md
```


### Replace default theme:

```bash
git submodule deinit -f themes/old-theme
git rm -f themes/old-theme
rm -rf .git/modules/themes/old-theme
```

Then add the new theme:
```bash
git submodule add https://github.com/imfing/hextra themes/hextra
```

lastly, the config.toml file should be updated to use the new theme:
```toml
theme = "hextra"
```
