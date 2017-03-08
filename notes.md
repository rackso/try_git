# Schibsted Notes

## Start

[Onboarding](https://confluence.schibsted.io/pages/viewpage.action?spaceKey=ST&title=Onboarding)

####GitHub Repos

- [Schibsted Spain](https://github.schibsted.io/scmspain)
- [SUI-Components](https://github.com/SUI-Components)
- [Git Extras](https://github.com/tj/git-extras/blob/master/Installation.md)

####Training

- [Frontend Courses (React + ES6)](https://confluence.schibsted.io/pages/viewpage.action?spaceKey=ST&title=Frontend+courses)
- [Books](https://confluence.schibsted.io/display/ST/Books)

####Slack Channels

|                        | CHANNELS                                                                        |
|------------------------|---------------------------------------------------------------------------------|
|Schibsted Global        |  [spt-all](https://sch-chat.slack.com/messages/spt-all)                         |
|                        |  [sch-everyone](https://sch-chat.slack.com/messages/sch-everyone)               |
|Schibsted Spain         |  [bcn-techtalk](https://sch-chat.slack.com/messages/bcn-techtalk)               | 
|                        |  [es-curso-js-experts](https://sch-chat.slack.com/messages/es-curso-js-experts) |
|                        |  [es-frontend](https://sch-chat.slack.com/messages/es-frontend)                 |
|                        |  [es-enablers](https://sch-chat.slack.com/messages/es-enablers)                 |
|Fotocasa (Suicide Squad)|  [es-suicide-squad](https://sch-chat.slack.com/messages/es-suicide-squad)       |
|                        |  [suicide-squad-bots](https://sch-chat.slack.com/messages/suicide-squad-bots)   |

Ask for private team channels.



## Development Tools

#### NVM

Use [nvm](https://github.com/creationix/nvm) to switch node versions.

|            | Recommended versions  |
|------------|-----------------------|
| npm        |  3.10.10              |
| node       |  4.7.2                |
| node - TDD |  6.10.0               |


#### npm

Remember that you need to use the NPM credentials to login the NPM for the corporative repos, or you won't be able to ```npm install``` anything.
The credentials can be provided by anyone from your team. They're composed by a user, a password and an email. With these data, you'll have to ```npm login``` in order to use them.

#### SSH keys

In order to clone the corporative repos, you'll need to define a SSH key in your Github user panel. Just follow [the document](https://help.github.com/articles/connecting-to-github-with-ssh/) to [add you key](https://github.com/settings/keys).

#### Component linker

Example from card to cardlist:
```
$ component-linker ../frontend-fc--uilib-cardlist
```
#### Web server

Update bash:
```
alias serverstart='sudo NODE_ENV=production REALESTATE_HOST=195.77.179.104 REALESTATE_PORT=80 ./node_modules/.bin/nodemon server/index.js'
alias serverstartpre='sudo NODE_ENV=preproduction REALESTATE_HOST=195.77.179.104 REALESTATE_PORT=80 ./node_modules/.bin/nodemon server/index.js'
alias serverwatch='NODE_ENV=production npm run dev:js -s'
alias serverwatchpre='NODE_ENV=preproduction npm run dev:js -s'
```
Init:
```
component-linker ../frontend-fc--web-server
serverstartpre
serverwatchpre
```

####UX

[Zeplin](https://zeplin.io/), collaboration tool between designers and developers.

####Atom linter
- linter
- linter-eslint
- linter-sass-lint
- linter-scss-lint

####Atom plugins (optional)
- react
- emmet
- git-time-machine
- highlight-selected
- atom-formatter-jsbeautify
- pretty-json
- file-icons
- formatter
- pigments
- rest-client
- sort-lintes

## Deploy

Local:
- `git add myFiles`
- `git commit -m "myTask"`
- `git push origin myBranch`

GitHub:
- Create Pull Request
- Wait for min 2 approvals
- Merge branch
- Delete branch

Local:
- `git checkout master`
- `git pull`
- Upgrade version in `package.json` - **Remember we use the [semantic versioning](http://semver.org/) when upgrading the version**
- `git commit -m "Upgrade to x.x.x"`
- `git release x.x.x`
- `npm publish`

## [Jenkins](http://172.16.100.35:8181/view/re-frontend-server/job/re-frontend-server-INSTALL/)

Build with para Parameters:
- INMESPRE03 -> Pre
- INMESWEC01 -> Pro (without users)
- NODE_ENV: preproduction
