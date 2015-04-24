
# Illustration of wkhtmltopdf issue with css ?

## My Config

- wkhtmltopdf 0.13.0-alpha-7b36694
- Windows 7 Pro SP1

## How to reproduce the issue ?

- You need node installed (or any http serveur)
- `git clone git@github.com:laguiz/wkhtmltopdf-issue-css.git`
- `cd wkhtmltopdf-issue-css`
- (with node) `http-server` in root folder
- Go to http://127.0.0.1:8080/ and make sure you see Bootstrap components properly
- Open new console and try to reproduce doing : `wkhtmltopdf.exe http://127.0.0.1:8080/ resultko.pdf`

## My observations

- I had to define `style media to `all` or `print` to ensure we see something close to what we see on `screen`.
- With media `screen` it's like css are not loaded
- With wkhtmltopdf 0.12 everything works with media `screen`

## Questions

- Is it expected to have a differente media usage?
- If `print` is the normal behavour then how to display background out of the box? Any trick?




