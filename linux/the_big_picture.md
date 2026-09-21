# The Big Picture
## Levels and layers of abstraction in a linux system
The user processes - The kernel - The hardware

The kernel is the core of the  Operating System (OS), it resides in the memory and acts as a bridge between user processes and the hardware
It manages tasks in four general system areas.
- Process Management
- Memory Management
- Device drivers
- Systems calls & support

## Process Management
 - It is responsible for context switching (multitasking).
 - Creating time slices for user processes to utilize the CPU.
this is important because it tells us WHEN the kernel runs, which is between the time slices, the CPU switches in and out of kernel mode between the time slices
the kernel is responsible for capturing the state of user processes (in bits) and storing this data whenever it peforms a context switch.

## Memory Management
 - The kernel must have its own private memory (this is presumably also where it stores process states).
 - All running user processes must also be allocated private memory by the kernel (so that no user process may accidentally or maliciously interfere with the operation of another).
 - Memory may be shared by user processes (facilitated by the kernel).

VIRTUAL MEMORY? 

## Device Drivers & Management
 - A device is only accessible in kernel mode (I presume this means that only inbetween time slices -i.e when the CPU is in kernel mode, may the kernel send and recieve data to and from devices, this only makes sense as user processes have no direct access to hardware)
   DOES THIS MEAN THAT THE KERNEL CAN ACTUALLY MULTITASK? because in a fraction of a second it has to facilitate process management, memory management & othe operation of device drivers, or is it just one task between each time slices -this feels more sensible but then again rather slow, given the large volume of functions-

## System Calls & Support
 - sorry what now?
The official way a user program asks the kernel to do something privileged.
 - usually something the process either cannot or would rather not do.

### Two Very Important System Calls
- fork() - the kernel creates an almost identical copy of the user process.
- exec() - when the process calls exec(program), the kernel loads and starts the program, replacing the process itself.

## Pseudodevices
### What they are
User process level programs that behave like hardware devices
my favourite pseudodevice is /dev/random, I am fascinated by how it utilizes the entropy from the real world to create true disorder and randomness, something that computers are, on their own (as I understand them) incapable of doing.

### Examples
/dev/random.

### Why do they exist?
They have a broad variety of essential utilities, such as the aforementioned random found in the /dev directory.

### Questions I Still Have
How many of these devices exist in a standard linux system?

### Things that surprised me
The extent to which computers go in order to generate randomness. But this is completely understandable from a security standpoint.

## User Space
What is it?
Basically userland where user processes run. It includes everything that the user interacts with on a day-to-day basis.

### Why does it exist?
It exists so that the user can be able to use the operating system.

### Example
An example of this is the bourne again shell (bash) and all the programs associated therewith.

### Questions I still have
Does userspace also include the other directories that the user can access or is it just limited to the home directory where such a user is the judge, jury and executioner. Which begs another question, if the former is the case, then is the whole system superuser (#) space?

### Things that surprised me
The fact that a single system can have up to multiple users.


## Users
A user is an entity that can run processes and own files.
they could be known by a username, e.g lordkiller83 (me), but the kernel uses simple numeric identifiers called UserIDs instead.
A linux system often has more than one user.
Every process has an owner, and such an owner may terminate or otherwise modify their processes, but may not do the same to the processes of other users
The exception to this rule is the root, the SUPERUSER (#).

Groups are a set of users, main purpose is file sharing (users can control who can read (r), write (w) or execute (x) their files).

