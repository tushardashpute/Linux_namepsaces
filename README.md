# Linux_namepsaces

**Namespaces in Linux:**

- Linux namepsace refers to feature of linux that partitions kernal resources.
- A namespace consists of one or more process + set of resources
- Resource can exists in multple namepsaces.
- Namrespaces are fundamental aspects of containers in linux.

**Why does Linux needs namespaces?**

- The main purpose is to wrap some global resources in an abstraction so that it appears to the process it has its own isolated world from the rest of the processes running next to it.
- The procress has no idea its running under one, it only knows about resources (CPU,Memory,Disk) given to it.

**Types of namespaces:**

- control group(cgroup): 
  
  - The cgroup namespace is used by containers to isolate a set of processes into a virtual system at a OS level.
  - cgroup limits, isolates and measures reources usage of a group of processes.
  - cgroups can have there own set of quotas for memory,CPU,Network and I/O.
  
- Interprocess Communication (IPC)
  - IPC is more a security oriented namespaces.
  - IPC is used to isolated inter-process communications so they can not accidentally accessed, or destroyed by another process which doesn’t have permission to use it.
  
- Mount (mnt)
  - A mount namespace allows different veiws of the filesystem hierarchy.Anytime you are using mount or umount commance you are managing the mount namespace.

- Network (net)
  - A network namepsace provides isolation of the system resources associated with teh networking.
  - Each namepsace has its own network device, IP address, IP routing tables, Port numbers etc
  - The network namspace also provices additional features to containers by creating a virtual network devices which are assigned to specifice container.
  - This is how docker can have multiple containers running each internally with a web-server assigned to port 80. 

- Process ID (pid)
  - Isoalated process by assigning different Pid's to processes executing each get's its own PID
  - PID's are hierarchical every PID has a parent which nests from PID=1 
  - This allows signal like the kill command to target a specific instance of a process.

- Time (time)
  - This is used by containers to allow them to set their data/time to be different from the main system and from each other,
 
- User
  - User namepsace isolated User and group ID number spaces from each other
  - User namepsaces can be netsted : Allows a unpriv user to own the outer namespace, while granting root(priv access to internal ns)

- UNIX Time Sharing (uts)
  - UTS is used to isolate two system identifiers (nodename or hostnames) and domainname from one another
  - It is the UTS namepsace hwich allows containers to have their own hostname and domainname
 
<img width="467" alt="image" src="https://user-images.githubusercontent.com/74225291/207245242-4c4c4af4-35e1-43ae-b20c-2d3f878ebc03.png">

