- Linux OS follows a layered design:
- **Hardware → Kernel → User Space**
- Kernel is the core component that controls the system
- User space contains applications and utilities
- Init system is responsible for starting services
---

## **Kernel**
- Runs in **kernel space** with full privileges
- Manages CPU scheduling, memory, devices, and filesystems
- Provides system calls for user-space programs
- Only layer that communicates directly with hardware

---## **User Space**
- Runs in **user space** with restricted privileges
- Includes shells, commands, applications, and daemons
- Cannot access hardware directly
- Failure of a user-space process does not crash the OS

**Process Creation & Management**

New processes are created using fork()
Child process is a copy of the parent

exec() replaces the process image with a new program

**Kernel assigns**:

PID, memory space, file descriptors

What systemd Does (and Why It Matters)

Starts the system and launches services

**Manages:**

Services (.service)
Timers (cron replacement)
Mounts, sockets, targets
Handles dependencies and parallel startup
Enables easy control:
systemctl start|stop|status


**Process State**

Running (R) – Executing on CPU
Sleeping (S) – Waiting for I/O or event
Uninterruptible Sleep (D) – Waiting on disk I/O
Stopped (T) – Paused (e.g., via Ctrl+Z)
Zombie (Z) – Finished execution but not reaped by parent

**dig**

Advanced DNS queries (better than nslookup)

**ss**

Modern replacement for netstat

Fast socket and network inspection

**lsof**

See which process is using a file or port

**strace**

Debug what a program is doing at the syscall level

**watch**

Run a command repeatedly and see live changes

Example: watch df -h

Scheduler decides when and how long a process runs
