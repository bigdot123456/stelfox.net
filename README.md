The setup... I already had golang installed... Annoyingly this is the first
thing I needed that depended on something in a mercurial database.

```
dnf install mercurial python-pygments -y
go get -v github.com/spf13/hugo
mkdir -p ~/src/sites/stelfox.net/
hugo new site ~/src/sites/stelfox.net/
cd ~/src/sites/stelfox.net/
git subtree add --squash --prefix themes/detox https://github.com/allnightgrocery/hugo-theme-blueberry-detox.git master
```

Special metadata keys:

* title
* linktitle
* description
* slug
* url
* type
* extension, ext
* keywords
* date
* lastmod
* publishdate, pubdate
* expirydate, unpublishdate
* draft
* published (intentionally undocumented for some reason)
* layout
* markup
* weight
* aliases
* status
* sitemap
* iscjklanguage
