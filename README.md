# Talon Docs

Documentation for [Talon](https://talonvoice.com/).

Currently it comes in two forms: "regular" HTML, which spans multiple pages, and single page HTML.

## With Pipenv

If you have pipenv and Python 3:

1. `git clone https://github.com/talonvoice/docs`
1. `cd docs`
1. `pipenv run make html singlehtml`
1. open `build/html/index.html` or `build/singlehtml/index.html`

## With plain virtualenv

1. Setup a virtualenv
1. Install Sphinx
    `pip install -r requirements.txt`
1. build the docs
    `make html singlehtml`
1. Look at `build/html/index.html` or `build/singlehtml/index.html`
