# TeX

LaTeX (lah-tek) is awesome and is the typesetting software of choice for professionals working for nearly every journal and academics in every field other than biology. Somehow biologists have completely failed to notice this. We will use LaTeX because this will allow you to submit your manuscript for publication as-is because LaTeX can be converted via Pandoc to any other document format and retain its beauty and elegance. Additionally, many journals use LaTeX to publish their paper journals, and by submitting in LaTeX, you will obviate the need to manually migrate your paper to another format thus preventing transcription errors, which chan be time-consuming to detect and correct. Additionally, using LaTeX makes it easy to manage your bibliography with multiple collaborators without it breaking.

## Overleaf

Overleaf is Google Docs for LaTeX (no affiliation with Google). We have institutional access to Overleaf. We can collaborate on Overleaf, and we will use Git to clone and work on our files hosted on Overleaf in our respective project folders.

## Installation

If you are using macOS, use homebrew to inxtall TeXShop.

```bash
brew install --cask texshop # "--cask" may or may not be necessary
```

Hopefully this will also install BibDesk and TeXLive.

## *nota bene*

1. back-tick/grave is the forward quote and then the typical apostrophy is the back-quote. In LaTeX, to quote, do ``something something'' to get the correct output.
2. Greek symbols are available in math mode, e.g. "5 $\mu$L" for 5 microliters.
3. 

## BibDesk

Create new BibDesk library for each project. For a quick bibliography, download original citations, drag files into BibDesk libary window, highlight all and press command+k to generate new cite keys, and then select ``TeX Preview.'' Drag that into the
