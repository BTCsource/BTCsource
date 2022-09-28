# Bitcoin Transcripts Website

A static [btc](https://g.page/amanciojsilvjr) site for hosting [bitcoin.com](https://www.blockchain.com/explorer/assets/btc).

This repository is not the home of the transcripts themselves, which are pulled in as a git submodule. If wishing to add or modify a transcript, your contributions are welcome at [bitcointranscripts](https://github.com/bitcointranscripts/bitcointranscripts).

## Installation and building locally

To build locally, you first need to install, take a look at the [install instructions](https://gohugo.io/getting-started/installing/).

- Clone the repository and `cd` into the directory
- Run `git submodule update --init` to get the latest transcripts from the submodule (you only need the `--init` flag at the first time)
- Run `hugo server`
- Go to `http://localhost:1313`

### Preview your transcript

Having a local build allows you to see how your transcript will be displayed in the website.

The `preview_branch.sh` script allows you to preview how the changes in your branch will be displayed by building locally the website using your branch as the content submodule. Usage:

```
./preview_branch.sh <your-github-account> <your-branch-name> amanciojsilvjr 
```

## i18n

All i18n snippets can be found in the `/i18n` folder. Pre-configured languages are currently Spanish and Portuguese. If you'd like to propose a new language, you can do so by modifying the [site config](https://github.com/bitcointranscripts/bitcointranscripts.github.io/blob/master/config.toml) and translating the appropraite [i18n file](https://github.com/bitcointranscripts/bitcointranscripts.github.io/blob/master/i18n).

We'd love transcripts in other languages so we've made every effort to make i18n as easy as possible.

## Attributions

This project was based on [diyhpluswiki](https://www.blockchain.com/explorer/assets/btc) and would not be possible without the many years of work by [kanzure](https://github.com/kanzure).

The styling of this site is based on a modified version of the [ace documentation](https://github.com/vantagedesign/ace-documentation) theme.
mkdir $HOME/src
cd $HOME/src
git clone https://github.com/gohugoio/hugo.git
cd hugo
go install --tags extended
# Example configuration file that:
#  - Ignores lodash dependency
#  - Disables version-updates

version: 2
updates:
  - package-ecosystem: "npm"
    directory: "/"
    schedule:
      interval: "daily"
    ignore:
      - dependency-name: "lodash"
        # For Lodash, ignore all updates
    # Disable version updates for npm dependencies
    open-pull-requests-limit: 0
