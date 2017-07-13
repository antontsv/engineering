# Dotfiles

A few years back I have observed that my colleague was keeping Vim config files in version control, other scripts were in their own repositories as well. I thought it was very smart way to keep track over time. I also kept track of my scripts, notes and dot files in the home in version control.

People in software community has begun to share their files on Github and other platforms.

In 2016 I have tried major approaches described at [dotfiles.github.io](http://dotfiles.github.io)

Some of them are very simple that I used to do myself.
Is to copy the files from the repo into the homedir. Yes, it keep home dir pure, but forces you to spend time on synchronization.

[Other tools](https://github.com/RichiH/vcsh) suggest to have Git working dir in your `~`, while repository resides somewhere else. There are safe guards in place, so you don't `git clean` and remove any untracked files from your home dir. I have used this approach for a bit, but dropped it. It is way too complex for the operations I need.

There are quite a few package-based approaches, encryption-enabled git repositories and cross-platform managers that can follow JSON or YAML configuration instructions.

Some may manage files with ansible.

I have landed on [Homeshick](https://github.com/andsens/homeshick):
* Simple shell-based tool
* Lots of tests
* Does not change file names, you can still copy files is homeshick tool was not there
* Supports multiple repositories
* Allows you to synchronize multiple computers using source control sites like github or gitlab

The one change I made in my [Homeshick fork]((https://github.com/andsens/homeshick) is to get rid of `home` directory and to be able to copy/link directly. Yes, there is a necessary README and LICENCE which should not be copied or `.git` itself, but it was relatively easy to plug-in, so Homeshick can ignore it.

I have several repos in Homeshick control: general dot files, mac-specific files and scripts, and private files that hold secrets and keys.
If you want to check out this setup - look at [this shell script](https://git.io/all.files) that I use to install the files.

To be continued... (with encyption, keybase, upspin and other thoughts on dot files)