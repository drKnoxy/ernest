# Ernest : A writer's interface to [Hugo](https://github.com/spf13/hugo/)
> There is nothing to writing. All you do is sit down at a typewriter and bleed.
> - Ernest Hemingway

## Feature Set
### MVP
* [x] electron app

* [ ] markdown editor
    * [ ] syntax highlighting / theme
    * [ ] code folding
    * [ ] menu bar for formatting; (b,i) (h1,h2,h3), (a,img), (blockquote, ul, ol), (?)
    * [ ] keybindings

* [ ] front matter editor [docs](https://gohugo.io/content/front-matter/)
    * [ ] pull the front matter off of the .md file and
      convert it to inputs.
    * [ ] maybe toss this editor in a different sidebar
    * [ ] autocomplete for tags / categories?
    * [ ] toml / yaml / json ?

* [ ] file browser / tree view
    * limit filetypes shown to folders and .md?
    * file actions
        1. select {name} -> opens in editor
        1. create {name} -> hugo new {name}
        1. rm {file}     -> rm from public
        1. file name change?
    * folder actions
        1. mkdir
        1. rename
        1. rm -r

* [ ] project actions
    * [ ] commit {msg} -> git commit -m {msg}
    * [ ] build        -> hugo
    * [ ] preview      -> hugo server OR we just bring up the html in a new / embedded view
    * [ ] deploy       -> hugo && git push

* [ ] watch for .md files -> hugo compile that one file
    * need to check if hugo supports this
    * what about files that would be effected by this change, ie if i update the menu frontmatter there is a
      bigger ripple effect.


### Roadmap / Ideas
1. theme building features
    * compile sass _where to? assuming hugo still moves the files_
    * `.go.html` syntax highlighting _i can't find any golang template syntaxes so we might have to roll one_
    * watch for
        1. `/themes/**/*.html`      -> hugo compile site
        1. `/themes/**/*{.css,.js}` -> hugo compile static

1. shortcodes
    * syntax highlighting
    * maybe some addition to

1. search content
    * probably dependent on hugo outputing some searchable json files first

1. site configuration [hugo docs](https://gohugo.io/overview/configuration/)
    * probably need some type of sitewide management / settings


## Underlying Tech
* npm global module
    * starts a server for the interface
    * api for actions is under `/api/`
* gulp - watching & asset pipeline
* angularjs - keep our spa clean
* [codemirror](https://codemirror.net/) or ace - text editor
* sass & flexbox - styling preprocessors


## Relavent links
* [Hugo v1 roadmap](https://discuss.gohugo.io/t/roadmap-to-hugo-v1-0/2278/3)
* [Hugo Discuss: Web based editor](https://discuss.gohugo.io/t/web-based-editor/155/59)
* [Design Inspiration on Pinterest](https://www.pinterest.com/adamwknox/web-markdown-editor-ui/)
* [Webhook on github](https://github.com/webhook) [Webhook Site](http://www.webhook.com/)