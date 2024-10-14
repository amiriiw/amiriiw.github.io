<h2 align="center">CVE-2019-14287: Sudo Vulnerability</h2>
**<p align="center">learning URLs: <a href="https://youtu.be/Y5kjWgiN6uQ?si=3lqHM_z8LuIVPBEE">jadi</a></p>**

---
# CVE-2019-14287: Sudo Vulnerability Explained
In 2019, a critical vulnerability was discovered in the **sudo** program, which allowed non-privileged users to gain root access. This bug is officially known as **CVE-2019-14287**. Sudo is a vital tool in Unix and Linux-based systems that allows authorized users to execute commands with elevated privileges (usually root).

## Bug Explanation:
The vulnerability was found in the user management functionality of sudo. Specifically, it occurred when a user was configured in the **sudoers** file to have access to specific accounts but was restricted from using the root account. However, if the user executed the `sudo` command with the `-u` option and passed a value of `-1` or `4294967295` (which are equivalent due to unsigned integer wrapping), the system would mistakenly allow them to execute commands as root.

Normally, when using `sudo -u`, you are expected to provide a valid user ID (UID) so that the command is executed as that user. However, when the UID `-1` (or `4294967295`) was provided, the system misinterpreted this value and mapped it to the root user. This incorrect mapping allowed a non-privileged user to gain root-level access.

## Scenario:
Suppose a user is allowed to execute commands as a specific UID in the `sudoers` file but is explicitly denied root privileges. If that user executes a command with the `-u` option using the value `-1`, they would mistakenly be granted root access. This vulnerability could allow a regular user to elevate their privileges to root and take full control of the system.

## Example:
```
sudo -u#-1 command
```
In this case, `command` could be any command the user wants to run with root privileges.

## Fix:
The vulnerability was fixed by ensuring that invalid UID values, such as `-1` or `4294967295`, are correctly handled and prevented from being interpreted as root.

### Vulnerable Code:
The vulnerable code failed to properly handle the `-1` value, leading to the incorrect privilege escalation. This issue was found in how sudo parsed and validated user input.
```c
    if (user_uid == (uid_t)-1) {
        user_uid = ROOT_UID;
    }
```
In this code, if the `user_uid` was set to `-1`, it was automatically assigned the `ROOT_UID`, giving unintended root privileges.

### Fixed Code:
The fix involved adding checks to ensure that negative or invalid UIDs were rejected, preventing the incorrect assignment of root privileges.
```c
    if (user_uid == (uid_t)-1 || user_uid == UID_MAX) {
        log_error("Invalid UID: %d", user_uid);
        return SUDO_RC_ERROR;
    }
```
In this fixed version, when the `user_uid` is `-1` or `UID_MAX` (which is equivalent to `4294967295` on many systems), an error is logged and the operation is aborted, preventing the privilege escalation.

## Significance:
This bug was significant because it allowed privilege escalation to root without proper authentication. Systems vulnerable to this issue were at high risk, especially in environments where unprivileged users had access to the system.

## References:
- [sudoers Manual](https://www.sudo.ws/man/1.8.28/sudoers.man.html)
- [CVE-2019-14287 Description](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-14287)

---