# Export Zotero to an HTML site.

This project exports your local [Zotero] library to a usable HTML website.
This generated website has the following features:

* Easily access your papers, site snapshots, notes from a navigation tree.
* Provides metadata from collections and attachments (i.e. referenes etc).
* Display PDF papers and website snapshot (the latter as framed).
* Method to navigate to/view the paper/website snapshot directly.
* Snazzy look and feel from the latest [Bootstrap] CSS/Javascript library.


## Obtaining

The easist way is via the `pip` installer:
```bash
pip install zotsite
```


## Usage

Run the application (without the angle brackets):

```bash
zotsite -o <sitedir>
```

After the program runs, `sitedir` will be where the tool creates/generates the
the new site.

The website will work as served from either a website or from the local file
system.  You can pass `levels` as a URL encoded parameter to produce the number
of levels when the page is loaded.

On the left you can click on the tree to select collections or attachments.
You have to drill all the way down to the leaf level in the tree to get at your
attachements and notes.  At the leaf level you can select and unselect a node
but all other nodes are note *selectable*.

By clicking on a non-leaf node it expands or collapses everything *and* gives
the meta data for that collection.  Note that this behavior was decided more by
the way [Tree View] works more than anything else since it is designed to show
the entire tree list at once.


## Process

The tool does the following:

1. Exports the meta data (directory structure, references, notes, etc) from
   your [Zotero] library.  On MacOS, this is done by querying the file system
   SQLite DB files.
2. Copies a static site that enables traversal of the exported data.
3. Copies your [Zotero] stored papers, snapshot (sites) etc.
4. Generates a navigation tree to easily find your papers/content.


### Platform

This project uses the SQLite Python library and should run on other platforms
but assumes a directory structure that's been tested on OSX.


## Attribution

This software uses:
* Python 3
* [Bootstrap] version 4
* [Tree View] for Bootstrap


## Todo

Make the site portion a proper Javascript site.  Right now, all the `min`s are
added in the distribution to same directory as
the [main navigation/content](src/site/js/zotero.js) file.


## Changelog

An extensive changelog is available [here](CHANGELOG.md).


## License

Copyright © 2018 Paul Landes

Apache License version 2.0

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.


<!-- links -->
[Zotero]: https://www.zotero.org
[Bootstrap]: https://getbootstrap.com
[Tree View]: https://github.com/jonmiles/bootstrap-treeview
