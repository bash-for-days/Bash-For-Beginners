### Running Bash Commands in the Background

To push a command to the background use “&” at the end of your command. Using “&” pushes your command into the background so you can continue using a terminal.

Here is an example using the “update” command followed by the “&” command.

	#!/bin/bash/
	sudo apt-get update -y &

### View Commands Running in the Background

To view commands running in the background use the “jobs” command.

	#!/bin/bash/
	sudo apt-get update -y &

And then:

	jobs


To continue running a command after you exit the terminal window use “disown” after. Here is an example using disown:

![](images/bash-background-disown-jobs.jpg)

Adding “&” at the end of a command will push a command into the background, but as a result the background command will continue to print messages into the terminal as you’re using it. 
If you’re looking to prevent this, consider redirecting the command to:

	#!/bin/bash/
	apt-get update -y &>dev/null &

This command will still end at the close of the terminal.

![](/images/bash-background-dev-null-e1459219851329.jpg)

### Make Commands Run Persistently in the Background 

To make a command run in the background as a dameon, remove its output from the terminal, and make it persistent after the terminal exits you can use the following in the terminal.

	#!/bin/bash
	nohup [command] &>/dev/null &

![](/images/bash-background-no-hup-e1459220107918.png)

That’s it! Now you can run commands in the background within the terminal, hide their output, and continue running them after the terminal session had ended. 


