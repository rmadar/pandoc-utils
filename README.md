# Writting documentation with pandoc

This repository contains various templates and building scripts based on [pandoc](http://pandoc.org) 
in order to produce article, slides or webpage with a predifined (and tunable) style.

## Setup the tool

First the user need to setup the proper environemental variables by doing:
```
source setup.sh
```
This will make aware the system where are the pandoc templates and let the user call the script from anywhere.
For an automatic setup, the user can use the following lines in `~/.bashrc` file:
```
export PANDOC_TEMPLATES=<installation-dir>/pandoc-templates/templates
export PANDOC_SCRIPTS=<installation-dir>/pandoc-templates/scripts
PATH=$PATH:${PANDOC_SCRIPTS}
```
where `<installation-dir>` is the directory where pandoc-templates is installed.

## Usage

The conversion can be done using three executable scripts with predefined setup.

### Latex article

```
makeArticle notes.md article.pdf
```

Title, author and abstract are specifed using the markdown file header. The table of contents is added by default
but this can be modified in `makeArticle`


### Latex book

The same options are available then for the article (execpt the abstract):

```
makeBook notes.md book.pdf
```

### Latex slides



```
makeSlides notes.md slides.pdf
```

### Webpage

```
makeWebpage notes.md blogpost.html
```


## Run the examples

There are two available example that can be ran in the `example` directory. 
One is based on some notes I took during a conference ([article](examples/NoteSUSY2018/Article.pdf), [slides](examples/NoteSUSY2018/Slides.pdf), [html](examples/NoteSUSY2018/Webpage.htm)),
and the other is based on the notebooks produce with [jupyter notebook](http://jupyter.org/) and exported
in markdown via `nbconvert` ([article](examples/BookRandomTopics/RandomTopics.pdf), [html](examples/BookRandomTopics/RandomTopics.html)).

## To-do-list

It might be interesting to have a look to [pandoc filter in python](https://github.com/jgm/pandocfilters) in 
order to properly perform the tasks below (and possibly many more).

- [ ] add logos on beamer presentations
- [ ] tune title page for LaTeX books
- [ ] modify latex template to remove horizontal line (so that slide transition don't appear in article.pdf)
- [ ] define a block appearing only on slides and not in the article 
(equivalent to `<div class="note">` but for slides only)
