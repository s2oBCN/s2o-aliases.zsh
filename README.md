##  Aliases zsh

## Installation

### Oh-My-Zsh

Assuming you have [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh), you can
simply write:

```bash
git clone git@github.com:peterhurford/git-aliases.zsh.git ~/.oh-my-zsh/custom/plugins/git-aliases
echo "plugins+=(git-aliases)" >> ~/.zshrc
```

(Alternatively, you can place the `git-aliases` plugin in the `plugins=(...)` local in your `~/.zshrc` manually.)

(Once you have this plugin, you can clone this plugin via `clone peterhurford git-aliases.zsh` instead.  Much better!)

### Antigen
If you're using the [Antigen](https://github.com/zsh-users/antigen) framework for ZSH, all you have to do is add `antigen bundle peterhurford/git-aliases.zsh` to your `.zshrc` wherever you're adding your other antigen bundles. Antigen will automatically clone the repo and add it to your antigen configuration the next time you open a new shell.

### Bash
If you use the non-recommended alternative, bash, you can install this directly to you
r `~/.bash_profile`:

```bash
curl -s https://raw.githubusercontent.com/peterhurford/git-aliases.zsh/master/git-aliases.plugin.zsh >>
~/.bash_profile
```


## Customization

* If you don't want to run `git status` with every branch change, put `GIT_ALIASES_SILENCE_GIT_STATUS=1` into your `.zshrc` (or `.bash_profile`).

* If you want to automatically push a new branch upon branch creation (e.g., commit "Started <branchname>" with the creation of branch <branchname>), use `GIT_ALIASES_AUTO PUSH_NEW_BRANCH=1`.

* If you want to use [icdiff](https://github.com/jeffkaufman/icdiff) instead of `diff`, use `GIT_ALIASES_ICDIFF=1`.

* If you want to use the shorter, prettier version of `git status`, set `GIT_ALIASES_SHORTER_GIT_STATUS=1`.


## Why use this instead of the "git" plugin?
[Oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh/) already has a [git plugin](https://github.com/robbyrussell/oh-my-zsh/tree/master/plugins/git) you can optionally install that has aliases.

I obviously prefer my plugin better -- it has alias names that make more sense to me, and it has more complex aliases that make working on things much easier (especially Ruby projects with built in `bundle` and `migrate`), and stuff like autopush on new branch is really neeat.  But if you don't work with Ruby and don't like some of the style choices I made (though feel free to suggest options for futher customizations, see above), you might prefer that plugin instead.


## Why can't I use them both?
Pick a side, we're at war!

But in seriousness, I think if you use them both (include both in your plugin line), nothing crashes and they don't interfere much with each other.  You'll be able to use the custom commands both here and there (i.e., both `gco` and `co` will work to do `git checkout`) and nothing in either plugin overwrites functionality of the other plugin.


## Help! Tab completion isn't working for branch names like you said!
First, I think this only works in Zshell, so if you're not using Zshell, then that's your first problem.

If you are using Zshell and things aren't working, you have to mess with your settings.  If you have either `autoload -U compinit && compinit` or `setopt completealiases` in your `.zshrc`, remove them.

If that doesn't work, you may have to include `unsetopt completealiases` in your `.zshrc` because it is being set somewhere else.  Though doing this may break the functionality of a different plugin, so watch out and choose wisely!

If the problem still persists, it's a problem I haven't encountered myself yet.  File an issue and I can take a look!


## If you like this, you might also like...
* [Send.zsh](https://github.com/robertzk/send.zsh), a git command by robertzk that combines `git add .`, `git commit -a -m`, and `git push origin <branch>`.
* [Send.vim](https://github.com/peterhurford/send.vim), a vim plugin by me to do the above _without leaving vim_.
* [Git-it-on.zsh](https://github.com/peterhurford/git-it-on.zsh), git commands to open files on GitHub from the command line.
# s2o-aliases.zsh
