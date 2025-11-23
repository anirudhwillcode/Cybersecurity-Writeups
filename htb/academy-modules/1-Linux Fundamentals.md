# Linux Fundamentals

## > Cheat Sheet

| Command / Syntax        | Description                                       |
|-------------------------|---------------------------------------------------|
| man <tool>              | Opens man pages for the specified tool            |
| <tool> -h               | Prints the tool's help page                       |
| apropos <keyword>       | Searches man page descriptions                    |
| cat                     | Concatenate and print files                       |
| whoami                  | Displays current username                         |
| id                      | Shows user identity                               |
| hostname                | Prints/sets system hostname                       |
| uname                   | Prints OS information                             |
| pwd                     | Prints working directory                          |
| ifconfig                | View/set network interface address                |
| ip                      | Manage routing, devices, tunnels                  |
| netstat                 | Shows network status (legacy)                     |
| ss                      | Investigate sockets                               |
| ps                      | Shows process status                              |
| who                     | Shows logged-in users                             |
| env                     | Prints environment variables                      |
| lsblk                   | Lists block devices                               |
| lsusb                   | Lists USB devices                                 |
| lsof                    | Lists opened files                                |
| lspci                   | Lists PCI devices                                 |
| sudo                    | Run command as another user                       |
| su                      | Switch user                                       |
| useradd                 | Create new user                                   |
| userdel                 | Delete user                                       |
| usermod                 | Modify user                                       |
| addgroup                | Add new group                                     |
| delgroup                | Remove group                                      |
| passwd                  | Change user password                              |
| dpkg                    | Manage Debian packages                            |
| apt                     | Package manager                                   |
| aptitude                | Alternative to apt                                |
| snap                    | Manage snap packages                              |
| gem                     | Ruby package manager                              |
| pip                     | Python package manager                            |
| git                     | Version control                                   |
| systemctl               | Manage systemd services                           |
| journalctl              | Query system logs                                 |
| kill                    | Send signal to process                            |
| bg                      | Background a job                                  |
| jobs                    | List background jobs                              |
| fg                      | Foreground a job                                  |
| curl                    | Transfer data from/to server                      |
| wget                    | Download from web                                 |
| python3 -m http.server  | Start web server on port 8000                     |
| ls                      | List directory contents                           |
| cd                      | Change directory                                  |
| clear                   | Clear screen                                      |
| touch                   | Create file                                       |
| mkdir                   | Create directory                                  |
| tree                    | Recursive directory listing                       |
| mv                      | Move/rename files                                 |
| cp                      | Copy files                                        |
| nano                    | Terminal editor                                   |
| which                   | Show command path                                 |
| find                    | Search files                                      |
| updatedb                | Update locate DB                                  |
| locate                  | Search via locate DB                              |
| more                    | Basic pager                                       |
| less                    | Advanced pager                                    |
| head                    | First 10 lines of file                            |
| tail                    | Last 10 lines of file                             |
| sort                    | Sort input                                        |
| grep                    | Pattern search                                    |
| cut                     | Extract sections of lines                         |
| tr                      | Replace characters                                |
| column                  | Format into columns                               |
| awk                     | Text processing                                   |
| sed                     | Stream editor                                     |
| wc                      | Count lines/words/bytes                           |
| chmod                   | Change permissions                                |
| chown                   | Change file owner/group                           |



## File System Management

Managing file systems on Linux is a crucial task that involves organizing, storing, and maintaining data on a disk or other storage device. Linux is a versatile operating system that supports many different file systems, including ext2, ext3, ext4, XFS, Btrfs, and NTFS, among others. Each of these file systems has unique features and is suited to specific use cases. The best file system choice depends on the specific requirements of the application or user such as:
ext2 is an older file system with no journaling capabilities, which makes it less suited for modern systems but still useful in certain low-overhead scenarios (like USB drives).

    - ext3 and ext4 are more advanced, with journaling (which helps in recovering from crashes), and ext4 is the default choice for most modern Linux systems because it offers a balance of performance, reliability, and large file support.

    - Btrfs is known for advanced features like snapshotting and built-in data integrity checks, making it ideal for complex storage setups.

    - XFS excels at handling large files and has high performance. It is best suited for environments with high I/O demands

    - NTFS, originally developed for Windows, is useful for compatibility when dealing with dual-boot systems or external drives that need to work on both Linux and Windows systems.

When selecting a file system, it’s essential to analyze the needs of the application or user factors such as performance, data integrity, compatibility, and storage requirements will influence the decision.
Linux's file system architecture is based on the Unix model, organized in a hierarchical structure. This structure consists of several components, the most critical being inodes. Inodes are data structures that store metadata about each file and directory, including permissions, ownership, size, and timestamps. Inodes do not store the file’s actual data or name, but they contain pointers to the blocks where the file’s data is stored on the disk.
The inode table is a collection of these inodes, essentially acting as a database that the Linux kernel uses to track every file and directory on the system. This structure allows the operating system to efficiently access and manage files. Understanding and managing inodes is a crucial aspect of file system management in Linux, especially in scenarios where a disk is running out of inode space before running out of actual storage capacity.
Let's use an analogy, think of the Linux file system like a library. The inodes are like index cards in the library’s catalog system (inode table). Each card contains detailed information about a book (file) its title, author, location, and other details but not the actual book. The inode table is the entire catalog that helps the library (operating system) quickly find and manage the books (files).

In Linux, files can be stored in one of several key types:

    - Regular files
    - Directories
    - Symbolic links

## Remote Desktop Protocols in Linux

Remote desktop protocols are used in Windows, Linux, and macOS to provide graphical remote access to a system. These protocols allow administrators to manage, troubleshoot, and update systems remotely, making them essential 
tools for such scenarios. To do this, an administrator connects to the remote system using the appropriate protocol depending on the operating system they are managing. For example, when administrators need to install software 
or manage a remote system, they use the relevant protocol to establish a graphical session. Two of the most common protocols for this type of access are:

  - Remote Desktop Protocol (RDP): Primarily used in Windows environments. RDP allows administrators to connect remotely and interact with the desktop of a Windows 
                                   machine as if they were sitting right in front of it.
  - Virtual Network Computing (VNC): A popular protocol in Linux environments, although it is also cross-platform. VNC provides graphical access to remote desktops,
                                   allowing administrators to perform tasks on Linux systems in a similar way to RDP on Windows.

Think of remote desktop protocols like having different sets of keys for different types of buildings. RDP is like having a key specifically made for Windows buildings, allowing you to access and manage the rooms (desktops) 
remotely, as if you were inside. VNC, on the other hand, is more like a universal key that can work on many buildings, but it’s often used for Linux structures. 
Just as you would use the appropriate key depending on the building, administrators choose the right protocol depending on the system they need to access and control.

## Linux Security

- Several mechanisms are highly effective in securing Linux systems in keeping our and other companies' data safe. Three such mechanisms are SELinux, AppArmor, and TCP wrappers. These tools are designed to safeguard Linux 
systems against various security threats, from unauthorized access to malicious attacks. This is critical not only during penetration tests, where systems are intentionally stressed to uncover vulnerabilities, but also in real-world scenarios where an actual compromise could have serious consequences (few situations are as severe as a real-life breach.) By implementing these security measures and ensuring that we set up corresponding protection against potential attackers, we can significantly reduce the risk of data leaks and ensure our systems remain secure. While these tools share some similarities, they also have important differences.
Security-Enhanced Linux

- Security-Enhanced Linux (SELinux) is a mandatory access control (MAC) system integrated into the Linux kernel. It provides fine-grained control over access to system resources and applications by enforcing security policies. 
These policies define the permissions for each process and file on the system, significantly limiting the damage that a compromised process or service can do. SELinux operates at a low level, and though it offers strong security, it can be complex to configure and manage due to its granular controls.
AppArmor

- Like SELinux, AppArmor is a MAC system that controls access to system resources and applications, but it operates in a simpler, more user-friendly manner. AppArmor is implemented as a Linux Security Module (LSM) and uses 
application profiles to define what resources an application can access. While it may not provide the same level of fine-grained control as SELinux, AppArmor is often easier to configure and is generally considered more straightforward for day-to-day use.
TCP Wrappers

- TCP wrappers are a host-based network access control tool that restricts access to network services based on the IP address of incoming connections. When a network request is made, TCP wrappers intercept it, checking the 
request against a list of allowed or denied IP addresses. This is a simple yet effective way to control access to services, especially for blocking unauthorized systems from accessing networked resources. While it does not offer the fine-grained control of SELinux or AppArmor, TCP wrappers are an excellent tool for basic network-level protection.

- Regarding similarities, the three security mechanisms share the common goal of ensuring the safety and security of Linux systems. In addition to providing extra protection, they can restrict access to resources and services, thus reducing the risk of unauthorized access and data breaches. It's also worth noting that these mechanisms are readily available as part of most Linux distributions, making them accessible to us to enhance their systems' security. Furthermore, these mechanisms can be easily customized and configured using standard tools and utilities, making them a convenient choice for Linux users.
Although both SELinux and AppArmor are MAC systems that provide fine-grained control, they work in different ways. SELinux is deeply integrated into the kernel and offers more detailed security controls, but it can be more complex to configure and maintain. In contrast, AppArmor operates as a kernel module and uses profile-based security, making it easier to manage, though it may not offer the same level of granularity as SELinux.
On the other hand, TCP wrappers focus on controlling access to network services based on client IP addresses, which makes it simpler but limited to network-level access control. It doesn't offer the broader system resource protections that SELinux and AppArmor provide, but it’s useful for restricting access to services from unauthorized systems.
Setting Up


END OF DOC ---
