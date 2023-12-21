# **Linux Basics: A Cheat Sheet to Essential Commands**

<img src="../source/linux-cheat-sheet.png"></img>


## Introduction
In the world of computing, Linux stands out as a powerful, versatile, and open-source operating system. It's widely used in various environments, from personal computers to servers, and offers a range of features that appeal to both beginners and advanced users. This article aims to introduce Linux, explore its benefits, and provide a basic understanding of some common Linux commands.

## Key Linux Commands and Operations
Linux commands are the backbone of its functionality. Here, we outline some fundamental operations that are essential for anyone beginning their Linux journey.


### 1. File and Directory Operations

1. **Using Wildcards**: Explain how wildcards (like `*` and `?`) can be used with commands like `ls`, `cp`, `mv`, and `rm` to perform operations on multiple files at once.
   - Example: `ls *.txt` lists all files ending with `.txt`.
   - `rm *.jpg` deletes all `.jpg` files in the current directory.

2. **Combining Commands with Pipes and Redirection**:
   - Show how to use pipes (`|`) and redirection (`>`, `>>`) to combine commands for powerful operations.
   - Example: `ls -l | grep "Jan"` to list files modified in January.
   - `ls -l > filelist.txt` saves the list of files to `filelist.txt`.

3. **Viewing File Content**:
   - Introduce commands like `cat`, `less`, and `tail`.
   - Example: `cat filename.txt` to display the content of `filename.txt`.
   - `tail -n 5 filename.txt` to view the last 5 lines of `filename.txt`.

4. **Searching Within Files**:
   - Discuss the use of `grep` for searching text within files.
   - Example: `grep "search term" filename.txt` to find "search term" in `filename.txt`.

5. **File Permissions**:
   - Elaborate on changing file permissions with `chmod`.
   - Example: `chmod 755 script.sh` to make `script.sh` readable and executable by everyone but only writable by the owner.

6. **Linking Files**:
   - Explain the difference between hard links (`ln`) and symbolic links (`ln -s`).
   - Example: `ln -s /path/to/original /path/to/link` to create a symbolic link.

7. **Finding Files and Directories**:
   - Introduce `find` command for locating files and directories based on criteria like name, size, or modification time.
   - Example: `find /home -name "*.txt"` to find all `.txt` files in `/home`.

8. **Disk Usage**:
   - Show how to check disk usage with `du` and disk space with `df`.
   - Example: `du -sh /path/to/directory` to check the size of a directory.

9. **Archiving and Compression**:
   - Discuss creating archives with `tar` and compressing files with `gzip` and `bzip2`.
   - Example: `tar -czvf archive.tar.gz /path/to/directory` to compress and archive a directory.

10. **Advanced File Manipulation**:
    - Introduce commands like `sed` for stream editing and `awk` for pattern scanning and processing.
    - Example: `sed 's/original/replacement/' filename` to replace text in a file.

---


### 2. Copying, Moving Files, and Permissions

- **`cp [source] [destination]`**: Copies files or directories.
   - Basic Usage: `cp file1.txt file2.txt` copies `file1.txt` to `file2.txt`.
   - Copying Directories: `cp -r source_directory destination_directory` copies the entire directory and its contents.
   - Preserving Attributes: `cp -p file1.txt file2.txt` copies `file1.txt` to `file2.txt` while preserving the mode, ownership, and timestamps.

- **`mv [source] [destination]`**: Moves or renames files or directories.
   - Moving Files: `mv file1.txt directory/` moves `file1.txt` into the specified directory.
   - Renaming: `mv oldname.txt newname.txt` renames `oldname.txt` to `newname.txt`.
   - Moving Directories: `mv source_directory new_location/` moves an entire directory.

- **`chmod [permission] [file]`**: Changes file and directory permissions.
   - Changing Permissions: `chmod 755 filename.txt` sets the permissions of `filename.txt` to `-rwxr-xr-x`.
   - Symbolic Mode: `chmod u=rwx,g=rx,o=r filename.txt` sets permissions using symbolic representation (u for user, g for group, o for others).
   - Recursive Permission Change: `chmod -R 755 directory/` changes permissions for a directory and all its subdirectories.

- **Additional Notes and Examples**:
   - **Using Wildcards**: You can use wildcards with these commands for batch operations. Example: `cp *.txt backup/` copies all `.txt` files to the `backup` directory.
   - **Interactive Mode**: Adding `-i` to `cp` and `mv` prompts before overwriting. Example: `cp -i file1.txt file2.txt` asks for confirmation if `file2.txt` exists.
   - **Verbose Mode**: Adding `-v` provides detailed output of the operation. Example: `mv -v file1.txt new_directory/` shows the process of moving the file.

- **Tips for Understanding Permissions**:
   - Explain the structure of Linux permissions (read, write, execute for user, group, and others).
   - Discuss the numeric (e.g., 755) and symbolic (e.g., u+rwx) methods of setting permissions.
   - Mention the use of `umask` for setting default permissions.


---

### 3. Searching and System Information

- **`grep [word] [file]`**: Searches for text in files.
   - Basic Usage: `grep "search_term" filename.txt` searches for "search_term" in `filename.txt`.
   - Case Insensitivity: `grep -i "search_term" filename.txt` searches without considering case.
   - Recursive Search: `grep -r "search_term" /path/to/directory/` searches all files under the directory for "search_term".
   - Line Number Display: `grep -n "search_term" filename.txt` displays the line numbers along with the lines that match the search term.

- **`sudo [command]`**: Executes commands with administrative (root) privileges.
   - Example: `sudo apt-get update` runs the package list update command with root privileges.
   - Important Note: `sudo` should be used with caution as it grants powerful access and can affect system-wide settings.

- **`ps`**: Lists running processes.
   - Basic Listing: `ps` shows a snapshot of current processes.
   - Detailed View: `ps aux` provides a detailed list of all running processes.
   - Specific User's Processes: `ps -u username` lists processes run by a specific user.

- **`kill [process_id]`**: Terminates a specific process.
   - Basic Usage: `kill 12345` sends a signal to terminate the process with ID 12345.
   - Forceful Termination: `kill -9 12345` forcefully stops the process. Use with caution.
   - Multiple Processes: `kill 12345 67890` terminates both processes with IDs 12345 and 67890.

- **`top`**: Displays system resources and processes in real-time.
   - Usage: Running `top` will open an interactive interface showing system statistics and a list of processes.
   - Sort by CPU, Memory, etc.: Inside `top`, you can sort processes by various criteria like CPU usage (`P` key) or memory (`M` key).

    ### Additional Concepts and Commands
    
    - **Searching with `find`**: 
       - Use `find /path/to/search -name "filename"` to search for files and directories by name.
       - Complex Searches: `find / -type f -size +2M` finds files larger than 2 MB in the entire system.
    
      - **Monitoring with `htop`**:
         - `htop` is an advanced version of `top` with a more user-friendly interface. It provides a dynamic real-time view of the running system.
         - Note: `htop` might need to be installed separately.
    
      - **Using `lsof` for Open Files**:
         - `lsof` lists open files and the processes that opened them. For instance, `lsof -i :80` shows processes using port 80.
    
      - **Disk Usage with `df` and `du`**:
         - `df -h` shows disk space usage on all mounted filesystems in a human-readable format.
         - `du -sh /path/to/directory` shows the disk usage of a specified directory.


---


### 4. Software Management

- **`apt-get install [package_name]`**: Installs software on Debian-based systems (like Ubuntu).
   - Basic Usage: `apt-get install package_name` installs a specific package. For example, `apt-get install nginx` installs the Nginx web server.
   - Updating Package Lists: Before installing, it's a good practice to update package lists: `sudo apt-get update`.
   - Upgrade Packages: `sudo apt-get upgrade` upgrades all installed packages to their latest versions.
   - Search for Packages: `apt-cache search keyword` searches for packages related to the keyword.

- **`yum install [package_name]`**: Installs software on Red Hat-based systems (like CentOS and Fedora).
   - Basic Usage: `yum install package_name` to install a package. For instance, `yum install httpd` installs the Apache HTTP server.
   - Updating Packages: `yum update` updates all installed packages.
   - Search for Packages: `yum search keyword` searches for packages by keyword.
   - List Installed Packages: `yum list installed` shows all installed packages.

    ### Additional Concepts and Commands for Software Management
    
    - **Advanced Package Tool (APT) for Debian-based Systems**:
       - `apt-get autoremove` removes packages that were automatically installed to satisfy dependencies for other packages and are now no longer needed.
       - `apt-get clean` clears out the local repository of retrieved package files, freeing up disk space.
    
      - **YUM (Yellowdog Updater, Modified) for Red Hat-based Systems**:
         - `yum check-update` lists available updates for installed packages.
         - `yum remove package_name` removes a package (e.g., `yum remove httpd`).
    
      - **Using DNF on Fedora**: 
         - Fedora and newer Red Hat systems use `dnf` instead of `yum`. For example, `dnf install package_name`.
    
      - **Snap Packages**: 
         - Snap is a package management system that works across different Linux distributions. `snap install package_name` installs a snap package.
         - Snap packages are self-contained, which reduces compatibility issues.
    
      - **Flatpak for Desktop Applications**:
         - Flatpak is another universal packaging system for desktop applications. Use `flatpak install application_name` to install applications.
    
      - **Building from Source**:
         - Sometimes, software might need to be compiled from source. This usually involves downloading the source code, configuring the build environment with `./configure`, compiling with `make`, and installing with `sudo make install`.
         - Note: Installing from source should be done cautiously, as it falls outside standard package management and might affect system stability.

---


### 5. File Compression and Downloading

- **`tar -czvf [archive_name.tar.gz] [directory]`**: Compresses a directory into a `.tar.gz` archive.
   - Basic Usage: `tar -czvf archive.tar.gz directory/` compresses the `directory` into `archive.tar.gz`.
   - Explanation: 
     - `c` creates a new archive.
     - `z` uses gzip for compression.
     - `v` verbose mode, shows progress in the terminal.
     - `f` specifies the filename of the archive.

- **`tar -xzvf [archive_name.tar.gz]`**: Extracts a compressed archive.
   - Basic Usage: `tar -xzvf archive.tar.gz` extracts the contents of `archive.tar.gz`.
   - Explanation:
     - `x` extracts files from an archive.
     - `z` tells tar to decompress the archive (gzip).
     - `v` verbose mode, displays files being extracted.
     - `f` specifies the filename of the archive.

- **`wget [URL]`**: Downloads files from the internet.
   - Basic Usage: `wget http://example.com/file.zip` downloads `file.zip` from the specified URL.
   - Download in Background: `wget -b http://example.com/file.zip` downloads the file in the background.
   - Download Multiple Files: Create a text file with URLs (one per line) and use `wget -i file.txt` to download all the files listed.

    ### Additional Concepts and Commands for File Handling
    
    - **Using `gzip` and `bzip2` for File Compression**:
       - Compress a File: `gzip filename.txt` compresses `filename.txt` to `filename.txt.gz`.
       - Decompress a File: `gunzip filename.txt.gz` or `gzip -d filename.txt.gz`.
    
      - **File Extraction with `unzip` and `7z`**:
         - `unzip file.zip` extracts the contents of a ZIP file.
         - `7z x file.7z` extracts files from a 7z archive.
    
      - **Using `curl` for Downloading**:
         - `curl -O URL` downloads a file from the internet, similar to `wget`.
         - `curl` can also be used for sending HTTP requests, making it versatile for web-related tasks.
    
      - **Advanced `tar` Options**:
         - Incremental Backups: `tar` can be used to create incremental backups. Use `tar -czvf backup.tar.gz --listed-incremental=/path/to/snapshot.file /path/to/directory` for creating or updating an incremental backup.
         - Excluding Files: Use `--exclude='pattern'` to exclude files matching the pattern.
    
      - **Downloading Files with `axel`**:
         - `axel URL` can download files faster by using multiple connections. It's an alternative to `wget` and `curl` for downloading large files.

---


### 6. Text Editors

- **`nano [file]`**: Nano is a user-friendly, command-line text editor suitable for beginners.
   - Basic Usage: `nano filename.txt` opens `filename.txt` in Nano for editing. If `filename.txt` doesn't exist, it will be created upon saving.
   - Saving Changes: Inside Nano, use `Ctrl + O` to save changes, followed by `Enter`.
   - Exiting: Use `Ctrl + X` to exit Nano. If there are unsaved changes, it will prompt you to save them.
   - Cut/Paste Text: `Ctrl + K` cuts the current line, and `Ctrl + U` pastes it.

- **`echo [text]`**: Prints text to the console or redirects it to a file.
   - Displaying Text: `echo "Hello, world!"` displays "Hello, world!" on the screen.
   - Redirecting to a File: `echo "Some text" > file.txt` writes "Some text" to `file.txt`. If `file.txt` exists, it will be overwritten.
   - Appending to a File: `echo "More text" >> file.txt` appends "More text" to `file.txt` without overwriting the existing content.

    ### Additional Concepts and Commands for Text Editing
    
    - **Using `vim` or `vi`**:
       - Vim (or Vi) is a powerful text editor. Use `vim filename.txt` to open or create a file.
       - Vim has different modes (insert, command, visual). Press `i` to enter insert mode; press `Esc` to go back to command mode.
       - To save and exit, in command mode type `:wq`; just `:q` to exit without saving.
    
      - **Using `gedit` for Graphical Text Editing**:
         - `gedit` is a simple, graphical text editor for GNOME. Use `gedit filename.txt` to open or create a file in a GUI environment.
         - Good for users who prefer a graphical interface over command-line editing.
    
      - **Advanced Editing with `sed`**:
         - `sed` is a stream editor for filtering and transforming text. Example: `sed 's/original/replacement/' filename.txt` replaces the first occurrence of "original" with "replacement" in each line of `filename.txt`.
    
      - **Batch Editing with `awk`**:
         - `awk` is a powerful language for text processing. Useful for complex file formatting, data reformatting, and report generation.
         - Basic Usage: `awk '{ print $1 }' filename.txt` prints the first column of `filename.txt`.
    
      - **Editing with `emacs`**:
         - Emacs is a highly customizable text editor. Open a file with `emacs filename.txt`.
         - It has a steep learning curve but offers powerful features for coding, project planning, writing, and more.

---

### 7. Network Management

- **`ifconfig` / `ip addr`**: Displays network interfaces and their settings.
   - `ifconfig`: Traditional command to view and configure network interfaces. Example: `ifconfig eth0` shows configuration for `eth0`.
   - `ip addr`: Modern replacement for `ifconfig`. Example: `ip addr show` lists all network interfaces with their IP addresses.

- **`ping [hostname/IP]`**: Checks connectivity to a host.
   - Basic Usage: `ping google.com` sends ICMP echo requests to Google to check internet connectivity.
   - Control Count: `ping -c 4 google.com` sends exactly 4 pings.

- **`netstat`**: Shows network statistics, active connections, routing tables, etc.
   - Basic Usage: `netstat -r` shows the routing table.
   - Active Connections: `netstat -tuln` lists active listening ports and their status.

- **`nslookup` / `dig`**: Queries DNS to look up IP addresses associated with hostnames.
   - `nslookup google.com` gets the IP address for google.com.
   - `dig google.com` provides detailed DNS information including response time.

- **`traceroute [hostname/IP]`**: Traces the route packets take to a network host.
   - Usage: `traceroute google.com` shows the path packets take to reach Google.

- **`iwconfig` / `nmcli`**: Configures wireless network interfaces.
   - `iwconfig`: Similar to `ifconfig` but for wireless networks. `iwconfig wlan0` shows configuration for wireless interface `wlan0`.
   - `nmcli`: Network Manager command-line tool, more user-friendly. `nmcli d` lists all network devices.

- **`iptables` / `firewalld`**: Manages network firewall rules.
   - `iptables`: Traditional tool for configuring firewall rules. Example: `iptables -L` lists all active firewall rules.
   - `firewalld`: A newer firewall management solution. Use `firewall-cmd --list-all` to view rules.

- **`ssh [user@host]`**: Securely connects to a remote server.
   - Usage: `ssh user@remote_server` to log into `remote_server` as `user`.
   - Key-based Authentication: Use SSH keys for a more secure and convenient login method than passwords.

- **`scp [source] [destination]`**: Securely copies files between local and remote hosts.
   - Example: `scp file.txt user@remote_server:/path/to/destination` copies `file.txt` to the remote server.

- **`wget` / `curl` for Downloading**:
   - Already covered in the "File Compression and Downloading" section, but also relevant for network operations.

### Tips and Best Practices:

- Regularly check and update network configurations to ensure network security and efficiency.
- Familiarize yourself with the network management tools specific to your distribution, as some commands may vary.
- For remote server management, always prioritize secure methods like SSH and use strong passwords or key-based authentication.

---


## 🚀 **Linux Basics: A Cheat Sheet to Essential Commands**
- 🔍 Looking for a thorough guide to master Linux? Dive into the extensive Linux Cheat Sheet I've compiled on GitHub! It's a treasure trove of information for both novices and seasoned developers. This cheat sheet covers everything from basic commands to advanced Linux features, ensuring you have a quick yet detailed reference at your fingertips.
- 🔗 Access the full cheat sheet here: [Linux Basics: A Cheat Sheet to Essential Commands](linux-cheat-sheet.md)
- 💡 Whether you're starting out or looking to refine your Linux skills, this resource is tailored to boost your productivity and understanding of containerization. Don't miss out on this valuable tool for modern software development!




### Conclusion

These commands form the foundation for getting things done in Linux. However, this is just the beginning. The power and flexibility of Linux extend beyond these commands. To progress, we recommend reading the `man` pages for each command and practicing regularly.

## Contact

If you have any questions, comments, or suggestions about **Linux Cheat sheet**, please feel free to contact me:

- LinkedIn: [Halil Ibrahim Deniz](https://www.linkedin.com/in/halil-ibrahim-deniz/)
- TryHackMe: [Halilovic](https://tryhackme.com/p/halilovic)
- Instagram: [deniz.halil333](https://www.instagram.com/deniz.halil333/)
- YouTube: [Halil Deniz](https://www.youtube.com/c/HalilDeniz)
- Email: halildeniz313@gmail.com


## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## 💰 You can help me by Donating
  Thank you for considering supporting me! Your support enables me to dedicate more time and effort to creating useful **Cheat Sheet** and developing new projects. By contributing, you're not only helping me improve existing tools but also inspiring new ideas and innovations. Your support plays a vital role in the growth of this project and future endeavors. Together, let's continue building and learning. Thank you!"<br>
[![BuyMeACoffee](https://img.shields.io/badge/Buy%20Me%20a%20Coffee-ffdd00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](https://buymeacoffee.com/halildeniz)
[![Patreon](https://img.shields.io/badge/Patreon-F96854?style=for-the-badge&logo=patreon&logoColor=white)](https://patreon.com/denizhalil) 
