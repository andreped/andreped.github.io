Personal website
===================================

[![Website andreped.github.io](https://img.shields.io/website-up-down-green-red/https/andreped.github.io.svg)](https://andreped.github.io/)

<img src="https://github.com/andreped/andreped.github.io/releases/download/screenshot-website/screenshot.png" width="80%" height="80%">

## Getting started

#### Production
This repository uses continuous deployment; for every successful commit, the website will be updated directly.
The website is hosted through GitHub Pages, hence, no development setup is required to update the website.
The snapshot in this README shows the current state of the website.

#### Development
If you wish to develop locally, it is required that you have some tools installed.
* Ruby
* Bundler
* Python
* Pip

Then you can build the website by running these commands:

```
$ bundle install
$ pip install jupyter
$ bundle exec jekyll serve --lsi
```

Now, feel free to customize the theme however you like (don't forget to change the name!). After you are done, commit your final changes.

## Credit

All credit to [alshedivat](https://github.com/alshedivat) for making such a great template! This repo is a detached fork from [al-folio](https://github.com/alshedivat/al-folio).
