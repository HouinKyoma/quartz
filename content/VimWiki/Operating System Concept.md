# Operating System Concept Index
### Operating System Services
- User Interface
- Progaram execution
- I/O 
- File-system maniputlation
- communication
- error detection
== for ensuring efficient operation
- resource allocation
- accounting-usage statics
- protection and security
### User and Operating-System Interface
#### Command Interpreters
- Main function is to get and execute the next user command
#### GUI

### System Calls
System calls provide an interface to the services made available by OS
- generally they are routines written in C or C++
- How are System Calls used:
	- Through API, this way is less complex and less likely to mess up
	- A simple copying of a file A to file B can make many syscall
	- For UNIX-like system, the library is called **libc**

##### Ways of passing parameters to the OS
- registers
- Stored in memory and pass the address
- place on the stack and pop by the OS
- The latter two does not limit the size of parameters

### Types of System Calls
#### Process Control
- end() abort() to terminate current process
	- deterimine error level etc.
- load() execute()
	- a process may want to execute another program
- create process, terminate process
- get process attributes, set process attributes
- wait for time
- wait event, signal event
- allocate and free memory
#### File Management
- create file, delete file
- open close
- read write repostion
- get file attributes, set file attributes
#### Device Management
- request device, release device
- read, write, reposition
- get device attributes, set device attributes
- logically attach or detach devices
#### Information Maintenance
- get time or dtate, set time or date
- get system data, set system data
- get process, file, or device attributes
- set process, file, or device attributes
#### Communications
- create, delete communications connection
- send receive messages
- transfer status information
- attach or detach remote devices
