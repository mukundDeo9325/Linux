```
For everything that happens on a Linux server, a process is started. For that reason, process
management is among the key skills that an administrator has to master. To do this efficiently, it is
important to know which type of process you are dealing with.
A major distinction can be made between two process types:
■ Shell jobs are commands started from the command line. They are associated with the shell
that was current when the process was started. Shell jobs are also referred to as interactive
processes.
■ Daemons are processes that provide services. They normally are started when a computer
is booted and often (but certainly not in all cases) they are running with root privileges.




Understanding Processes and Threads
Tasks on Linux are typically started as processes. One process can start several worker threads.
Working with threads makes sense, because if the process is very busy, the threads can be handled by
different CPUs or CPU cores available in the machine. As a Linux administrator, you cannot manage
individual threads; you can manage processes, though. It is the programmer of the multithreaded
application that has to define how threads relate to one another.
```

<img width="610" height="95" alt="Screenshot 2026-08-05 at 1 13 34 AM" src="https://github.com/user-attachments/assets/290fc6fb-93ae-4cbe-a736-a22a2beee739" />

<img width="616" height="253" alt="Screenshot 2026-08-05 at 1 13 59 AM" src="https://github.com/user-attachments/assets/ef8491f5-0908-40a3-904b-3303494cf59b" />

```
Adjusting Process Priority with nice
When Linux processes are started, they are started with a specific priority. By default, all
regular processes are equal and are started with the same priority, which is the priority number 20. In
some cases, it is useful to change the default priority that was assigned to the process when it was
started. You can do that using the nice and renice commands. Changing process priority may make
sense in two different scenarios.

Example: that you are about to start a backup job that does not necessarily have to finish fast.
Typically, backup jobs are rather resource intensive, so you might want to start it in a way that it is not
annoying other users too much, by lowering its priority.

Another example is where you are about to start a very important calculation job. To ensure
that it is handled as fast as possible, you might want to give it an increased priority, taking away CPU
time from other processes. When using nice or renice to adjust process priority, you can select from
values ranging from -20 to 19.

Sending Signals to Processes with kill, killall, and pkill
The Linux kernel allows many signals to be sent to processes. Use man 7 signals for a complete
overview of all the available signals. Three of these signals work for all processes:
 The signal SIGTERM (15) is used to ask a process to stop.
 The signal SIGKILL (9) is used to force a process to stop.
 The SIGHUP (1) signal is used to hang up a process. The effect is that the process will
reread its configuration files, which makes this a useful signal to use after making
modifications to a process configuration file.
To send a signal to a process, the kill command is used. The most common use is the need
to stop a process, which you can do by using the kill command followed by the PID of the process.
This sends the SIGTERM signal to the process, which normally causes the process to cease its activity.
Sometimes the kill command does not work because the process you want to kill is busy. In
that case, you can use kill -9 to send the SIGKILL signal to the process.
Because the SIGKILL signal cannot be ignored, it forces the process to stop, but you also risk
losing data while using this command. In general, it is a bad idea to use kill -9 because,
 You risk losing data.
 Your system may become unstable if other processes depend on the process you have just
killed.
Sending signal using kill command,


```
```
Controlling Jobs
A job is a process that the shell manages. Each job is assigned a sequential job ID. Because a job is a
process, each job has an associated PID. There are three types of job statuses:
 Foreground: When you enter a command in a terminal window, the command occupies that
terminal window until it completes. This is a foreground job.
 Background: When you enter an ampersand (&) symbol at the end of a command line, the
command runs without occupying the terminal window. The shell prompt is displayed
immediately after you press Return. This is an example of a background job.
 Stopped: If you press Control + Z for a foreground job, or enter the stop command for a
background job, the job stops. This job is called a stopped job.



Killing Processes
Usually, a process terminates on its own when they’re done with their task, or when you ask
them to quit. However, sometimes a process can hang up or consume a lot of CPU or RAM. In this
situation, you would want to manually “kill” the process. In order to kill a process, you should first
locate the details of the process. You can do this through following commands:
top, ps, pidof and pgrep.
(We had already seen how to get details of processes using top and ps command in this chapter.)
Getting process details using pgrep,
pgrep command searches for processes currently running on the system, based on a
complete or partial process name, or other specified attributes.


pidof command searches processes currently running on system. This command is similar to
pgrep command but it shows process id only.

Getting process details using pstree and pidstat
pstree command is similar to ps command but instead of showing detailed information,
pstree command shows processes in tree structure. Pstree command followed by user name
will give process tree generated from that particular user.
pidstat command is used for monitoring individual tasks currently being managed by the
Linux kernel. It writes to standard output activities for every task managed by the Linux kernel.
The pidstat command can also be used for monitoring the child processes of selected tasks.
The interval parameter specifies the amount of time in seconds between each report.
```

<img width="616" height="135" alt="Screenshot 2026-08-05 at 1 17 01 AM" src="https://github.com/user-attachments/assets/6912f077-fb70-4e38-bda1-3296aa646a1b" />






