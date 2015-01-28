# CLI for ProcessWire

A basic command line shell script for outputting informations about ProcessWire pages.

## Installation

* Follow the instructions from [Include & Bootstrap](https://processwire.com/api/include/) on the ProcessWire website.
* Edit `#!/usr/bin/php` to match your local dev setting.
* Edit the path in `include("/path/to/processwire/index.php");` to match your ProcessWire location.

## General information

The basic usage pattern looks like this: `pw <apiMethod> "selector" [field]*`

* `pw`: maps to the name of the main file in this repository (required).
* `<apiMethod>`: a ProcessWire API method like `get` or `find` (required).
* `"selector"`: a [ProcessWire selector](https://processwire.com/api/selectors/) like `"template=basic-page,children.count>5,limit=3"` (required).
* `[field]*`: custom fields you want to output (optional).

## Usage examples

* `pw get "/"` – Gets the root page and outputs the standard output defined in `pw`.
* `pw find "template=basic-page,limit=5" id name parent children` – Gets 5 pages with the template `basic-page` and only outputs the fields `id`, `name`, `parent` and `children` for each found page.
* `pw help` – Outputs usage instructions regarding the shell script.

## Notes

* For performance reasons pages output is limitted to 100. Adjust to your needs.
* When you don’t specify custom fields after the selector (aka the `[field]*` part) then a standard set of fields will be output.
