
- Issue"1": [Broken Sudo Due to Sudoers Syntax Error](#%EF%B8%8Fissue1-broken-sudo-due-to-sudoers-syntax-error)


  ##### ⚠️Issue"1": Broken Sudo Due to Sudoers Syntax Error
  If your sudo is broken due to a bad /etc/sudoers file, and you're getting errors like:
  
  ```visudo```\
  ```!#saiful ALL=(ALL) ALL```\
  ``` visudo -cf /etc/sudoers ```\
  ``` cp /etc/sudoers /etc/sudoers.bak ```
  
  ```sh
  >>> /etc/sudoers: syntax error near line XX <<<
  sudo: parse error in /etc/sudoers near line XX
  sudo: no valid sudoers sources found, quitting
  sudo: unable to initialize policy plugin
  ```
  - Recommended Fix (Safe):
    - Boot from a Live ISO or Recovery Disk.
    - Login using root credentials
    - Make confirm another root access terminal login before visudo added.
