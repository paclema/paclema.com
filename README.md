### paclema.com
This repository contains the source code for my personal website. 
It is built using [Hugo](https://gohugo.io/) and is hosted on GitHub Pages.

To install Hugo, follow the instructions on the [Hugo installation page](https://gohugo.io/getting-started/installing/).

Run hugo server with: 
```bash
hugo server --buildDrafts --bind "0.0.0.0" --disableFastRender
```

## Setting up with Docker compose within my HomeLab stacks

Initially, I added this repository as a submodule to my stacks repository under the `services` folder with the command:

```bash
git submodule add https://github.com/paclema/paclema.com.git services/paclemaweb
git submodule update --init --recursive
```

Under my stacks repo, I create a new folder `paclema.com` adding the [docker-compose.yml](docker-compose.yml). Note here that it must be changed the volumen path to fit where the submodule source code is located, in that case under the `services/paclemaweb` folder.

I encountered some issues with the submodule, so I decided to use the source code as an external repository instead. The problem was that HUgo website could not recognice properly the git info when the repository was added as a submodule, so I had to remove the submodule and use the source code as an external repository. You can find the steps to do that in the [readme](readme.md) file of the `paclemaweb` stack.


## Run the stack with Docker Compose:
Run the following commands to set up the stack:
```bash
docker compose up -d
```

In case that you want to make a cleanup of Hugo´s cache, you can run the following command:
```bash
docker compose --profile cleanup run --rm cleanup
```
This will remove the Hugo cache and temporary files, and if the server is running, it will restart it automatically. But if the server is not running, it will skip the restart and just clean the cache and temporary website files.

And to clean and restart the stack, you can run:
```bash
docker compose down
docker compose --profile cleanup run --rm cleanup
docker compose up -d
```

To access the container log, you can run:
```bash
docker compose logs -f server
```

## Other useful information:

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

