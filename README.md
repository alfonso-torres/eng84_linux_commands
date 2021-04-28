# LINUX COMMANDS

[Link](http://permissions-calculator.org/) to check permissions.

Let's practice with some linux commands:

1. How to check Hidden Files and Directories.

`ls -al`

2. The Manual, Flags.

`man man`

3. What is a wildecards and How to use Wildcards.

A wildcard in Linux is a symbol or a set of symbols that stands in for other characters. It can be used to substitute for any other character or characters in a string. For example, you can use a wildcard to get a list of all files in a directory that begin with the letter O: `ls -l O*`

	- `*`: All files
	- `.`: Current folder
	- `..`: Up one folder

4. How can do you Process Management.

To find the process ID and parent process ID of the current shell, run:

- `echo $$`
- `echo $PPID`

Manage a running process: `ps`

Click on the [link](https://opensource.com/article/18/9/linux-commands-process-management) to have a look of the commands.

5. What is Currently Running on your system.

- `top`: task manager.
- `ps`: to lists running processes. Or `sudo ps -a`.
- - Use the following command to list Linux processes along with pid, user name, stat as follows: `ps -eo pid,user,stat,comm`.
- You can combine ps with grep command command as follows: `ps -eo pid,user,stat,comm | grep nginx`.

6. Killing a process/Crashed Process.

- `kill pid`: to kill a process based on its pid.

7. How to check any process running in the Foreground and Background Jobs.

- `sudo ps -aux | less`
- `ps aux | more`
- List your background processes: `jobs`.

8. How to stop/kill any process running in the Foregroung and Background Jobs.

- `kill pid`: to kill a process based on its pid. Take the pid from the previous command.

9. How to change permissions with chmod command.

- `chmod (+rwx | -rwx)`: to change permissions

    - `+ | -`: add or remove permission
    - `r`: read permission
    - `w`: write permission
    - `x`: execute permission
    - `777`: read, write and execute for everyone
    - `400`: same as 777 but only for the issuing user
    - `600`: same as 777 but only for the file owner and restricts all others

10. How to check permission for files/dir.

- `ll`: to check permissions

11. How to use head, tail, sort, nl (number line), wc (word count)

- `head`: prints first 10 lines of a file.
- `tail`: prints last 10 lines of a file.
- `sort`: sorts information in a file.
- `nl`: prints a file with numbered lines.
- `wc`: print out a word count.

12. What is piping and redirection, HINT > indicates to the command line.

Two such advantages are the use of pipes and redirection. With pipes and redirection, you can "chain" multiple programs to become extremely powerful commands. Most programs on the command-line accept different modes of operation. Many can read and write to files for data, and most can accept standard input or output. This means that you can direct the output of one program as input to another program. You can then take the output of the second program and redirect it as input to yet another program, or redirect the output to a file.

- For example, to redirect the output of the ps program to a file, use: `ps ax > output.txt`.
- If you wanted to merge two separate files together into a single file that already contains data, you could use the cat command and redirection: `cat 1.txt 2.txt >> 3.txt`.

Pipes work a little differently. When you use a pipe, the output of the command on the left of the pipe is redirected as input to the command on the right of the pipe. For instance, to find all sshd processes in a ps listing, you would use: `ps ax | grep sshd | grep -v grep`.

So:

- `cmd 1 | cmd 2`: Use command 1 and use that output as input for command 2.
- `cmd > file`: redirect output into a file and overwrite the contents.
- `cmd >> file`: redirect output into a file and append it to the end.

13. What is STDIN standard input and output.

The standard input device, also referred to as stdin, is the device from which input to the system is taken. Typically this is the keyboard, but you can specify that input is to come from a serial port or a disk file, for example. The standard output device, also referred to as stdout, is the device to which output from the system is sent. Typically this is a display, but you can redirect output to a serial port or a file.

- The file descriptor for standard input is 0 (zero).
- The file descriptor for standard output is 1 (one).

__Extra commands:__

- `apt (install | remove)`: Package manager
- `nano name_file`: text editor.
- `touch name_file`: makefile.
- `cd ..`: up a dir.
- `pwd`: print working directory.
- `mv`: move also used to rename.
- `cp`: copy.
- `rm`: remove.
- `sudo systemctl (status | start | stop | restart)`: Manage background services.
- Transfer files to the instance: `scp -ri ~/.ssh/.pem /file_to_transfer ubuntu@<ip>:~/location`.
Proxy SSH into our private network: `ssh -i ~/.ssh/local.pem -o ProxyCommand="ssh -i ~/.ssh/local.pem -W %h:%p ubuntu@app_ip" ubuntu@db_private_ip`.
- who am I `uname`.
- list dir `ls` list all dir `ls -a`.
- make Dir `mkdir`.
- create file `nano file_name`.
- `sudo` used to run commands as an admin.
- `sudo su` to go into admin mode.
- to go back a dir from current location `cd ..`.
- Where am I `pwd`.
- update command `sudo apt-get update -y`.
- upgrade command `sudo apt-get upgrade -y`.
- `clear` to clear screen/terminal.
- renaming the README `mv README.md MYREADME.md
`.
- copy our README file from current location to devops folder `cp MYREADME.md devops/MYREADME.md
`. Need to entiry the whole path.
- detele a file `rm name_of_the_file`.
- move file with mv command is to change the path `mv MYREADME.md devops/
`
- nano provision.sh, and inside:

````bash
#!/bin/bash

sudo apt-get update -y
````

Click on the [link](https://ubuntu.com/tutorials/command-line-for-beginners#1-overview) to follow a guide of using command line in linux.
