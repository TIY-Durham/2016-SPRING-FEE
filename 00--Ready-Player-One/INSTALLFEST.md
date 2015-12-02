Ready to be a developer? It's dangerous to go alone... Take these!

1. [Install XCode](#step-1-install-xcode)
  1. Install XCode CLI Tools via `Terminal.app`
  1. Configure `Terminal.app`
1. [Install Homebrew](#step-2-install-homebrew)
  1. Run the install script...
  1. Confirm that the `brew` command exists with `which brew`
  1. Run `brew doctor` to ensure everything works!
  1. Call for help if it doesn't!
1. [Use `brew install`...](#step-3-use-brew-install)
  * `git`
  * `tree`
  * `zsh`
  * `node`
  * `ruby`
1. [Configure `git`](#step-4-configure-git):
  1. your name and email address
  1. where to store your password
  1. which editor to use: Atom!

## Step 1: [Install XCode](https://developer.apple.com/xcode/download/)

Don't bother installing the absolute latest version; just install what's available in the App Store. You'll find that you need to create an Apple Developer account (which is free) to download and install XCode, which is kind of a bummer. After you've downloaded XCode, we'll need to install the XCode Command Line Tools package.

### Step 1a: [Install XCode CLI Tools](https://developer.apple.com/library/ios/technotes/tn2339/_index.html)

Once you have XCode installed, open `Terminal.app`, which will present you with a mostly empty white screen with some black text inside of it. **Don't Panic.** This is a [terminal emulation window](https://en.m.wikipedia.org/wiki/Terminal_emulator) that mimics [the earliest types of computer interfaces](https://en.m.wikipedia.org/wiki/Text_user_interface), which turn out to be [more efficient for programmers than GUIs](https://en.m.wikipedia.org/wiki/Graphical_user_interface#Command-line_interfaces).

_If you need some more exposure to the CLI, head to [the CLI Crash Course](README.md#cli-crash-course) first._

In CLI documentation whenever you see a box that contains code-formatted text that start with the symbols `$>`, you're probably looking at a command that you should type into the CLI. To install the XCode CLI Tools then, we'll use the `xcode-select` command:

    $> xcode-select --install

This will _open a separate dialog window_ to ask for your authorization to install some commands into a _hidden location on your computer_. No worries, though, as your "command shell" running inside of `Terminal.app` knows how to find those hidden things. This little white box (soon to be black) is your first step into wizardry.

### Step 1b: Configure Terminal to become a PRO!

If you open the **Preferences** pane, by pressing **&#8984;+,** on your keyboard (PS: that works for basically every application on a Mac), you'll see a number of **Profiles** available. These are essentually themes for the base colors in your command line windows. Play around with some of these themes, and select one as the default (there's a button for that). The darker themes are easier on the eyes.

## Step 2: [Install Homebrew](http://brew.sh/#install)

Programming, like wizardry, is full of obscure incantations that we find and use without fully understanding them first. Installing the Homebrew package manager is one of those incantations. [Read up on Homebrew and what it does](https://git.io/brew-docs), but [be sure to install it](http://brew.sh/#install) _only after installing XCode CLI Tools_. Homebrew _needs_ those tools to do its job. They're like prerequisites for a course in college or essential paperwork for a visa application. They're called _dependencies_; you'll find that word in software _a lot_.

### Step 2a: Run the install script...

Just drop [the copy-pasta](http://brew.sh/#install) directly into a fresh `Terminal.app` window and follow the prompts. In the event that you run into an error, skip ahead to **Step 2d**.

### Step 2b: Confirm that Homebrew is installed...

There are a couple of ways to do that. First, you can [check that any command exists with the `which` command](https://en.m.wikipedia.org/wiki/Which_(Unix)). It's a command that tells you where other commands are installed. Check that Homebrew installed the `brew` command; `which` _should_ produce the following response:

    $> which brew
    /usr/local/bin/brew

If you get something _different_, you might not have installed _something_ -- XCode or the XCode CLI tools or even Homebrew itself -- correctly. Skip ahead to **Step 2d** for help.

### Step 2c: And that it works correctly...

Tell Homebrew to give itself a checkup with:

    $> brew doctor

### Step 2d: Keep Calm and File a Bug Report

So you installed something incorrectly or your copy-pasta missed some characters? Try again, and pay careful attention to any error messages. Do some research on the issue, starting with the error message and the circumstatnces and document your debugging process in your _WIP Issue_. When you get stuck, [**@-mention** your instructors on your _WIP Issue_](https://help.github.com/articles/writing-on-github/#name-and-team-mentions-autocomplete) to summon us for help, which also sends us email.

Chances are high that you _won't_ encounter difficulty, but if you do, you can [_uninstall Homebrew_](https://github.com/Homebrew/homebrew/blob/master/share/doc/homebrew/FAQ.md#how-do-i-uninstall-homebrew) and start over from there. Once we get Homebrew installed correctly, though, you'll probably _never uninstall and reinstall Homebrew again_. You'll update and upgrade, just like any other application.

## Step 3: Use `brew install`...

[Like the documentation says](https://git.io/brew-docs), Homebrew is a [**Package Manager**](https://en.m.wikipedia.org/wiki/Package_manager): a program that installs _other_ programs. It's like the App Store for CLI tools. Now that we've got the `brew` command, we can use it to install some _other_ commands that we'll need over the course. Install the following with `brew install`:

* `git`
* `zsh`
* `tree`
* `node`
* `ruby`

Test that each of these is installed correctly by running `which` on each of them, just like we did for `brew`. You should get ouput that starts with `/usr/local/bin/` and ends with the command name, e.g. `/usr/local/bin/git`. Finally, run `brew list` and [take a screenshot](https://support.apple.com/en-us/HT201361) of the result, which should list all of those _packages_ we just installed. Attach that screenshot to your _WIP Issue_.

## Step 4: Configure `git`...

Now that we have `git` installed via `brew` -- _XCode actually installs its own version that we have no ability to upgrade; boo, Apple_ -- we should tell `git` all about us, so it can tell GitHub who we are when we start using it. Let's [use the `git` command to configure `git`](http://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration)!

### 1a. Tell `git` your name and email address...

The first thing `git` needs to know is _who you are_ and _how to identify you_, which it does with two configuration settings: `user.name` and `user.email`. Set those with the `git` command:

    $> git config --global user.name "YOUR NAME"
    $> git config --global user.email "YOUR-EMAIL@EXAMPLE.COM"

This tells `git` to attach `YOUR NAME` and `YOUR-EMAIL@EXAMPLE.COM` to all your work on your computer. Well, that's _almost_ right. Run those commands again, replacing `YOUR NAME` with your real name, the same one [you added to your GitHub account](README.md#github-ing-to-know-you). Do the same with your _real_ email address. To confirm, simply run:

    $> git config --global --get-regexp user

If you don't see what you expected, try again. If you run into an error message along the lines of `Fatal: Not a git respository`, you probably omitted the `--global` flag.

### 1b. Tell `git` where to store your password...

When we start using `git` to send code to GitHub, you'll have to identify yourself to GitHub with the username and password you used when you created your account. Having to type that a lot can be very tedious (but occasionally helpful!), so let's tell `git` how to keep your password around securely:

    $> git config --global credential.helper osxkeychain

Mac OS X includes [a secure password manager called `Keychain.app`](https://en.wikipedia.org/wiki/Keychain_(software)) that `git` can use to store your password and send it to GitHub for you.

### 1c. Tell `git` which editor to use...

So `git` is a Command Line Interface (CLI), right? On its own, `git` doesn't know anything about GUI tools like Atom, so when it needs you to write a long message or edit a file, it opens up a CLI editing tool like `vim` or `nano`... at least by default. Let's tell it about our new friend Atom, though, since we're going to be spending so much time there:

    $> git config --global core.editor "atom -w"

Don't forget the quotes! Like before, we can check all of these setting by using `git config` again. This time, we'll look at _the whole list_:

    $> git config --global --list

Make sure your changes are in there: `user.name`, `user.email`, `credential.helper`, and `core.editor`...! To test that our editor is setup correctly, we can just ask `git` to open [the global configuration file](http://git-scm.com/docs/git-config#FILES) in Atom:

    $> git config --global --edit

If that _doesn't_ open a rather strange looking file in Atom (be patient, it can take a few seconds), _Don't Panic!_ If you're in `nano` (the name `nano` will appear in the top bar), press `^X` (that's the `control` key plus the `X` key) to quit. If you're in `vi` or `vim` (basically a screen full of text), press `ZZ` (that's `shift` plus the `Z` key twice).

Welcome to Atom and the _other_ way to configure `git`! The file you're looking at is [a hidden file](https://en.wikipedia.org/wiki/Hidden_file_and_hidden_directory) named `.gitconfig` that lives in [your home directory](https://en.wikipedia.org/wiki/Home_directory). If you [open your Home folder in Finder](https://support.apple.com/kb/PH22031?locale=en_US&viewlocale=en_US), you won't see it -- because it's _hidden_ -- but the file is still there.

You can poke around with your `.gitconfig` file if you want, but make sure that the settings we configured are correct before you save and close. You're ready to [install and configure Prezto](PREZTO.md) next, which will involve poking around some _more_ of those hidden files with Atom!

## One Final Warning

Please adhere to these instructions when installing these tools on your Mac. _Please do not install `node` by any other means!_ There are all kinds of instructions and tutorials out there for how to install this software on your Mac, some of which are outdated and don't account for a nice, sane package manager like Homebrew. While it's important to know that _nothing you can do will irrevocably harm your computer_, there are [some trolls on the internet](https://en.m.wikipedia.org/wiki/Internet_troll) who will try to ruin your day with certain evil incantations that will not be repeated here. _Stay on the yellow brick road, Dorothy!_

In general, _you should avoid executing commands that include `sudo`_ until you really [understand what it does](https://en.m.wikipedia.org/wiki/Sudo) and [when to use it](http://www.techrepublic.com/blog/linux-and-open-source/do-you-sudo-learn-the-basics/). That probably won't be you for a while, so avoiding `sudo` is a Good Idea for now.
