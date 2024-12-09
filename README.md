Introduction:
This project involves creating a micro-shell called enseash, which lets users run commands interactively and displays information about their execution.
The project is divided into several steps, with each feature to be developed sequentially.
The goal of this project is to understand the basic operations of a shell, such as displaying a prompt, reading user input, executing system commands, and handling simple interactions with the operating system.

Question 1 :
Here we display a welcome message and a prompt "enseash %" in the console using the write() function, which directly outputs to the standard output (stdout). It simulates a basic shell environment by showing a message instructing the user how to exit and a prompt for user input. However, the code doesn't include functionality to read or process user input yet, making it a simple shell-like interface without interactive command handling.

Question 2:
The code here implements a basic shell that reads a user command, executes it, and returns to the prompt. It reads input using read(), creates a child process with fork(), and executes the command using execlp().The fork() call creates a new child process to run the command entered by the user.The parent process waits for the child process to complete using wait(), ensuring the parent doesn't continue until the command has finished executing.
The loop continues, displaying the prompt after each command execution, enabling a REPL (Read-Eval-Print Loop) behavior.


Question 3:
The program simulates a basic shell that reads user input, executes commands, and handles exit conditions. It uses fork() to create a child process for executing commands, and execlp() to run the command in the child process. If the user types "exit" or presses <Ctrl>D, the shell prints "Bye bye..." and exits. The parent process waits for the child to finish using wait().

Question 4:
The shell displays the exit status or signal of the last command in the prompt. If the command runs successfully, it shows exit:0, indicating no errors. If the command is terminated by a signal, such as a forceful stop, it shows sign:9, which represents the signal that caused the termination. This gives feedback about whether the command completed normally or was interrupted.
In our code, we'll use the sys/wait.h header to access macros that help us check the exit status or signal of a child process, allowing us to handle and display whether the process terminated normally or was interrupted by a signal. 
We will use 2 separate fiel to test our exit, provided in git. A first one to test and see a segmentation default and a second file that will put the value of exit at 58

Question 5:
The duration method measures how long a command takes to execute. It records the start and end times using clock_gettime(). The difference between the start and end times is calculated in seconds and nanoseconds, then converted into milliseconds. Finally, the program displays the execution time along with the command's exit status.


Question 6:
In this part, we will use excpl with arguments to display for exemple hostnam -i. It reads the input, splits it into the command and its arguments, and then creates a child process to execute the command. The shell measures how long the command takes to run and displays the exit status or signal along with the execution time. If the command is not found, it shows an error message. The shell continues to run until the user types "exit" or presses Ctrl+D.

Conclusion:
In conclusion, the enseash works by displaying prompts, executing commands, and tracking execution status. It uses fork(), execlp(), and wait() to run commands in a child process, measure execution time, and display exit statuses. The project provides a solid understanding of shell operations and system-level programming.
