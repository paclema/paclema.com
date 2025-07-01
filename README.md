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

### Installation Hextra theme via hugo module:

Official instructions for installing the Hextra theme using Hugo modules can be found [here](https://imfing.github.io/hextra/docs/getting-started/#steps).

```bash
# Initialize Hugo site
hugo new site my-site --format=yaml

# Initialize hugo module
hugo mod init github.com/username/my-site

# Add Hextra theme
hugo mod get github.com/imfing/hextra
```

Configure the theme in `config.yaml`:
```yaml
module:
  imports:
    - path: github.com/imfing/hextra
```
After configuring the modules, update them all with:
```bash
hugo mod get -u
```

### Setting up with Docker compose within my HomeLab stacks

In one other hand, I have added this repository as a submodule to my stacks repository under the `services` folder with the command:

```bash
git submodule add https://github.com/paclema/paclema.com.git services/paclemaweb
git submodule update --init --recursive
```

Under my stacks repo, I create a new folder `paclema.com` adding the [docker-compose.yml](docker-compose.yml). Note here that it must be changed the volumen path to fit where the submodule source code is located, in that case under the `services/paclemaweb` folder.