# 🐧 Day 2: Linux Storage Architecture & Filesystem Hierarchy Standard (FHS)

### 💾 1. Linux File System Deep Dive
* **Everything is a File:** Learned that Linux treats hardware, directories, and processes all as files.
* **Inodes (Index Nodes):** Understood how metadata (size, permissions, timestamps) is stored separately from actual data blocks.
* **Journaling (ext4 vs XFS):** Explored how modern filesystems use journaling to prevent data corruption during sudden power failures or crashes.

### 🏛️ 2. Filesystem Hierarchy Standard (FHS) Mapped:
* `/etc`: System configuration files (e.g., `/etc/passwd` for users, `/etc/resolv.conf` for DNS).
* `/var/log`: System dynamic logs used for debugging and server auditing (e.g., `/var/log/messages`).
* `/proc`: Virtual memory-based filesystem displaying live kernel and hardware metrics (e.g., `/proc/cpuinfo`).
* `/dev`: Device files representing connected hardware components directly.
* `/usr`: User binaries, documentation, and source libraries (`/usr/bin` and `/usr/sbin`).
