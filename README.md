# [Registry Monitor & Protection SDK](https://www.easefilter.com/Forums_Files/RegMon.htm)

---
A powerful, kernel-level Windows Registry monitoring, tracking, and access control framework built on top of the Windows Registry Filter Driver architecture. **EaseFilter RegMon** allows developers to intercept, audit, modify, and block registry operations in real time, delivering robust defense against unauthorized modifications, "fileless" malware, and tampering with critical system configurations.
---

## 🚀 Key Features

* **Real-Time Registry Monitoring:** Track create, delete, read, write, rename, and query operations across Windows registry keys and values instantly.
* **Granular Access Control:** Define strict inclusion/exclusion rules to allow or deny registry operations based on process name, user context, or key paths.
* **"Fileless" Malware Protection:** Safeguard critical registry hives (such as `Run`, `RunOnce`, and system startup persistence mechanisms) from unauthorized persistence injections.
* **Pre- and Post-Operation Callbacks:** Inspect input/output buffers and decide whether to permit, deny (`STATUS_ACCESS_DENIED`), or redirect operations before the Configuration Manager processes them.
* **Registry Key Virtualization:** Dynamically redirect or return custom virtualized registry data for tailored application behavior and sandboxing.
* **Developer-Friendly API:** Simple, robust C# and C++ APIs with complete sample projects for rapid prototyping and enterprise integration.

---

## 🛠️ Architecture & How It Works

EaseFilter RegMon operates at the kernel level by registering a `RegistryCallback` routine with the Windows kernel filter architecture. 
![Registry SDK Architecture](https://www.easefilter.com/Images/registry-filter-driver-architecture.jpg)

1. **Interception:** Captures registry transaction requests (`REG_NOTIFY_CLASS` operations) before they hit storage or the system configuration manager.
2. **Context Evaluation:** Passes a `REG_XXX_KEY_INFORMATION` data structure containing process ID, user identity, key path, and value details to the user-mode service or callback handler.
3. **Policy Enforcement:** Evaluates incoming actions against custom filter masks and rules to allow execution, log audit trails, or block unauthorized alterations instantly.

---

## 📋 Configuration & Quick Setup

To monitor or control Windows registry activities using the EaseFilter SDK:

1. **Define Filter Rules:** Establish process filter masks (e.g., matching specific executables or PIDs) combined with target registry key paths.
2. **Set Access Control Flags:** Configure rule actions to audit or block unauthorized write/delete attempts on sensitive hives.
3. **Register Callbacks:** Implement pre-notification routines to inspect and dynamically filter registry changes.

---


## EaseFilter File System Filter Driver SDK Reference
| Product Name | Description |
| --- | --- |
| [Cloud File System SDK](https://www.easefilter.com/cloud/cloud-file-system-sdk.htm) | EaseFilter Cloud File System SDK Introduction. |
| [CloudTier Storage Tiering SDK](https://www.easefilter.com/cloud/storage-tiering-sdk.htm) | EaseFilter Storage Tiering Filter Driver SDK Introduction. |
| [File Monitor SDK](https://www.easefilter.com/kb/file-monitor-filter-driver-sdk.htm) | EaseFilter File Monitor Filter Driver SDK Introduction. |
| [File Control SDK](https://www.easefilter.com/kb/file-control-file-security-sdk.htm) | EaseFilter File Control Filter Driver SDK Introduction. |
| [File Encryption SDK](https://www.easefilter.com/kb/transparent-file-encryption-filter-driver-sdk.htm) | EaseFilter Transparent File Encryption Filter Driver SDK Introduction. |
| [Registry Filter SDK](https://www.easefilter.com/kb/registry-filter-drive-sdk.htm) | EaseFilter Registry Filter Driver SDK Introduction. |
| [Process Filter SDK](https://www.easefilter.com/kb/process-filter-driver-sdk.htm) | EaseFilter Process Filter Driver SDK Introduction. |
| [EaseFilter SDK Programming](https://www.easefilter.com/kb/programming.htm) | EaseFilter Filter Driver SDK Programming. |

## EaseFilter SDK Sample Projects
| Sample Project | Description |
| --- | --- |
| [CloudTier Storage Tiering Demo](https://www.easefilter.com/cloud/cloudtier-storage-tiering-demo.htm) | A HSM File System Filter Driver Demo. |
| [CloudTier S3 Tiering Demo](https://www.easefilter.com/cloud/cloudtier-s3-intelligent-tiering-demo.htm) | CloudTier S3 Intelligent Tiering Demo. |
| [Cloud File DR S3 Demo](https://www.easefilter.com/cloud/cloud-file-dr-demo.htm) | Cloud File DR S3 Demo. |
| [Amazon S3 File Explorer Demo](https://www.easefilter.com/cloud/s3-browser-demo.htm) | Amazon S3 File Explorer Demo. |
| [Auto File DRM Encryption](https://www.easefilter.com/kb/auto-file-drm-encryption-tool.htm) | Auto file encryption with DRM data embedded. |
| [Transparent File Encrypt](https://www.easefilter.com/kb/AutoFileEncryption.htm) | Transparent on access file encryption. |
| [Secure File Sharing with DRM](https://www.easefilter.com/kb/DRM_Secure_File_Sharing.htm) | Secure encrypted file sharing with digital rights management. |
| [File Monitor Example](https://www.easefilter.com/kb/file-monitor-demo.htm) | Monitor file system I/O in real time, tracking file changes. |
| [File Protector Example](https://www.easefilter.com/kb/file-protector-demo.htm) | Prevent sensitive files from being accessed by unauthorized users or processes. |
| [FolderLocker Example](https://www.easefilter.com/kb/FolderLocker.htm) | Lock file automatically in a FolderLocker. |
| [Process Monitor](https://www.easefilter.com/kb/Process-Monitor.htm) | Monitor the process creation and termination, block unauthorized process running. |
| [Registry Monitor](https://www.easefilter.com/kb/RegMon.htm) | Monitor the Registry activities, block the modification of the Registry keys. |
| [Secure Sandbox Example](https://www.easefilter.com/kb/Secure-Sandbox.htm) |A secure sandbox example, block the processes accessing the files out of the box. |
| [FileSystemWatcher Example](https://www.easefilter.com/kb/FileSystemWatcher.htm) | File system watcher, logging the file I/O events. |
| [ZeroTrust Example](https://www.easefilter.com/kb/zero-trust-file-access-control-demo.htm) | Zero trust file access control with encryption feature. |

## Filter Driver Reference

* [Understand MiniFilter Driver](https://www.easefilter.com/kb/understand-minifilter.htm)
* [Understand File I/O](https://www.easefilter.com/kb/File_IO.htm)
* [Understand I/O Request Packets(IRPs)](https://www.easefilter.com/kb/understand-irps.htm)
* [Filter Driver Developer Guide](https://www.easefilter.com/kb/DeveloperGuide.htm)
* [MiniFilter Filter Driver Framework](https://www.easefilter.com/kb/minifilter-framework.htm)
* [Isolation Filter Driver](https://www.easefilter.com/kb/Isolation_Filter_Driver.htm)

## License

This repository contains two distinct licensing categories:

1. **Wrapper/Implementation Code (MIT License):** 
   The source code, scripts, and configuration files provided directly in this repository are licensed under the [MIT License](LICENSE). You are free to modify, distribute, and use this specific integration code.

2. **EaseFilter SDK (Commercial License):**
   This project requires the EaseFilter SDK (including its binaries, filter drivers, and core libraries) to function. The EaseFilter SDK is **proprietary commercial software** and is strictly excluded from the MIT License.   
   To use the EaseFilter SDK for commercial purposes or in a production environment, you must obtain a valid commercial license directly from [EaseFilter](https://www.easefilter.com/license.pdf).


## Support
If you have questions or need help, please contact support@easefilter.com 

[Home](https://www.easefilter.com/) | [Solution](https://www.easefilter.com/solutions.htm) | [Download](https://www.easefilter.com/download.htm) | [Demos](https://www.easefilter.com/online-fileio-test.aspx) | [Blog](https://blog.easefilter.com/) | [Programming](https://www.easefilter.com/kb/programming.htm)
