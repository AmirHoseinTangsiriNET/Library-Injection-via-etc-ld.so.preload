# Library Injection via ld.so.preload File 
A technique that uses /etc/ld.so.preload to inject custom libraries for code execution and persistence
### Description
This technique exploits the /etc/ld.so.preload file on Linux systems to achieve system-wide persistence by injecting a shared library that loads with every dynamically linked process. By adding a custom library path to /etc/ld.so.preload, attackers can execute arbitrary code whenever any new process is started. This technique leverages the dynamic linker (ld.so) to preload a specified library before standard libraries, making it effective for both privilege escalation and stealth operations.

When an application starts, the dynamic linker checks /etc/ld.so.preload and loads any libraries listed there, enabling custom code to run with the privileges of the calling process. Because /etc/ld.so.preload applies system-wide and requires root permissions to modify, it is often used by attackers with escalated privileges to maintain control over a compromised system. This can be leveraged to execute logging, monitoring, or malicious activities silently across reboots and user sessions.
<p align="center">
  <img src="Video/etcldso.gif" alt="Master">
</p>
