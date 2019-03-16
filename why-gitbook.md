# Why GitBook?

Requirements:

* Easy maintenance
* Git/file system support
  * Allows for easy migration
  * Doesn't require me to have internet access
  * I can easily do a `grep` or `ack` locally to find information.
  * In theory, easy migration to different platforms
* Markdown support
  * Easy styling

Pros:

* Nice UI
* Decent free Basic plan
  * Includes one free private book
* No need to always use command line
* Works well on iPad through Safari
* Custom domains
* Google Analytics support
* [Syncs with GitHub](https://docs.gitbook.com/integrations/github)
  * Bi-directional support
* Renaming pages appears to maintain old URLs
  * Only if it is not moved to a different folder

Cons:

* Organizing a lot of pages is difficult, even if nested
  * I currently have 59 pages and its difficult to reorganize
  * I may have to organize things on the filesystem/markdown
  * I could potentially move to a second GitBook, but I like everything organized in one for now
* Long pages can be very confusing
  * Better to break out the content into different pages
  * Increases the problem of organizing a lot of pages
* Content is really "static"

Limitations:

* Single theme
  * I don't really mind it. It's a decent but most importantly, usable theme.
* Logs to git commit history could be nicer
* No offline read/write support
  * Workaround is to download the repository
* Moving pages doesn't redirect to new URL
  * For renaming pages in the same directory structure, the old url still works
  * For moving pages into a different directory, the old url will not work

Other static site generators: [https://www.staticgen.com](https://www.staticgen.com)

Previously using Phenomic. Fully manual.

