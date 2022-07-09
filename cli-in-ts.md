[![XTechnology - Technology is beautiful, let's discover it together!](https://user-images.githubusercontent.com/1259644/139526072-c2df5b3f-86b3-40eb-a91a-e51a307269ec.png)](https://xtechnology.dev/)

<div class="twitter-btn">
  <a href="https://twitter.com/XTechnology5/status/1513973177768157200"><i></i>
  <span>Tweet about us!</span></a>
</div>

# Mastering CLI with TypeScript

We like Node, Command Line Interfaces, JavaScript and TypeScript. We write and speak about technologies in meetups and conferences. However, the best knowledge sharing - is live sessions with theory and coding exercises. This is exactly what this workshop is about

In 3 hours we'll write a complete CLI application. You will have a project in your Github repository, ready to use and evolve. You will know how it is designed, understand technologies and best practices it is following

## How it Goes

We will start with theory - overview key concepts of building a Command Line Interface program. By making a tiny example in Node, we explore npm and package.json capabilities, compare different technologies. We build a TypeScript based pluggable CLI with oclif framework and design internal's business logic. In the final part we polish program UX and output using various libraries.

Our goals are to learn awesome technologies, practice modern techniques, and of course, make your CLI application production ready!

## Agenda

- Introduction 💡
- About CLI in Node 📖
- Hello World CLI in Node 👋
- Make it Work with oclif 🛠️
- Make it Shine ⭐
- oclif in Depth 🏊
- Final 🎉

### Prerequisites

- You’ll need to have a laptop with you. Windows, Linux or Mac doesn’t matter. Ideally, you should feel comfortable using this computer for daily tasks. Don't forget to take a charger.
- [Preinstall Node.js, npm](https://nodejs.org/en/download/)
- Git, account on [Github](https://github.com/)
- [Preinstall Protocol Buffer Compiler](https://grpc.io/docs/protoc-installation/)
- We prefer to use VSCode for a better experience with JavaScript and TypeScript (other IDEs are also ok)

### Instructors

[Alex Korzhikov](https://twitter.com/AlexKorzhikov) & [Pavlik Kiselev](https://www.linkedin.com/in/pavlik-kiselev-06993347/)

### Materials

- Workshop - NodeConfEU 2019
- [Repository](https://github.com/korzio/note)

![repository-open-graph-template 1](https://user-images.githubusercontent.com/1259644/115153860-493a2880-a078-11eb-85c8-201b1512ee4b.png)


# Mastering CLI with TypeScript

## Workshop Begins!

# Introduction

## Agenda

![Node](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/node.png?raw=true)

- Introduction

- CLI in Node
  - Basic Principles
  - Examples - npm, git

- Hello World CLI in Node
  - `package.json`
  - `TypeScript`
  
- Make it Work with `oclif`
  - Configure `oclif` project
  - Arguments & Flags
  - Develop a command to `slack` hello world

- Make it Shine 
  - Input & Output
  - Effects

- `oclif` in Depth
  - Hooks
  - Tests
  - Plugins

- Final

## Goals

![Node](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/node.png?raw=true)

- Understand Basic CLI Concepts

- Practice coding `JavaScript` & `TypeScript` CLI programs in `Node` 

- Overview popular `npm` tools, libraries & frameworks for constructing CLIs

- Make an `oclif` CLI application to manipulate `Github` repository and send notifications to `slack`

![github](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/github.png?raw=true)

## Who are we?

![Alex](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/team/alex.jpg?raw=true)

### Alex Korzhikov
#### `JavaScript, Node, Web Components, TypeScript` 
### @ING @Otus

- Twitter: **[AlexKorzhikov](https://twitter.com/AlexKorzhikov)**  
- Medium: **[korzio](https://medium.com/@korzio)**  
- Github: **[korzio](https://github.com/korzio)**  

## Who are we?

![Pavlik](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/team/pavlik.jpg?raw=true)

### Pavlik Kiselev
#### `JavaScript, Serverless, React, GraphQL` 
### @Frontmen

- **[LinkedIn](
https://www.linkedin.com/in/pavlik-kiselev-06993347/)**  
- Github: **[paulcodiny](https://github.com/paulcodiny)**  

# CLI in Node.js

> A command-line interface or command language interpreter (CLI), is a means of interacting with a computer program where the user (or client) issues commands to the program in the form of lines of text (command lines). A program which handles the interface is called a command language interpreter or shell.

> Shell is a **program** that takes commands from the keyboard and gives them to the operating system to perform

- [SS64 Command line reference](https://ss64.com/)

```bash
cat /etc/shells   # List of shells
cat /etc/passwd   # Default shell
```

© Wiki

## ¿Por qué?

### Which CLI program
- Do you like?
- Do you use the most?

![question](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/question.png?raw=true)
  
- Why `CLI`?
- Why `JavaScript`?
- Why `Node`?
- Why `TypeScript`?

## Why CLI?

- **Tools** for
  - manipulating OS objects,
  - improving **developer experience** and
  - task automation
- *which allow to gain even more by combining them!*
- *It's fun!*

## Why Node?

### ➕

- Practice with `JavaScript`
  - `JavaScript` tools are the best for `JavaScript` & FrontEnd
- [Atwood's Law](https://blog.codinghorror.com/the-principle-of-least-power/) - *any application that can be written in JavaScript, will eventually be written in JavaScript*
- Fast and easy to develop
- Cross Platform
- A rich infrastructure with all kinds of packages and libraries with `npm` 
- Modules & plug'n'play

### ➖?
- `Node` need to be installed?!

## [Why TypeScript?](https://itnext.io/why-use-typescript-good-and-bad-reasons-ccd807b292fb)

### ➕

- Types for unifying protocols and interfaces, checked statically Ahead Of Time
  - According to [To Type or Not to Type: Quantifying Detectable Bugs in JavaScript
  by Zheng Gao, Christian Bird, Christian Bird](http://ttendency.cs.ucl.ac.uk/projects/type_study/documents/type_study.pdf) study, using TypeScript results in 15% decrease of bugs
  - Focus on API, not on implementation details
  
- OOP patterns and abstractions
- IDE help & support for writing code saves developers time

### ➖

- Takes more time to develop and maintain projects

## Principles Question

![question](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/question_ru.png?raw=true)

### Which basic principles of designing a `CLI` program you might mention?

```bash
npx cowsay hello cow
 ___________
< hello cow >
 -----------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```

## Examples

![NPM](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/icons/trim/npm.png?raw=true)
![git](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/git.png?raw=true)

### Principles

- Understand what's happening
  - `help`
  - `version`
- Output to the right channel 
  - Logs and data for `stdout`, errors for `stderr`
- Exit with `process.exit(code)` 
  - Retrieve with `$?` in `shell`
- *Do One Thing and Do It Well*
- *No breaking changes*

### Top

- `git`
- `npm`

### Generators & Developer Experience

- yeoman
- create-react-app
- angular-cli

## Workshop CLI

![workshop cli](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/cli-in-ts-10-14.gif?raw=true)

```bash
npm install --global cli-in-ts
workshop
# or workshop help
workshop hello
# and go to practice
workshop go
```

# Hello World CLI in Node

## package.json

```json
{
  "name": "my-hello-world-cli",
  "version": "1.0.0",
  "description": "Hello CLI",
  "main": "server.js",
  "bin": "server.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "man" : "./man/doc.1"
}
```

- `main` - exports
- `bin` - make an executable `symlink` inside `PATH`, `./node_modules/.bin/`
- `url` - [`npm bugs`](https://docs.npmjs.com/files/package.json#bugs) feedback on a package 🤗

### Execution

- `shebang` specifies an interpeter in `*nix` systems (also in `Windows`)

```js
#!/usr/bin/env node
```

- `process.argv` contains arguments which a program is called with

![question](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/question.png?raw=true)

### What will be an output of running `server.js`?

```javascript
// server.js
console.log(process.argv)
```

```bash
node server.js hello world
```

## Windows Specifics

- `Windows Console` - a program to run applications with text-based interface
- `cmd.exe` or `Command Prompt` - *venerable* Windows Command Processor
- `PowerShell` an extended scripting language and a framework, providing powerful command-line tools for most Windows capabilities and APIs

### Try to run `bash` directly with [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/about) (for Windows 10)

[![Bash on Ubuntu on Windows](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/bash-in-windows.png)](https://blogs.windows.com?raw=true/windowsdeveloper/2016/03/30/run-bash-on-ubuntu-on-windows/)

- [Learn About Windows Console & Windows Subsystem For Linux (WSL) - Microsoft](https://blogs.msdn.microsoft.com/commandline/learn-about-windows-console-and-windows-subsystem-for-linux-wsl/)

- Environment variables (`HOME` vs `HOMEPATH`)
- Use `path` build-in `Node` module to construct locations
- Running processes

```js
const { spawn } = require('child_process');
const bat = spawn('cmd.exe', ['/c', '"my script.cmd"']);
```

- [shelljs](https://www.npmjs.com/package/shelljs) - cross-platform implementation of `Unix` shell commands written in `Node`

### How to run Node program in Windows?

```bash
%USERPROFILE%/AppData/Roaming/npm
```

When running `npm install -g .` in Windows, `.cmd` extension file is generated along by `npm` to enable `.js` file execution with `Node`

#### `oclif run.cmd` example

```batch
@echo off

node "%~dp0\run" %*
```

- `%*` - will return the remainder of the command line starting at the first command line argument (in Windows NT 4, %* also includes all leading spaces)
- `%~dn` - will return the drive letter of %n (n can range from 0 to 9) if %n is a valid path or file name (no UNC)
- `%~pn` - will return the directory of %n if %n is a valid path or file name (no UNC)

- [Batch files - Command line parameters](https://www.robvanderwoude.com/parameters.php)
- [Spawning .bat and .cmd files on Windows - Official Node Documentation on Child Processes](https://nodejs.org/api/child_process.html#child_process_spawning_bat_and_cmd_files_on_windows)

## Practice - Hello World

### Make the Hello World CLI in Node

```bash
mkdir my-hello-world-cli
cd my-hello-world-cli
npm init
# answer npm questions and check package.json content
echo "console.log('Hello CLI')" > server.js
# check if environment works
npm start
# use bin package.json property to point to server.js
# don't forget to add the shebang 
# #!/usr/bin/env node
# in the top of the server.js file
# install cli globally
npm install --global .
# when execute the CLI in the terminal
my-hello-world-cli
# the result should be in the console
# Hello CLI
```

## Practice - Parse arguments

### Read `package.json` fields - `name`, `version`, and `description`

```json
"name": "my-hello-world-cli",
"version": "1.0.0",
"description": "My First Node.js CLI",
```

### Show help message when user doesn't provide any flags

```bash
my-hello-world-cli

Package description
Package version

Usage: 
--help    Help documentation
--version Installed package version
```

### Show version message when user provides `--version` argument

```bash
my-hello-world-cli --version

my-hello-world-cli 1.0.0
```

![spoiler alert](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/spoiler-alert.jpg?raw=true)

### [Hello World CLI in Node](https://github.com/korzio/note/blob/master/experiments/my-cli/index.js)

## TypeScript

*JavaScript that scales.  
TypeScript is a typed superset of JavaScript that compiles to plain JavaScript.  
Any browser. Any host. Any OS. Open source.*

![ts](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/ts.png?raw=true)

Anders Hejlsberg, 2012 @ Microsoft

### Tools

- `typescript, tsc` - compile to `JavaScript`
- `@types` - types definitions, [@types/node](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/node)
- `ts-node` - *on-the-fly* `TypeScript` execution for `Node`

## Practice - Hello World with TypeScript

### Migrate Hello World CLI to TypeScript

```bash
# install typescript globally
# or use npx instead
npm install --global typescript
# initialize typescript compiler project configuration file
tsc --init
# rename js file to ts
mv server.js server.ts
# @types/node 
npm install --save-dev @types/node
# compile project to typescript
tsc
# install cli globally
npm install --global .
# try if cli works
my-hello-world-cli
```

### Troubleshooting

#### `Cannot redeclare block-scoped variable 'name'.ts(2451)`

By default, `TypeScript` uses the `DOM` typings for the global execution environment and the `name` property exists on the global window scope.

There are two easy ways to avoid this problem:

- Use `modules` instead of `commonjs`

Change `require()` to `import ... from ...`.

To import from `json` module add the `resolveJsonModule` *TypeScript* compiler option.

- Don't include `DOM` typings. Add an explicitly empty `lib` array property in the `tsconfig.json` to not include `DOM`

```json
{
  "compilerOptions": {
    "lib": [
      "es2015"
    ]
  }
}
```

![spoiler alert](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/spoiler-alert.jpg?raw=true)

### [Hello World CLI in TypeScript](https://github.com/korzio/note/blob/master/experiments/my-cli/server.ts)

# Make it Work with oclif

## [oclif](https://oclif.io/)

### *Heroku, SalesForce* framework to build CLIs

### Features

- `TypeScript` (can be `JavaScript`)
- Auto-documentation
- Parse Arguments
  - Flags & Arguments
- Code generation (with `yeoman`)
  - Single & Multi
  - Project' folders structure
- Extend basic functionality
  - Plugins & Hooks
- Test & Build & Package

### Command

#### Extend `Command` base class for application's commands

```ts
import { Command } from '@oclif/command'

export class MyCommand extends Command {
  static description = 'description of this example command'

  async run() {
    console.log('running my command')
  }
}
```

### Arguments

#### Arguments are declared on the command level, parsed by `oclif` and used for documentation generation

- `yargs`, `nops`, or `minimist` as alternative libraries

- **Flags** change a format of an executed command `npm i --verbose`
- **Options** add customisation `git log --abbrev-commit --pretty=oneline -n 50`
- **Arguments** command operation targets `npm install yargs`
- **Standard Input**
- **Environment Variables**

```bash
LOG_LEVEL=debug note
```

```ts
import { Command, flags } from '@oclif/command'

export default class MyCommand extends Command {
  static flags = {
    logLevel: flags.string({
      description: `Environment variable 'LOG_LEVEL'.\nIt CAN NOT be passed as a flag`,
      env: 'LOG_LEVEL',
    })
  }

  async run() {
    const { flags: { logLevel } } = this.parse(MyCommand)
    
    console.log(`running my command with logLevel ${logLevel}`)
  }
}
```

## Practice - Configure oclif project

Create a new CLI project with `oclif` generator

```bash
npx oclif multi my-oclif-cli
cd my-oclif-cli
npm install -g .
my-oclif-cli hello
```

[Note - Project Management as CLI](https://github.com/korzio/note)

> Educational Open Source Project to practice with JavaScript, TypeScript, Node, oclif, Git, Web Components, and Project Management

## Practice - Make it Work

### Make a command [to send](https://www.npmjs.com/package/@slack/webhook) Hello World notification to `slack` 

```bash
npm install @slack/webhook
npx oclif command slack
```

### Example of input/output
```bash
my-oclif-cli slack "Hello from @username"
# the message "Hello from @username" appears in the slack channel
```

### Configure your Slack
`1.` How to obtain the WebHook URL for our [Slack Node-Edu Channel](https://join.slack.com/t/note-edu/shared_invite/enQtNzM5NDU3MDUzMDE0LWQwNjFmZDc0NzYwOTBhZDczNDUwZTM0ZDM2NGZhOTNlOWVlMWM4M2I1YmQyOWZiNWMzMGY0ODRmOWVmYzZiNDg):
  - Our Slack (preferable)
    1. Open the [link to Slack webhook](https://bit.ly/37eqCFs) in a new tab. Please note, that the page shows an error. That is expected since this is an actual WebHook which expects some params.
    2. Copy the URL of the page from point 1. We did not paste the WebHook link directly to the workshop because Slack immediately disables it once it gets public or, in other words, added to the workshop on GitHub.
  - Your Slack (only if you are sure)
    1. Register an app https://api.slack.com/apps (activate Webhooks with "Post to specific channels in Slack" permissions)
    2. Connect the app to any channel

`2.` Put the Webhook URL to `config/.slackrc` file as `SLACK_WEBHOOK_URL` environment variable

```bash
export SLACK_WEBHOOK_URL=___WEBHOOK_GOES_HERE___
# or
export SLACK_WEBHOOK_URL=$(echo "aHR0cHM6Ly9ob29rcy5zbGFjay5jb20vc2VydmljZXMvVEwwMzg2V1BOL0JRMzRWREhQVy9DTjg3d2NVYlE4YTkyMmhaZjBaeEgwMVM=" | base64 --decode)
# or 
export SLACK_WEBHOOK_URL=$(workshop slack)
```
    
`3.`  Import `.slackrc` to your shell with `source`
    
```bash
source config/.slackrc
```


### Install NPM dependencies

```bash
npm i @slack/webhook
```

### Write the command

`1.` Require an IncomingWebhook class from the `@slack/webhook`
  
```js
import { IncomingWebhook } from '@slack/webhook'
```

`2.` Set a description for your command

```js
static description = 'Send a message to a channel in Slack'
```

`3.` The text should be provided as an argument. So, lets define an argument

```js
static args = [
  {
    name: 'text',
    required: true
  }
]
```

`4.` Add a definition of the flag to `flags` section. You may still keep "help" flag since it's quite useful usually 
    
```js
static flags = {
  help: flags.help({
    char: 'h'
  }),
  slackWebhookUrl: flags.string({
    env: 'SLACK_WEBHOOK_URL',
    required: true
  })
}
```

`5.` In the very beginning of the `run` function lets get our `flags` and `args` from the input with the following line

```js
const { flags, args } = this.parse(Slack)
```
 
    
`6.` Next lets create a new instance of IncomingWebhook with a `slackWebhookUrl` flag
  
```js
const webhook = new IncomingWebhook(flags.slackWebhookUrl)
```
    
`7.`  Call the "send" method with an object containing "text" property with your text. Please bear in mind that this is an async function
```js
await webhook.send({ text: args.text })
```

![spoiler alert](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/spoiler-alert.jpg?raw=true)

### [Send Slack message code](https://github.com/korzio/note/blob/master/experiments/my-oclif-cli/src/commands/slack.ts)

```
my-oclif-cli slack "Hello World!"
```

# Make it Shine

## Effects

### Beautify Input and Output

`listr` - terminal task list
![listr](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/listr.gif?raw=true)

- Effects
  - `progress` show status
  - `figlet` ASCII output

- Decoration
  - `chalk, colors` for colors
  - `clui` output tables, status, charts
  - `cli-table` print table data

- Utilities
  - `clear` clear terminal
  - `debug` wrap console log

### @oclif/cli-ux

#### oclif utilities for input & output

```ts
import cli from 'cli-ux'
cli.prompt('What is your password?', {type: 'mask'})
```

#### Features

- `url(), open()` for urls
- `action()` immersive logs
- `table(), tree()` to print lists and structures

## Practice - List Github Issues

#### Make a command to list Github tasks 

![github](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/github.png?raw=true)

Use [@oclif/cli-ux](https://www.npmjs.com/package/cli-ux) or any other tools to

- show a spinner while loading information
- print the list
- colors for printing open & closed issues

```bash
npx oclif command github:issues
```

```bash
my-oclif-cli github:issues
Getting a list of issues... done
Number Title                                      Assignee      State Link                                     
66     workshop CLI                               korzio        open  https://github.com/korzio/note/issues/66 
65     fix: Changed the formatting of exercises   null          open  https://github.com/korzio/note/pull/65   
64     Workshop CLI in TS on Saturday 9am 3 hours korzio        open  https://github.com/korzio/note/issues/64 
63     Add test section and example to workshop   paulcodiny    open  https://github.com/korzio/note/issues/63
...
```

#### Configure an access

`1.`  Create a [Personal token](https://github.com/settings/tokens)

`2.` Add it to the config file `.githubrc` to variable `GITHUB_PERSONAL_TOKEN`

```bash
export GITHUB_PERSONAL_TOKEN=___TOKEN_GOES_HERE___
```

`3.`  Export this variable to the current shell with `source` command

```bash
source config/.githubrc
```
    
`4.`  Use the auth key with [@octokit/rest](https://octokit.github.io/rest.js/)

`5.`  Get the list of [Github issues](https://octokit.github.io/rest.js/#octokit-routes-issues-list-for-repo)


#### Install NPM dependencies

```bash
npm i cli-ux chalk @octokit/rest
```

### Write the code
`1.` Import `cli` from `cli-ux` to use advanced formatting

```js
import cli from 'cli-ux'
```

`2.` Import `chalk` from `chalk` to use colors

```js
import chalk from 'chalk'
```

`3.` Require the Octokit. This library is imported in a specific way

```js
import Octokit = require('@octokit/rest')
```

`4.` Set a description for your command

```js
static description = 'Get a list of issues'
```

`5.` Add arguments: one for an owner and for a repository

```js
static args = [
  {
    name: 'owner',
    required: false,
    description: 'An owner of a repository',
    default: 'korzio',
  },
  {
    name: 'repo',
    required: false,
    description: 'A repository',
    default: 'note',
  },
]
```

`6.` Add a `GITHUB_PERSONAL_TOKEN` flag to `flags` definition so oclif will put the environment variable to a flag

```js
static flags = {
  help: flags.help({
    char: 'h'
  }),
  githubPersonalToken: flags.string({
    description: `Environment variable GITHUB_PERSONAL_TOKEN`,
    env: 'GITHUB_PERSONAL_TOKEN',
    required: true
  })
}
```
  
`7.` Use `cli.action.start` to show the loader with some useful information what is happening
    
```js
cli.action.start('Getting the list of the issues')
```
    
`8.` Create a new instance of Octokit with an object argument containing the "auth" property with the auth key created in the previous section
    
```js
const octokit = new Octokit({
  auth: flags.githubPersonalToken
})
```
   
`9.` Call the "issues.listForRepo" method with an object argument containing "owner" and "repo" keys. You can pass "korzio" as an owner and "note" as a repository. Documentation of the method https://octokit.github.io/rest.js/#octokit-routes-issues-list-for-repo.
The result of this method is an object containing "data" property
    
```js
const { data: issues } = await octokit.issues.listForRepo({
  owner: 'korzio',
  repo: 'note',
})
```
    
`10.` Stop the loader with `cli.action.stop`
    
```js
cli.action.stop()
```
    
`11.` Show tha table with the "data" as the first argument and the object with table description as the second. You can use columns "number", "title", "assignee" with a getter to get deep property, "state" with a getter to color the resulting state, "html_url" with a different header

```js
cli.table(issues, {
  number: {},
  title: {},
  assignee: {
    get: row => row.assignee ? row.assignee.login : null,
  },
  state: {
    get: row => row.state === 'open' ? chalk.green('open') : chalk.red('closed'),
  },
  html_url: {
    header: 'Link'
  },
})
```

![spoiler alert](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/spoiler-alert.jpg?raw=true)

### [Get a list of issues code](https://github.com/korzio/note/blob/master/experiments/my-oclif-cli/src/commands/gh/issues.ts)
   
   ## Practice - Assign Yourself on an Issue

#### Develop a command [to change an assignee](https://octokit.github.io/rest.js/#octokit-routes-issues-update)

Use `@oclif/cli-ux` - `prompt()` functionality.

```bash
my-oclif-cli github:assignee
Do you want to start working on an issue? (Y/n) [y]: y
Which issue you want to pick up? Please provide the ID: 62
What is your GitHub login?: paulcodiny
```

`1.` Ask whether the user wants to start working on an issue. Use capital letter to communicate the default choice even though oclif helps with this

```js
const startWorking = await cli.prompt('Do you want to start working on an issue? (y/N)', {
  required: false,
  default: 'y'
})
```
 
`2.` If the choice is "y" then show additional promts

```js
if (['y', 'yes'].includes(startWorking.toLowerCase())) {
  const issueNumber = await cli.prompt('Which issue you want to pick up? Please provide the Number')
  const assignee = await cli.prompt('What is your GitHub login?')
  
  // ...
}
```

`3.` After the CLI script gathers all required inputs we can perform an update

```js
await octokit.issues.update({
  owner: args.owner,
  repo: args.repo,
  issue_number: issueNumber,
  assignees: [assignee]
})
```

`4.` Do not forget to communicate back the success message.

```js
this.log(`Assignee of the issue #${issueNumber} has been successfully changed to "${assignee}"!`)
```

![spoiler alert](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/spoiler-alert.jpg?raw=true)

### [Change an assignee code](https://github.com/korzio/note/blob/master/experiments/my-oclif-cli/src/commands/gh/assignee.ts)
   
   # `oclif` in Depth

## `oclif` Abstractions

#### Configuration in `package.json` with `oclif` property

```json
"oclif": {
  "commands": "./lib/commands",
  "bin": "my-oclif-cli",
  "plugins": [
    "@oclif/plugin-help"
  ],
  "hooks": {
    "commit": "./lib/hooks/commit/commit"
  }
},
```

#### oclif CLI `manifest` command generates configuration declaration for publish and load details purposes

#### List of useful plugins made by `oclif`, like `plugin-help`, `plugin-autocomplete` or `plugin-plugins`

### Hooks

#### Extending commands like lifecycle callbacks

- `init` - before any command when CLI is initialied,
- `prerun` - after `init` hook, but also before the command,
- `command_not_found` - if a command is not found before the error
- `preupdate`
- `update`
- `plugins:preinstall`

##### Custom hooks can be called programmatically

```ts
await this.config.runHook('custom', { arguments })
```

## Practice - Notify Slack on Issues Update

`1.` Generate a hook to notify slack on issues update

```bash
oclif hook notify --event=notify
cat src/hooks/notify/notify.ts
```

```ts
import {Hook} from '@oclif/config'

const hook: Hook<'notify'> = async function (opts) {
  process.stdout.write(`example hook running ${opts.id}\n`)
}

export default hook
```

`2.` Let's modify `github:assignee` command so it sends a notification to slack

```bash
my-oclif-cli github:assignee
## after the issue start command is finished
## the notify hook sends slack message
```

`3.` We'll need to add a environment variable input flag in the same way we did with slack command itself

```ts
slackWebhookUrl: flags.string({
  env: 'SLACK_WEBHOOK_URL',
  required: true
})
```

`4.` Parse the flag inside the `github:assignee` command

```ts
const {slackWebhookUrl: url} = flags
```

`5.` To execute the hook call the `runHook()` method on a command's context with appropriate arguments

```
this.config.runHook('notify', {url, text})
```

Now oclif should be able to find existing `notify` functionality

![spoiler alert](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/spoiler-alert.jpg?raw=true)

### [Notify slack on assignee change code](https://github.com/korzio/note/blob/master/experiments/my-oclif-cli/src/commands/gh/assignee.ts)

## Practice - Add Tests to `github:issues` Command


### Add a test to check the output of the `github:issues` 

```bash
npm test

> my-oclif@1.0.0 test /Users/paulcodiny/Projects/clits/experiments/my-oclif-cli
> nyc --extension .ts mocha --forbid-only "test/commands/github/issues.test.ts"



  github:issues
...

Getting a list of issues... done
Number Title                              Assignee State Link                                                 
33272  Google feedback on TypeScript 3.5  evmar    open  /microsoft/TypeScript/issues/33272 
    ✓ should format the table (3305ms)


  1 passing (3s)
...
```


### Update the `package.json`

Basically, for now we can focus only on one test and for it let's update a bit the `package.json`

```json
{
  "scripts": {
    "test": "nyc --extension .ts mocha --forbid-only \"test/commands/github/issues.test.ts\"",
  }
}
```


### Write the test

`1.` Import required dependencies
  
```js
import {expect, test} from '@oclif/test'
```

`2.` Create a `describe` section for the command

```js
describe('github:issues', () => {
  // ...
})
```

`3.` Create a test for the `issues` command 

```js
test
  // ... 
```

`4.` Mock the response from github with the help of `nock` package. Please note, we don't have `data` property in the response. If's automatically created for us by `nock`
    
```js
test
  .nock('https://api.github.com', api => api
    .get('/repos/korzio/note/issues')
    .reply(200, [
      {
        number: '33272',
        title: 'Google feedback on TypeScript 3.5 ',
        assignee: {
          login: 'evmar'
        },
        state: 'open',
        html_url: 'https://github.com/microsoft/TypeScript/issues/33272'
      }
    ])
  )
```

`5.` Capture the `stdout` to the variable. Pass `{ print: true }` to simplify debugging. It's not required for your build pipelines (CI/CD) and can be even harmful for your logs 

```js
test
  // nock...
  .stdout({ print: true })
```
 
    
`6.` Next let's run the command. We don't need to provide arguments - for now it will be `korzio/note` 
  
```js
test
  // nock...
  // stdout...
  .command(['github:issues'])
```
    
`7.` After all it's time for the expectations - `oclif` uses `chai` as the expectation library underneath 
```js
test
  // .nock...
  // .stdout...
  // .command...
  .it('should show the issues from github', ctx => {
     expect(ctx.stdout)
       .to.contain('33272')
       .and.to.contain('Google feedback on TypeScript 3.5')
       .and.to.contain('evmar')
       .and.to.contain('open')
       .and.to.contain('https://github.com/microsoft/TypeScript/issues/33272')
   })
```

![spoiler alert](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/spoiler-alert.jpg?raw=true)

### [github:issues test](https://github.com/korzio/note/blob/master/experiments/my-oclif-cli/test/commands/gh/issues.test.ts)

## Practice - Commands VS Plugins

- `Command` is a granular functionality
- `Plugin` is a pack of `commands`, `hooks` or other things grouped by semantic reasons

`1.` Move `Github` commands and logic into a new plugin

```bash
oclif plugin manage-github

     _-----_
    |       |    ╭──────────────────────────╮
    |--(o)--|    │   Time to build a oclif  │
   `---------´   │  plugin! Version: 1.13.6 │
    ( _´U`_ )    ╰──────────────────────────╯
    /___A___\   /
     |  ~  |
   __'.___.'__
 ´   `  |° ´ Y `

? npm package name manage-github
? description
? author Alex Korzhikov @korzio
? version 0.0.0
? license MIT
? Select a package manager npm
? TypeScript Yes
? Use tslint (linter for TypeScript) Yes
? Use mocha (testing framework) Yes
```

`2.` Move all the github related project code into a generated plugin

`3.` Update CLI core to be able installing other plugins

Please note - if in the first oclif exercise the CLI was generated as multi, `package.json` should already contain this dependency

```bash
npm i @oclif/plugin-plugins
```

`4.` Test functionality locally by installing the plugin into a core

```bash
my-oclif-cli plugins:link ./manage-github
my-oclif-cli github:assignee
# should still work
```

![spoiler alert](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/spoiler-alert.jpg?raw=true)

### [Split project code into plugins](https://github.com/korzio/note/tree/architecture-32/cli)

# Final

## Summary

![Node](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/node.png?raw=true)

- Understand Basic CLI Concepts

- Overviewed different `npm` packages for developing a CLI

- Practice with CLI in `Node` with `TypeScript` and popular frameworks & libraries

- Make an `oclif` CLI application to manipulate `Github` repository and send *Hello World* notifications to `slack` 

![github](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/github.png?raw=true)

## Feedback

### Please [share your feedback](https://forms.gle/HcTFj5dpHnxNS8PK8) on Mastering CLI in TypeScript workshop

```
workshop feedback
```

## Docs

- [Evolution of the Heroku CLI: 2008-2017](https://blog.heroku.com/evolution-of-heroku-cli-2008-2017)

- [12 Factor CLI Apps - Heroku](https://medium.com/@jdxcode/12-factor-cli-apps-dd3c227a0e46)

- [Building Great CLI Experiences in Node - Jeff Dickey, Heroku](https://www.youtube.com/watch?v=Izx3-KSuaM8)

- [Building an enterprise-grade CLI with oclif by Thomas Dvornik](https://www.youtube.com/watch?v=v4saIi5zoy8)

- [Build a JavaScript Command Line Interface (CLI) with Node.js — SitePoint](https://www.sitepoint.com/javascript-command-line-interface-cli-node-js/)

- [TypeScript Essentials 💡 Charly Poly](https://medium.com/@wittydeveloper/typescript-essentials-b7ae85b0f561)

- [Typescript: The Complete Developer's Guide — Stephen Grider](https://www.udemy.com/course/typescript-the-complete-developers-guide/)

## Thank you!

### Alex Korzhikov

- Twitter: **[AlexKorzhikov](https://twitter.com/AlexKorzhikov)**  
- Medium: **[korzio](https://medium.com/@korzio)**  
- Github: **[korzio](https://github.com/korzio)**  

### Pavlik Kiselev

- **[LinkedIn](
https://www.linkedin.com/in/pavlik-kiselev-06993347/)**  
- Github: **[paulcodiny](https://github.com/paulcodiny)**  

<style type="text/css">
  h1:first-child {
    display: none;
  }
  
  img[alt="andrew reddikh"] {
    filter: grayscale(100%);
  }

  img {
    max-width: 400px;
  }

  /* twitter button */
  .twitter-btn {
    width: 200px;
    display: inline-block;
    overflow: hidden;
    text-align: left;
    white-space: nowrap;
    vertical-align: top:
    zoom: 1;
    font-size: 13px;
    line-height: 26px;
    font-family: "Helvetica Neue",Arial,sans-serif;
  }
  .twitter-btn a {
    height: 28px;
    padding: 1px 10px 1px 9px;
    border-radius: 4px;
    position: relative;
    font-weight: 500;
    color: #fff;
    cursor: pointer;
    background-color: #1b95e0;
    border-radius: 3px;
    box-sizing: border-box;
    display: inline-block;
    text-decoration: none;
  }
  .twitter-btn a:hover {
    background-color: #0c7abf;
  }
  .twitter-btn a i {
    width: 18px;
    height: 18px;
    top: 4px;
    position: relative;
    display: inline-block;
    background: transparent 0 0 no-repeat;
    background-image: url(data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20viewBox%3D%220%200%2072%2072%22%3E%3Cpath%20fill%3D%22none%22%20d%3D%22M0%200h72v72H0z%22%2F%3E%3Cpath%20class%3D%22icon%22%20fill%3D%22%23fff%22%20d%3D%22M68.812%2015.14c-2.348%201.04-4.87%201.744-7.52%202.06%202.704-1.62%204.78-4.186%205.757-7.243-2.53%201.5-5.33%202.592-8.314%203.176C56.35%2010.59%2052.948%209%2049.182%209c-7.23%200-13.092%205.86-13.092%2013.093%200%201.026.118%202.02.338%202.98C25.543%2024.527%2015.9%2019.318%209.44%2011.396c-1.125%201.936-1.77%204.184-1.77%206.58%200%204.543%202.312%208.552%205.824%2010.9-2.146-.07-4.165-.658-5.93-1.64-.002.056-.002.11-.002.163%200%206.345%204.513%2011.638%2010.504%2012.84-1.1.298-2.256.457-3.45.457-.845%200-1.666-.078-2.464-.23%201.667%205.2%206.5%208.985%2012.23%209.09-4.482%203.51-10.13%205.605-16.26%205.605-1.055%200-2.096-.06-3.122-.184%205.794%203.717%2012.676%205.882%2020.067%205.882%2024.083%200%2037.25-19.95%2037.25-37.25%200-.565-.013-1.133-.038-1.693%202.558-1.847%204.778-4.15%206.532-6.774z%22%2F%3E%3C%2Fsvg%3E);
  }
  .twitter-btn a span {
    margin-left: 4px;
    white-space: nowrap;
    display: inline-block;
    vertical-align: top;
    zoom: 1;
  }
</style>
