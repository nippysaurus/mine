# mine

Configure your machine by running scripts and linking files.

# installation

```
curl -sL "https://raw.githubusercontent.com/nippysaurus/mine/master/mine" > /usr/local/bin/mine
```

You should now be able to run `mine` from anywhere.

# usage

Running `mine` will load configuration files from the default location (`~/.mine`), run all the scripts and link all the files (read more about how this works in the config section).

`mine edit` will open the configuration directory with your default editor.

# config

`mine` basically operates by traversing the config directory and:
 - executing all executable files
 - collating and linking all non executable files

Directories and files are ordered using `sort`, so prepending `[0-9]_` allows the ordering to be manipulated.

Value substitution for non-executable files can be acheived by creating a file with the same name and `.sed` appended. This will be supplied to `sed -f` during processing.

The following is an example config layout:

```
~/.mine
  /0_git
    /install
    /.gitconfig.sed
    /.gitconfig
```
