# Real world React apps

> Real world React apps and their open source codebases for developers to learn from

Learn from React apps written by experienced developers.

You'll find the source code for the apps in the [`apps/`](apps/) subdirectory.

Thank you to every developer who has worked on a project this repo links to, your work is helping developers learn React.

## How to install on your computer

```bash
# Clone this git repo:
git clone git@github.com:jeromedalbert/real-world-react-apps.git

cd real-world-react-apps/

# The apps are linked to as git submodules.
# This will take some time... (see comment below for possible speedup)
git submodule update --init

# OR if you've got git 2.9+ installed try to run updates in parallel:
# git submodule update --init --jobs 4
```

## How you can analyze the apps

Some of the examples below use [ag](https://github.com/ggreer/the_silver_searcher), but could just as well use grep or equivalent.

#### Global searches

```bash
# Look for Yarn in markdown instructions
ag -C 'yarn' -G '\.md'

# Find out what cookie libraries people use
ag cookie -G 'package.json'
```

#### Compare a lot of files at once

```bash
# Find ideas on how to configure Webpack
# Opens all webpack.config files in your editor of choice (vim/code/etc)
vim $(find . -name '*webpack.config*')

# Output content from all package.json files
find . -name package.json | xargs cat
```

#### Find out how long eslintrc files tend to be
```bash
find . -name '*eslintrc*' | xargs wc -l | sort
```

#### Compare the popularity of let vs const
```bash
ag 'let ' --js --stats-only | head -n 1
ag 'const ' --js --stats-only | head -n 1
```

## Other Real World codebase collections

- Real World React Native https://github.com/jeromedalbert/real-world-react-native
- Real World Rails https://github.com/eliotsykes/real-world-rails
- Real World Sinatra https://github.com/jeromedalbert/real-world-sinatra
- Real World Ruby Apps https://github.com/jeromedalbert/real-world-ruby-apps
- Real World Ember https://github.com/eliotsykes/real-world-ember
- Know any others? Please open a PR and add the link here

## Information for contributors

#### Is your app the right fit?

- A real world app should be publicly accessible and used by real people in a production environment.
- Boilerplate, starter kits, libraries, and small demo/example projects are not accepted.
- Most of the code should be frontend-oriented, in order to focus on React. Small backends may be OK, but should constitute the minority of the codebase.
- For React Native only apps, contribute to [Real World React Native](https://github.com/jeromedalbert/real-world-react-native) instead.

Don't hesitate to submit a pull request if you meet the criteria!

#### How to add a Real World app

Given a GitHub repo for an app `githubuser/foo`:

```bash
# Inside the project root:
git submodule add -b master git@github.com:githubuser/foo.git apps/foo
```

#### Updating the apps submodules to latest

The apps in `apps/` are git submodules. Git submodules are locked to a revision and don't stay in sync with the latest revision.

To update the revisions, run:

```bash
# This will take some time:
git submodule foreach git pull origin master
```

---

# Contributors

- Jerome Dalbert http://jeromedalbert.com
- Contributions are welcome, fork the GitHub repo, make your changes, then submit your pull request! Reach out if you'd like some help.
