<h2 align="center">Debian Base Linux</h2>
**<p align="center">Learning URLs:
    <a href="https://youtube.com/playlist?list=PL-tKrPVkKKE2AniHDmp6zK9KGD1sjf0bd&si=Y2-MOKhcWicwUdgo">jadi Vim course S1</a> ,
    <a href="https://youtube.com/playlist?list=PL-tKrPVkKKE0kM18Sg5fqaZW1V2nidAeU&si=nErZaIaVZhFh0mGa">jadi Vim course S2</a></p>**

---

### What is Linux Debian?

**Linux Debian** is a free and open-source operating system based on the Linux kernel. It is one of the oldest and most stable Linux distributions, known for its robustness and extensive software repositories. Debian is used as the foundation for many other Linux distributions, including Ubuntu. It is developed and maintained by a community of volunteers who ensure that it remains secure, reliable, and up-to-date.

---

### Where is Linux Debian Used?

Linux Debian is used in a variety of environments, including:

- **Servers:** Debian is popular for use on servers due to its stability, security, and efficient package management. It's often chosen for web servers, database servers, and other critical systems.
- **Desktops:** While it is more commonly associated with servers, Debian can also be used as a desktop operating system, offering a variety of desktop environments and software packages.
- **Embedded Systems:** Debian’s versatility allows it to be used in embedded systems and Internet of Things (IoT) devices.
- **Development:** Many developers use Debian as their development environment due to its stability, extensive software repositories, and adherence to open-source principles.

---

### The Difference Between Linux Debian and Other Linux Distributions

1. **Stability:**
   - **Debian:** Known for its stability and reliability. Debian packages are thoroughly tested before they are included in the stable release, which can lead to slower updates but a more secure and stable system.
   - **Other Distributions:** Some distributions, like Fedora or Arch Linux, prioritize having the latest software and features, sometimes at the cost of stability.
2. **Package Management:**
   - **Debian:** Uses the Advanced Package Tool (APT) system for managing software, with packages primarily in `.deb` format.
   - **Other Distributions:** Other distributions might use different package managers, like `dnf` for Fedora or `pacman` for Arch Linux.
3. **Philosophy:**
   - **Debian:** Staunchly committed to free and open-source software, adhering to the Debian Free Software Guidelines (DFSG).
   - **Other Distributions:** Some distributions are more flexible in including non-free software or proprietary drivers.
4. **Community Support:**
   - **Debian:** Maintained by a large, global community of volunteers, with extensive documentation and community support.
   - **Other Distributions:** Support and community involvement can vary widely depending on the distribution.

In summary, Linux Debian is a highly stable, secure, and versatile operating system that is used in a variety of environments, from servers to desktops. It is known for its strong commitment to open-source principles and its reliable package management system.

---

<h2 align="center">Debian linux commands</h2>
<p align="center">

| No. | Command                                                             | Description                                                                                                                     |
| --- | ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| 1   | `mkdir [directory name]`                                            | Creates a new directory with the specified name.                                                                                |
| 2   | `cd [directory name]`                                               | Changes the current working directory to the specified one.                                                                     |
| 3   | `..`                                                                | Moves up one level in the directory hierarchy.                                                                                  |
| 4   | `~`                                                                 | Represents the path to the user's home directory.                                                                               |
| 5   | `ls`                                                                | Lists the files and directories in the current directory.                                                                       |
| 6   | `ls -ltrh`                                                          | Lists files and directories with detailed information, including sizes in a human-readable format, sorted by modification time. |
| 7   | `cat [file]`                                                        | Displays the contents of a file.                                                                                                |
| 8   | `tac`                                                               | Displays the contents of a file in reverse order, starting from the end.                                                        |
| 9   | `cp [file] [file2]`                                                 | Copies a file from the source to the destination.                                                                               |
| 10  | `mv [file name] [directory name]`                                   | Moves or renames a file to the specified directory.                                                                             |
| 11  | `rm`                                                                | Removes a specified file.                                                                                                       |
| 12  | `rmdir`                                                             | Removes an empty directory.                                                                                                     |
| 13  | `touch`                                                             | Updates file timestamps or creates an empty file if it does not already exist.                                                  |
| 14  | `clear`                                                             | Clears the terminal screen of previous commands and outputs.                                                                    |
| 15  | `uptime`                                                            | Shows the current time, system uptime, number of users logged in, and the system load averages.                                 |
| 16  | `syslog`                                                            | Displays system log messages.                                                                                                   |
| 17  | `shutdown -h now`                                                   | Immediately shuts down the system.                                                                                              |
| 18  | `man [command]`                                                     | Displays the manual or help page for the specified command.                                                                     |
| 19  | `sudo su`                                                           | Switches the current user to the root user with superuser privileges.                                                           |
| 20  | `ping [ip address]`                                                 | Sends ICMP echo requests to the specified IP address to test connectivity and measure response time.                            |
| 21  | `ifconfig`                                                          | Configures or displays network interface parameters and settings.                                                               |
| 22  | `ip addr show`                                                      | Shows IP addresses and other properties of network interfaces.                                                                  |
| 23  | `arp`                                                               | Displays, adds, or removes entries in the ARP cache.                                                                            |
| 24  | `sudo arp -d [ip address]`                                          | Deletes the specified IP address from the ARP cache.                                                                            |
| 25  | `ip route`                                                          | Displays or modifies the IP routing table.                                                                                      |
| 26  | `sudo ip addr add [ip] dev [device]`                                | Assigns a specified IP address to a network interface device.                                                                   |
| 27  | `sudo ip route add [ip] dev [device]`                               | Adds a new route to the IP routing table.                                                                                       |
| 28  | `sudo ip route add default dev [device name]`                       | Sets the default gateway for the specified network device.                                                                      |
| 29  | `dig [site or ip]`                                                  | Queries DNS servers for detailed information about the domain or IP address.                                                    |
| 30  | `dig a +short`                                                      | Queries DNS for short answers about A records (IPv4 addresses) only.                                                            |
| 31  | `nslookup [name and domain]`                                        | Queries DNS to obtain the domain name or IP address mapping for the specified name.                                             |
| 32  | `mtr [site or ip]`                                                  | Combines the functionality of `ping` and `traceroute` to provide a comprehensive view of network connections.                   |
| 33  | `traceroute [ip]`                                                   | Traces the path packets take to reach the specified IP address.                                                                 |
| 34  | `less /etc/services`                                                | Displays the contents of the `/etc/services` file, which lists network services and their corresponding ports.                  |
| 35  | `ssh`                                                               | Initiates a connection to an SSH server.                                                                                        |
| 36  | `ssh maskiiw@192.168.8.100`                                         | Connects to the SSH server at the specified IP address as the user "maskiiw".                                                   |
| 37  | `open ssh -server`                                                  | Starts an SSH server on the local machine.                                                                                      |
| 38  | `open ssh -client`                                                  | Starts an SSH client on the local machine.                                                                                      |
| 39  | `ssh-keygen -f "/home/maskiiw/.ssh/known_hosts" -R "192.168.8.100"` | Removes the specified host from the SSH known hosts file.                                                                       |
| 40  | `sftp`                                                              | Starts an SSH File Transfer Protocol session for transferring files securely.                                                   |
| 41  | `telnet`                                                            | Connects to a remote device or server over the network using the Telnet protocol.                                               |
| 42  | `telnet localhost 10000`                                            | Connects to port 10000 on the local machine using Telnet.                                                                       |
| 43  | `netstat -na`                                                       | Displays network connections, routing tables, and interface statistics in numeric format.                                       |
| 44  | `netstat -tulpn`                                                    | Shows active TCP and UDP connections along with the applications using them.                                                    |
| 45  | `iptables`                                                          | Configures the IP packet filtering rules for the Linux kernel firewall.                                                         |
| 46  | `nc`                                                                | Reads from and writes to network connections using TCP or UDP.                                                                  |
| 47  | `nc -l -p [port] -v`                                                | Listens on the specified port and provides verbose output of the connections.                                                   |
| 48  | `less`                                                              | Reads the contents of a file one page at a time, allowing for navigation without loading the entire file into memory.           |
| 49  | `pipe symbol`                                                       | The pipe symbol (`                                                                                                              | `) is used to pass the output of one command as input to another command. |
| 50  | `tab`                                                               | Autocompletes the rest of the command or filename.                                                                              |
| 51  | `double tap`                                                        | Displays available options for autocompletion by pressing the tab key twice.                                                    |
| 52  | `dnsx -silent`                                                      | Executes a DNS enumeration scan silently, without displaying verbose output.                                                    |
| 53  | `dig a +short`                                                      | Retrieves a short summary of A (IPv4 address) records for the specified domain.                                                 |
| 54  | `sudo traceroute [ip]`                                              | Displays the route packets take to a network host using elevated (superuser) permissions.                                       |
| 55  | `sudo ip addr add [ip] dev [device]`                                | Adds an IP address to a specified network device with superuser permissions.                                                    |
| 56  | `sudo ip route add default dev [device name]`                       | Adds a default route to the routing table with superuser permissions.                                                           |
| 57  | `clear`                                                             | Clears the terminal screen of previous commands and outputs.                                                                    |
| 58  | `uptime`                                                            | Displays the system uptime, number of users logged in, and the system load averages.                                            |

</p>

---
