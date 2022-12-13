# Linux_namepsaces

**Namespaces in Linux:**

- Linux namepsace refers to feature of linux that partitions kernal resources.
- A namespace consists of one or more process + set of resources
- Resource can exists in multple namepsaces.
- Namrespaces are fundamental aspects of containers in linux.

**Why does Linux needs namespaces?**

- The main purpose is to wrap some global resources in an abstraction so that it appears to the process it has its own isolated world from the rest of the processes running next to it.
- The procress has no idea its running under one, it only knows about resources (CPU,Memory,Disk) given to it.

Types of namespaces:

- control group(cgroup) : 
  The cgroup namespace is used by containers to isolate a set of processes into a virtual system at a OS level.
  cgroup limits, isolates and measures reources usage of a group of processes.
  cgroups can have there own set of quotas for memory,CPU,Network and I/O.
  
- Interprocess Communication (IPC)
- Mount (mnt)
- Network (net)
- Process ID (pid)
- Time (time)
- User
- UNIX Time Sharing (uts)
