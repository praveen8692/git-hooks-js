# git-hooks-js [![NPM version](https://badge.fury.io/js/git-hooks.svg)](http://badge.fury.io/js/git-hooks) [![Build Status](https://travis-ci.org/tarmolov/git-hooks-js.svg)](https://travis-ci.org/tarmolov/git-hooks-js)

`git-hooks` is an utility for managing and running project [git hooks](http://git-scm.com/docs/githooks).

Just [install git-hooks](#install) and it will run your hooks when a hook is called by git.

## Why do you need git hooks in your project?
Hooks are little scripts you can place in `$GIT_DIR/hooks` directory to trigger action at certain points.

They are very powerful and helpful.

You can do a lot of things with them:

  * [Validate code](http://jshint.com/) and run tests before commit.
  * [Check codestyle](http://jscs.info/).
  * Spell check the commit message or check it format.
  * and etc.

**Note.** When you use `git-hooks`, you should not modify `$GIT_DIR/hooks` directory manually because `git-hooks` will do it for you.

## Install
Install `git-hooks` in your project.
```bash
npm install git-hooks --save-dev
```

To keep things organized, `git-hooks` looks for scripts in sub-directories named after the git hook name.
All these sub-directories should be stored in `.githooks` directory in the project root.

Let's create some dummy pre-commit hook.
```bash
mkdir -p .githooks/pre-commit
echo -e '#!/usr/bin/env node' "\nconsole.log('hello, world');" > hello.js
chmod +x hello.js
```

Then just try to commit and see how things are rolling.

See also [hooks examples](examples).

## Related projects
  * Original [git-hooks](https://github.com/icefox/git-hooks) project
  * [pre-commit](https://github.com/observing/pre-commit)
