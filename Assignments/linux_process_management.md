# Linux Process Management 
### 1. Viewing All  process 
```
ps aux
```

##### This command  shows all process running on your system .

### explanation :
 a : Show processes for all users.

u : Display the user/owner of the process.

 x : Include processes not attached to a terminal (e.g., background or system services).
  ### Output :
  
<img width="1211" height="914" alt="image" src="https://github.com/user-attachments/assets/b785af8b-8f95-440e-ae8e-ad23b45cea08" />

  
## 2. process tree command 
  

  ```
pstree -p
``` 
#### This shows a tree-like hierarchy of all processes, starting from the init or systemd process (PID 1).
#### Output Example :

<img width="921" height="601" alt="image" src="https://github.com/user-attachments/assets/a8a1cc3a-483a-4017-b632-5a266d6dd0d8" />

#### Shows parent-child process relationship. 


## 3. Real-Time Monitoring command :

```
top
```

#### Explanation :
top command shows a live, updating list of processes, sorted by CPU usage by default. It helps you:

Monitor CPU, memory, and process usage

Identify resource hogs

Kill or manage processes interactively
#### Output :
<img width="1387" height="844" alt="image" src="https://github.com/user-attachments/assets/57e69b25-882a-480c-b8ec-ecc9a2be7e91" />


## 4. Adjust Process Priority 
## start a process with low priority :
```
nice -n 10 sleep 300 &
```

 ### explanation :
 nice: Runs a command with a modified priority (a “niceness” level).

-n 10: Sets the niceness value to +10, meaning the process will run with lower priority than the default (0).

sleep 300: The actual command being run — it just waits for 300 seconds (5 minutes) without doing anything.

&: Runs the command in the background, so your terminal remains usable.

### Change priority of running process :


```
renice -n -5 -p 3050
```

 ### Output :
 <img width="464" height="124" alt="image" src="https://github.com/user-attachments/assets/41c3e8ed-f060-4166-b060-07c9e20ef5c3" />

 
## 5. CPU Affinity (Bind process to CPU Core )
 ```
taskset -cp 3050
```

### Explanation:
taskset: Tool to view or set CPU affinity for a process — i.e., which CPUs a process is allowed to run on.

-c: Use CPU list format (e.g., 0,1, 0-3)

-p: Operate on an existing process

3050: The PID of the process you're querying or modifying
#### example output :
```
pid 3050's current affinity list: 0-3
````
##### This means the process can run on CPU cores 0, 1, 2, and 3

## 6. I/O Scheduling priority c
## Comand :
```
ionice -c 3 -p 3050
```
 ###### is used to set the I/O scheduling class of a process with PID 3050 to idle class using the ionice tool on Linux.
 #### Explanation : ionice: Tool to set or get the I/O scheduling class and priority of a process.

#### -c 3: Specifies the I/O scheduling class.

#### 3 = Idle class. The process only gets I/O time when no other process needs it.

#### -p 3050: Specifies the process ID (PID) of the target process. In this case, PID 3050.
 
 
 ### Output :<img width="510" height="333" alt="image" src="https://github.com/user-attachments/assets/edd9e2bb-18cd-41af-8be9-cbb2f4bab16b" />


 ## 7. File Descriptors Used by a process 
 ## command :
 ```
lsof -p 3050 | head -5
```

### Explanation :
lsof: Lists open files (everything is a file in Unix/Linux: files, sockets, pipes, etc.).

-p 3050: Filter results to only show those for PID 3050.

| head -5: Limit the output to the first 5 lines for readability.

 ### Example Output :
 ```COMMAND   PID USER   FD      TYPE             DEVICE  SIZE/OFF      NODE NAME
firefox  4321 user  cwd       DIR              8,1      4096     131072 /home/user
firefox  4321 user  rtd       DIR              8,1      4096          2 /
firefox  4321 user  txt       REG              8,1  52590496    3932161 /usr/lib/firefox/firefox
firefox  4321 user  mem       REG              8,1    476640    3932180 /usr/lib/libgtk-3.so.0.2404.16
```

#### explanation of output :
| Column     | Meaning                                                                |
| ---------- | ---------------------------------------------------------------------- |
| `COMMAND`  | Name of the command or executable                                      |
| `PID`      | Process ID                                                             |
| `USER`     | Username running the process                                           |
| `FD`       | File descriptor (e.g., `cwd` = current working dir, `txt` = text code) |
| `TYPE`     | Type of file (e.g., `DIR`, `REG`, `CHR`, etc.)                         |
| `DEVICE`   | Device identifier                                                      |
| `SIZE/OFF` | File size or offset                                                    |
| `NODE`     | Inode number                                                           |
| `NAME`     | Name of the file/path                                                  |


## 8. Trace System Calls of a process 
## Command :
```
strace -p 3050
```

### Explanation :
#### strace – A powerful diagnostic, debugging, and instructional tool that monitors system calls and signals used by a process.

#### -p 3050 – Tells strace to attach to the process with PID 3050 and start tracing it in real-time.


### output:
 <img width="902" height="428" alt="image" src="https://github.com/user-attachments/assets/c53471c2-85d0-4a6e-b61d-eb8dbce27057" />



 ## 9. Find process Using a port 
 ## Command :
 ```
sudo fuser -n tcp 8080
```
#### Explanation :
sudo – Run the command with superuser privileges (necessary for seeing all processes and ports).

fuser – A command-line tool to identify processes using files or sockets.

-n tcp – Tells fuser to operate in the network namespace and specifically look at TCP ports.

8080 – The port number you're interested in (commonly used by HTTP servers or proxies).
 
### Output:
<img width="1017" height="136" alt="image" src="https://github.com/user-attachments/assets/777d2376-3d57-4889-9456-ee553573f2e8" />



## 10. Per-Process Statistics 
## Command :
```
pidstat -p 3050 2 3
```

#### Explanation :
pidstat – Reports statistics for Linux tasks (processes), useful for analyzing CPU, memory, I/O usage, etc.

-p 3050 – Monitor only the process with PID 3050.

2 – Interval in seconds between reports.

3 – Number of reports (i.e., it will print 3 samples, 2 seconds apart).


#### Output :
<img width="1018" height="111" alt="image" src="https://github.com/user-attachments/assets/80a1f7fc-5200-4e8e-8630-613e37462bef" />

### Explanation:
| **Column** | **Meaning**                                                     |
| ---------- | --------------------------------------------------------------- |
| `UID`      | User ID who owns the process                                    |
| `PID`      | Process ID being monitored                                      |
| `%usr`     | CPU time spent in **user space** (non-kernel code)              |
| `%system`  | CPU time spent in **kernel space** (system calls, etc.)         |
| `%guest`   | CPU time used by guest OS (e.g. virtualized)                    |
| `%wait`    | Time the CPU was idle **while the process was waiting for I/O** |
| `%CPU`     | Total CPU usage by the process (`%usr` + `%system` + `%guest`)  |
| `CPU`      | The specific CPU core used                                      |
| `Command`  | Name of the process                                             |

## 11. Control Groups (cgroups) for Resource Limits Create a new cgroup:
```
sudo cgcreate -g cpu,memory:/testgroup
```

#### Explanation :
| **Part**                   | **Meaning**                                                                                      |
| -------------------------- | ------------------------------------------------------------------------------------------------ |
| `sudo`                     | Run as root (required for cgroup operations)                                                     |
| `cgcreate`                 | Command to create a new cgroup                                                                   |
| `-g cpu,memory:/testgroup` | Create the group under both the **CPU** and **Memory** controllers with the **name `testgroup`** 


# 🧠 12. Alternatives to nice / renice
 ### 1. chrt (Real-Time Scheduling) 
```
sudo chrt -f 50 sleep 1000
chrt -p <pid>
````


#### explanation :

    The command sudo chrt -f 50 sleep 1000 starts the sleep process with the FIFO (First-In-First-Out) scheduling policy and sets its priority to 50 (the range is usually 1 to 99, with higher being more urgent).

    The command chrt -p <pid> can be used to view or change the real-time attributes of an already running process.



### 2.ionice (I/O Priority Control) 

```
ionice -c 2 -n 7 tar -czf backup.tar.gz /home
````

#### explanation :
The ionice -c 2 -n 7 tar -czf backup.tar.gz /home command runs the backup process with a low disk I/O priority, ensuring it yields to more critical disk operations. It minimizes interference with other tasks by running the I/O in the "best-effort" class at the lowest priority level.

### output : <img width="308" height="678" alt="image" src="https://github.com/user-attachments/assets/1234a536-97fd-4f8f-b25b-87243ea2639e" />




### taskset (CPU Affinity)
```
taskset -c 1 firefox
````

#### explanation :
The taskset command sets or retrieves the CPU affinity of a process, which means binding the process to specific CPU cores. This helps improve performance by limiting where a process can run, making better use of CPU caches and reducing overhead from switching cores.
