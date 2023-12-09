# **Aircrack-ng: A Comprehensive Guide and Cheat Sheet**

<img src="../source/aircrack-ng.png"></img>


## Detailed Content:
1. **Switching Network Interface to Monitor Mode:**
   - `airmon-ng start [interface]`
     - This command switches the specified network interface to monitor mode, allowing it to capture all wireless traffic in the vicinity without connecting to a specific network. For example, `airmon-ng start wlan0` would put the wireless interface named 'wlan0' into monitor mode.
   - `airmon-ng check kill`
     - This command stops processes that could interfere with the wireless card's operation in monitor mode. For instance, executing `airmon-ng check kill` ensures that network managers or other processes do not hinder the monitoring process.


2. **Scanning for Wireless Networks:**
   - `airodump-ng [interface]`
     - This command lists nearby wireless networks and connected devices, providing essential information like BSSID, channel, and encryption type. For example, `airodump-ng wlan0mon` would display all wireless networks visible to the 'wlan0mon' interface.
   - `airodump-ng --band [a/b/g] [interface]`
     - This variation of the command allows scanning in a specific frequency band (a, b, or g) to narrow down the search. For instance, `airodump-ng --band a wlan0mon` would scan for networks only in the 5 GHz (band a) frequency range.


3. **Focusing on a Specific Network to Collect Data:**
   - `airodump-ng --bssid [BSSID] -c [channel] --write [file_name] [interface]`
     - This command targets a specific BSSID (wireless network identifier) and channel for data collection, storing the captured packets in a file. For example, using `airodump-ng --bssid 00:11:22:33:44:55 -c 6 --write output wlan0mon` will capture packets from the network with BSSID 00:11:22:33:44:55 on channel 6 and save them to a file named 'output'.
   - `airodump-ng --bssid [BSSID] --encrypt [WEP/WPA/WPA2] [interface]`
     - This variant allows filtering networks based on encryption type (WEP, WPA, or WPA2) along with BSSID. For instance, `airodump-ng --bssid 00:11:22:33:44:55 --encrypt WPA2 wlan0mon` will focus on capturing data from a WPA2 encrypted network with the specified BSSID.


4. **Attacking a WEP-Encrypted Network:**
   - `aireplay-ng --fakeauth 0 -a [BSSID] -h [MAC] [interface]`
     - This command performs a fake authentication to a WEP network using the specified BSSID and MAC address. For example, `aireplay-ng --fakeauth 0 -a 00:11:22:33:44:55 -h 66:77:88:99:AA:BB wlan0mon` simulates a client joining the network, necessary for certain types of attacks.
   - `aireplay-ng --arpreplay -b [BSSID] -h [MAC] [interface]`
     - This command increases network data traffic by sending ARP (Address Resolution Protocol) requests. Increased traffic generates more IVs (Initialization Vectors), which are essential for cracking WEP. For instance, `aireplay-ng --arpreplay -b 00:11:22:33:44:55 -h 66:77:88:99:AA:BB wlan0mon` targets a specific network to accelerate data capture.
   - `aircrack-ng [file_name].cap`
     - This final step uses the collected data in the '.cap' file to crack the WEP key. For instance, executing `aircrack-ng captured_data.cap` will analyze the captured packets and attempt to derive the WEP key, leveraging any vulnerabilities in the WEP encryption.


5. **Attacking a WPA/WPA2 Encrypted Network:**
   - `aireplay-ng --deauth [number] -a [BSSID] -c [target MAC] [interface]`
     - This command forces a target device to disconnect from a WPA/WPA2 network by sending deauthentication packets. For example, `aireplay-ng --deauth 100 -a 00:11:22:33:44:55 -c 66:77:88:99:AA:BB wlan0mon` will send 100 deauth packets to disconnect a device with MAC 66:77:88:99:AA:BB from the network with BSSID 00:11:22:33:44:55.
   - `aircrack-ng -w [dictionary_file] [file_name].cap`
     - This command attempts a dictionary attack against the WPA/WPA2 password using the captured handshake data. For instance, using `aircrack-ng -w wordlist.txt captured_handshake.cap` will try to match the network password against the words in 'wordlist.txt' using the data in 'captured_handshake.cap'. This method's success largely depends on the strength of the dictionary file and the complexity of the network password.


## Advanced Usage:

### 6. **Packet Injection and Complex ARP Attacks:**

Packet Injection and Advanced ARP (Address Resolution Protocol) Attacks are sophisticated techniques used in network penetration testing to test the resilience of wireless networks against active security breaches.

**Packet Injection:**
- **Purpose:** Packet injection involves injecting arbitrary packets into a network. This can be used to provoke responses from the network or to initiate a connection with a network without legitimate credentials.
- **Example Command:** 
  - `aireplay-ng --inject [number] -a [BSSID] [interface]`
  - This command injects a specified number of packets into a network with a given BSSID. For example, `aireplay-ng --inject 100 -a 00:11:22:33:44:55 wlan0mon` would inject 100 packets into the target network.

**Complex ARP Attacks:**
- **Purpose:** These attacks involve generating a large number of ARP requests to flood the network, leading to a rapid increase in data packets that can be used to crack network encryption.
- **Example Command:**
  - `aireplay-ng --arpreplay -b [BSSID] -h [MAC] [interface] --fast`
  - This variation of the ARP replay attack is more aggressive, generating ARP requests at a faster rate. For example, `aireplay-ng --arpreplay -b 00:11:22:33:44:55 -h 66:77:88:99:AA:BB wlan0mon --fast` will perform a rapid ARP request flood on the specified network.


### 7. **PTW Attack (Pyshkin, Tews, Weinmann Attack):**

The PTW Attack, named after its developers - Pyshkin, Tews, and Weinmann, is an advanced method for cracking WEP encryption. It significantly reduces the number of data packets required to decrypt a WEP key, making the attack faster and more efficient.

**Overview of the PTW Attack:**
- **Purpose:** This attack specifically targets the vulnerabilities in the WEP encryption algorithm. It is more efficient than traditional WEP cracking methods as it requires fewer initialization vectors (IVs) to successfully crack the WEP key.
- **Working Principle:** The PTW attack exploits weaknesses in the RC4 cipher used by WEP. It uses statistical methods to analyze captured packets and deduce the encryption key with fewer packets than traditional methods.

**Implementation in Aircrack-ng:**
- **Aircrack-ng Integration:** The PTW attack is integrated into Aircrack-ng, allowing users to employ this method without needing separate software.
- **Example Command:**
  - `aircrack-ng -z [file_name].cap`
  - The `-z` option in Aircrack-ng triggers the PTW attack. For instance, executing `aircrack-ng -z captured_data.cap` will initiate the PTW attack on the captured data in the file 'captured_data.cap'.


### 8. **Capturing WPA/WPA2 Handshakes and Advanced Cracking Techniques:**

This section delves into the methods for capturing WPA/WPA2 handshakes and employing advanced techniques to crack these more secure encryption standards.

**Capturing WPA/WPA2 Handshakes:**
- **Purpose:** A handshake capture is crucial for attempting to crack WPA/WPA2 encrypted networks. It contains the information needed to attempt a password crack.
- **Method:**
  - **Example Command:**
    - `airodump-ng --bssid [BSSID] -c [channel] --write [file_name] [interface]`
    - This command is used to monitor a specific network and capture the handshake when a device connects to the network. For instance, `airodump-ng --bssid 00:11:22:33:44:55 -c 6 --write handshake wlan0mon` would capture the handshake of the network with the specified BSSID and channel.

**Advanced Cracking Techniques:**
- **Dictionary Attack:**
  - A common method using a list of potential passwords to find the correct one.
  - **Example Command:**
    - `aircrack-ng -w [dictionary_file] [file_name].cap`
    - This command uses the captured handshake file with a dictionary file to attempt cracking the WPA/WPA2 password.
- **Rainbow Table Attack:**
  - This involves using precomputed hash tables to speed up the cracking process, particularly effective against networks with weak passwords.
- **Brute Force Attack:**
  - This method attempts all possible password combinations, which can be time-consuming but effective for short or simple passwords.


### 9. **Hybrid Attacks and Dictionary Generation:**

Hybrid attacks combine different methods, typically dictionary and brute force attacks, to crack network passwords more effectively. Dictionary generation, on the other hand, focuses on creating customized wordlists for use in these attacks.

**Hybrid Attacks:**
- **Overview:** Hybrid attacks utilize a combination of brute force and dictionary methods. They often start with a dictionary attack and then switch to brute force tactics for the parts of the password not covered by the dictionary.
- **Method:**
  - **Example Command:**
    - `aircrack-ng -w [dictionary_file] --bssid [BSSID] [file_name].cap`
    - This command uses a dictionary file along with brute forcing techniques on a captured handshake file to crack the password. It offers a more nuanced approach than relying solely on one method.

**Dictionary Generation:**
- **Purpose:** Custom dictionaries increase the chances of successfully cracking a password. These dictionaries are tailored to include likely passwords based on known information about the network or its users.
- **Tools and Techniques:**
  - **Wordlist Tools:** Tools like `crunch`, `John the Ripper`, or `CeWL` can be used to generate custom wordlists based on specific criteria.
  - **Social Engineering:** Information gathered through social engineering can inform the creation of a more effective dictionary.

### 12. **Crack with John The Ripper:**

John The Ripper is a powerful and widely used password cracking tool. It is particularly effective for offline password cracking, making it a valuable addition to a penetration tester's toolkit.

**Usage:**
- **Installation:** Ensure you have John The Ripper installed on your system.
- **Command:** Use the following command to initiate password cracking:
  - `john --wordlist=wordlist.txt --format=md5 hashes.txt`
- **Options:** Customize the cracking process with various options and flags.
- **File:** Specify the file containing password hashes to be cracked.

**Advanced Features:**
- **Wordlist Attack:** John The Ripper supports wordlist-based attacks, where it systematically tests a list of potential passwords.
- **Brute Force Attack:** It can also perform brute force attacks, trying all possible password combinations.
- **Rules and Variations:** John The Ripper allows you to apply custom rules and variations to increase the chances of success.

### 10. **Additional Tips:**
   - Always operate within legal limits. Aircrack-ng should only be used on networks where you have permission for testing purposes.
   - Use a comprehensive dictionary file for an effective dictionary attack.
   - Be mindful of heavy traffic and attacks that might affect network performance.


## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, feel free to open an issue or submit a pull request.

## Contact

If you have any questions, comments, or suggestions about **Aircrack-Ng Cheat sheet**, please feel free to contact me:

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

  