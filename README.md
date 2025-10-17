# BASH FILES

## interactive login shell

When invoked as an interactive login shell:

1. `/etc/profile`

If the file exists, it runs the commands listed in the file. Then Bash looks for

- `~/.bash_profile`
- `~/.bash_login`
- `~/.profile`

... in the listed order, and executes commands from the first readable file found.

Typically, `~/.bash_profile` contains lines like below that source the .bashrc file. 
This means each time you log in to the terminal, both files are read and executed.

```sh
if [ -f ~/.bashrc ]; then
	. ~/.bashrc
fi
```

## interactive non-login shell

When Bash is invoked as an interactive non-login shell, it reads and executes commands from:
- `~/.bashrc`

## reasoning

Use `.bash_profile` to run commands that should **run only once**, such as 
- customizing $PATH

Use `.bashrc` for everything that should run every time you launch a new shell. This includes 
- aliases
- functions
- custom prompts
- history customizations
