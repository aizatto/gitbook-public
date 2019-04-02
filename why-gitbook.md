# Why GitBook?

Requirements:

* Easy maintenance
* Git/file system support
  * In theory, easy migration to different platforms
  * Doesn't require me to have internet access
  * I can easily do a `grep` or `ack` locally to find information.
  * Markdown support
* * Easy styling

Pros:

* Nice UI
* Decent free Basic plan
  * Includes one free private book
* No need to always use command line
* Custom domains
* Google Analytics support
* [Syncs with GitHub](https://docs.gitbook.com/integrations/github)
  * Bi-directional support
  * I can make hooks into GitBook via GitHub hooks, see [gitbook-summary](https://github.com/aizatto/gitbook-summary)
* Renaming pages appears to maintain old URLs
  * Only if it is not moved to a different folder
* Works decently on my 11” iPad Pro 2018
  * Browsing is fine on quarter, half or full screen
  * Can’t use Safari’s split screen mode for editing
    * Require’s using full screen, sad

Cons:

* Organizing a lot of pages is difficult, even if nested
  * I currently have 59 pages and its difficult to reorganize
  * I may have to organize things on the filesystem/markdown
  * I could potentially move to a second GitBook, but I like everything organized in one for now
* Long pages can be very confusing
  * Better to break out the content into different pages
  * Increases the problem of organizing a lot of pages
* Content is not really "static"
* No sitemap.xml
  * Feature Request [https://gitbook.canny.io/feature-requests/p/sitemap](https://gitbook.canny.io/feature-requests/p/sitemap)

Dislikes:

* Doesn't use same header shortcuts as Google Docs

Limitations:

* See [GitBook and GitHub Limitations](https://docs.gitbook.com/integrations/github/limitations)
* Single theme
  * I don't really mind it. It's a decent but most importantly, usable theme.
* Logs to git [commit history](https://github.com/aizatto/gitbook-public/commits/master) could be nicer
* No offline read/write support
  * Workaround is to download the repository
* Moving pages doesn't redirect to new URL
  * For renaming pages in the same directory structure, the old url still works
  * For moving pages into a different directory, the old url will not work
* I tried to compile a version using their `gitbook-cli` tool but it failed on `notes/javascript/fetch.md`
  * [https://www.npmjs.com/package/gitbook](https://www.npmjs.com/package/gitbook)

Facts:

* GitBook stores assets/images under [`.gitbook/assets`](https://github.com/aizatto/gitbook-public/tree/master/.gitbook/assets)
* Assets retain their filename

Other static site generators: [https://www.staticgen.com](https://www.staticgen.com)

Previously using Phenomic. cons: Fully manual.

Other notable GitBooks:

* [Nikita Voloboev](https://wiki.nikitavoloboev.xyz/)

