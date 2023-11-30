# **APT and APT-GET in Linux Package Management Cheat Sheet**

<img src="../source/apt-get-cheat-sheet.png"></img>


#### **Basic Concepts**:
- **APT (Advanced Package Tool)**: High-level package management tool.
- **APT-GET**: Lower-level command-line tool, part of APT.

#### **Common Commands**:

1. **Update Package Index**:
   - `apt update`: A crucial command that refreshes the local package index. It ensures that you have the latest package listings before any installation or upgrade.
   - `apt-get update`: Functionally identical to `apt update`, it's the traditional approach to refreshing the package database.

2. **Upgrade Packages**:
   - `apt upgrade`: This command smartly upgrades all the packages on your system to their latest versions, considering and resolving dependencies.
   - `apt-get upgrade`: Similar in function, it's more script-friendly for automated upgrades.

3. **Install Packages**:
   - `apt install [package-name]`: A straightforward way to add new software to your system.
   - `apt-get install [package-name]`: Equally effective, often preferred in scripts due to its predictable output.

4. **Remove Packages**:
   - `apt remove [package-name]`: Removes the binaries of a package but retains configuration files, which can be useful for temporary removals.
   - `apt-get remove [package-name]`: Mirrors the functionality of `apt remove`.

5. **Purge Packages**:
   - `apt purge [package-name]`: Goes a step further by removing both binaries and configuration files, essentially wiping the package from your system.
   - `apt-get purge [package-name]`: Offers the same thorough removal.

6. **Search for Packages**:
   - `apt search [query]`: An intuitive way to search through the repository for specific software.
   - `apt-cache search [query]`: Leverages the `apt-cache` tool for searching, offering more detailed search capabilities.

7. **Show Package Information**:
   - `apt show [package-name]`: Provides detailed insights into a package, including its version, dependencies, size, and description.
   - `apt-cache show [package-name]`: Similar to `apt show` but can offer more technical details.

8. **List Installed Packages**:
   - `apt list --installed`: A quick way to review all the software currently installed on your system.
   - `dpkg -l`: Uses the `dpkg` tool, providing a more detailed and technical listing of installed packages.

9. **Autoremove Unneeded Packages**:
   - `apt autoremove`: Cleans up your system by removing packages that were installed as dependencies and are no longer needed.
   - `apt-get autoremove`: Identical in function, ensuring your system isn't cluttered with unnecessary packages.

10. **Clean Up Downloaded Package Files**:
    - `apt clean`: Frees up space by deleting downloaded package files from the local repository.
    - `apt-get clean`: Performs the same cleaning operation, ensuring efficient use of disk space.

### Understanding `/etc/apt/sources.list` in APT Management

11. **Managing the Sources List (`/etc/apt/sources.list`)**:
    - **Function**: The `/etc/apt/sources.list` file is a vital configuration file in the APT system. It dictates where APT looks for software packages, specifying the repositories from which packages can be retrieved.
    - **Structure**: This file contains a list of 'sources' or 'repositories', each specified by a line that typically includes the type of the repository, its URL, the distribution (like `stable`, `testing`, or a specific version name for Ubuntu like `focal`), and the repository sections (like `main`, `contrib`, `non-free`).
    - #### **Example Entry**:
      ```
      deb http://us.archive.ubuntu.com/ubuntu/ focal main restricted
      ```
      - `deb`: Denotes a binary repository.
      - `http://us.archive.ubuntu.com/ubuntu/`: The URL of the repository.
      - `focal`: The distribution version.
      - `main restricted`: The sections within the repository.
    - **Editing the File**: To add, remove, or modify repositories, you need to edit this file. It's recommended to make a backup before editing. Use a text editor like `nano` or `vi` with superuser privileges (e.g., `sudo nano /etc/apt/sources.list`).
    - **Updating Sources**: After modifying the `sources.list` file, run `apt update` to refresh the package lists based on the new repositories.

### The Role of `/etc/apt/sources.list`

- **Software Availability**: The repositories listed in `sources.list` determine what software is available to your system through APT.
- **Software Updates and Upgrades**: The versions and updates of software that APT can install depend on the repositories specified in this file.
- **Security**: Official repositories are typically well-maintained and secure. Adding third-party repositories can offer additional software but may also pose security risks, so they should be added with caution.
- **Customization**: By editing `sources.list`, you can customize the sources of your software, which is particularly useful for adding software that's not available in the default repositories or for accessing earlier or later versions of some packages.

### Differences Between `apt` and `apt-get`:
- `apt` is more user-friendly and intended for end-users, while `apt-get` is more robust and suited for scripts.
- `apt` provides a progress bar during package installations and upgrades, which `apt-get` does not.
- `apt` combines the most commonly used commands from `apt-get` and `apt-cache`.

### General Tips:
- Always run `apt update` or `apt-get update` before installing or upgrading packages to ensure you have the latest information.
- Use `apt` for everyday package management tasks for its simplicity and ease of use.
- Prefer `apt-get` in scripts for backward compatibility and its predictable behavior.


## **Conclusion**
Both APT and APT-GET are integral to managing software in Debian and Ubuntu-based Linux distributions. While APT offers a more streamlined and user-friendly experience, APT-GET remains vital for scripting and automation. Understanding these tools and their commands is essential for efficient software management in Linux environments.


## Contact

If you have any questions, comments, or suggestions about **AWS Cheat sheet**, please feel free to contact me:

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

  