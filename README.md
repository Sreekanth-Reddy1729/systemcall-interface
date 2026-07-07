# SecureSysCall: A Linux System Call Interception Framework for Policy-Based File Access Control

## Overview

SecureSysCall is a Linux system programming project that demonstrates how file access can be monitored and controlled through system call interception. The project uses a JSON-based policy file to define blocked file paths and prevents access to those files during runtime.

The goal of this project is to understand Linux system calls, access control mechanisms, kernel-user interactions, and policy enforcement techniques.

---

## Features

- System call interception
- Policy-based file access control
- JSON configuration for blocked files
- Fast in-memory policy loading
- Modular C implementation
- Easy to extend for additional security rules

---

## Technologies Used

- C Programming
- Linux System Programming
- POSIX APIs
- cJSON Library
- GCC
- JSON

---

## Project Structure

```
systemcall-interface/
│
├── src/
│   ├── interceptor.c      # System call interception logic
│   ├── policy.c           # Loads and enforces security policies
│   ├── policy.h           # Header file for policy module
│   └── policy.json        # JSON file containing blocked file paths
│
└── README.md
```

---

## How It Works

1. The application loads the security policy from `policy.json`.
2. All blocked file paths are stored in memory.
3. Whenever a file access request is intercepted, the requested path is compared with the blocked list.
4. If the file exists in the policy, access is denied.
5. Otherwise, the request is allowed.

---

## Example Policy

```json
{
  "blocked_files": [
    "/etc/passwd",
    "/home/user/secret.txt"
  ]
}
```

---

## Building the Project

Compile using GCC.

```bash
gcc interceptor.c policy.c -lcjson -o systemcall-interface
```

---

## Running

```bash
./systemcall-interface
```

---

## Learning Objectives

- Linux System Programming
- System Call Interception
- File Access Control
- JSON Parsing in C
- Security Policy Enforcement
- Memory Management in C

---

## Future Improvements

- Directory-level access control
- Wildcard path matching
- Read/Write permission policies
- User and group-based access control
- Logging and auditing
- Dynamic policy reloading
- Kernel module implementation
- Support for SELinux/AppArmor integration

---

## Author

**Sreekanth Reddy**
Team Projet 

---

## License

This project is intended for educational and research purposes.
