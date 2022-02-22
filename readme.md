*This is a fork to make a permanent backup of a Wikidot site. Forked from [GitHub:Zokhoi/wdotcrawl](https://github.com/Zokhoi/wdotcrawl)*

This is a Python command line client for relatively popular wiki hosting
http://www.wikidot.com which lets you:

* List all pages on a site
* See all revisions of a page
* Query page source
* List number of pages on a site
* Query condition selection by category and/or tags

Most interestingly, it allows you to download the whole site as a Git repository, with proper commit dates, author and comments!

##### Dependencies

At least:

* Python 3, added to `Path` variable
* Git executable, added to `Path` variable
* python-beautifulsoup4
* python-gitpython
* python-requests
* python-tqdm

You can easily install dependencies (Python3 & Git should be installed manually) using the following commands:

```
pip install bs4
pip install gitpython
pip install requests
pip install tqdm
```

##### Examples:

    crawl.py http://example.wikidot.com --dump ExampleRepo --category "*"
    crawl.py http://example.wikidot.com --log --page example-page

It uses internal Wikidot AJAX requests to do its job. If you're from Wikidot, please don't break it. Thank you! We'll try to be nice and not put a load on your servers.

Downloading of large sites might take a while. If anything breaks, just restart the same command, it'll continue from where it crashed.

##### Useful links:

Wikidot code (very old) which simplifies things a bit:

* https://github.com/gabrys/wikidot/blob/master/php/modules/history/PageRevisionListModule.php

The descriptions for on-site modules are heavily correlated with AJAX ones:

* http://www.wikidot.com/doc-modules:listpages-module

Someone else did Wikidot AJAX:

* https://github.com/kerel-fs/ogn-rdb/blob/master/wikidotcrawler.py


#### TODO

 - Handle deleted images. Probably need to check the diff and check all pages for references if removed from one page.
