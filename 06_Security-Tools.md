# 6. **Security Tools**
   - **Encryption:**
     - `gpg --gen-key` – Generate a new GPG key for encryption.
     - `gpg --encrypt <file>` – Encrypt a file.
     - `gpg --decrypt <file.gpg>` – Decrypt a file.
   - **Firewall:**
     - `sudo ufw enable` – Enable Uncomplicated Firewall (UFW).
     - `sudo ufw status` – Displays the status of UFW.
     - `sudo ufw allow <port>` – Allows a specific port.
     - `sudo ufw deny <port>` – Denies a specific port.
   - **File Integrity:**
     - `sha256sum <file>` – Generates the SHA-256 hash of a file.
     - `md5sum <file>` – Generates the MD5 hash of a file (less secure).
   - **Auditing:**
     - `auditctl -l` – Displays active audit rules.
     - `ausearch -m avc` – Searches audit logs for access control violations.
   - **Cracking Tools:**
     - `john` – John the Ripper password cracking tool.
     - `hydra` – Brute-force login cracker for many services.