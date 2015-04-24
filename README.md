
# wkhtmltopdf 0.13 issue with css ?

## My Config

- wkhtmltopdf 0.13.0-alpha-7b36694
- Windows 7 Pro SP1

## Description

I use Bootstrap to format my CSS. In 0.12 all is ok but in 0.13 css seems loaded with media `print` so we have differences between what we expect with 0.12 and 0.13. I mainly discoved that `backgrounds` are not display properly but we may have bigger impact.

## How to reproduce the issue ?

- You need node installed (or any http serveur)
- `git clone git@github.com:laguiz/wkhtmltopdf-issue-css.git`
- `cd wkhtmltopdf-issue-css`
- (with node) `http-server` in root folder
- Go to http://127.0.0.1:8080/ and make sure you see Bootstrap components properly (with backgrounds and proper fonts)
- Open new console and try to reproduce doing : `wkhtmltopdf.exe http://127.0.0.1:8080/ resultko.pdf`

## My observations

- I had to set `all` or `print` for media for styles to make sure we see something close to what we see on `screen` (see `<link />` tags in source).
- With media `screen` it's like css are not loaded (maybe expected feature)
- With wkhtmltopdf 0.12 everything works with media `screen` so we don't have (if not) differences between screen and our pdf.

## Questions

- Is it expected to have a differente media usage?
- If `print` is the normal behavour then how to display background out of the box? Any trick?



