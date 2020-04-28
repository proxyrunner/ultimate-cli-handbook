# Shells


You can type the following command in your terminal to see which shell you are using:

```
echo $0
```

The result will look something similar to the below if you are using the bash (Bourne Again Shell) terminal:

```
-bash
```

## As of recent: 

The default interactive shell is now zsh.
To update your account to use zsh, please run:

```
chsh -s /bin/zsh
```

## Deeper dive


To find the shell you have on the default environment you can check the value of the SHELL environment variable:

```
echo $SHELL
```

To find the current shell instance, look for the process (shell) having the PID of the current shell instance.

To find the PID of the current instance of shell:

```
echo "$$"
```

Now to find the process having the PID:

```
ps -p <PID>
```

Putting it together:

```
ps -p "$$"
```
