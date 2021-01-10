# SSH Into Termux (SSHD)
Scripts and notes for setting up and using SSHd on your Android device using Termux so that you can SSH, SFTP, and SSHFS to your Android

# On your AndroidOS device 
  Install Termux (https://termux.com/)
  
  Launch Termux
  
  Enter these commands (In Android)
  
     > apt update 
     
     > apt upgrade
     
     > termux-setup-storage
     
     > apt install openssh
     
     > touch ~/.ssh/authorized_keys
     
     > chmod 600 ~/.ssh/authorized_keys
     
     > chmod 700 ~/.ssh
     
     > ssh-keygen
     
     > cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
     
     > chmod 600 ~/.ssh/authorized_keys
	 	 
In your remote device 

     ssh-keygen ( if you don't already have a ssh key-pair )
     
     cat id_rsa.pub
    
copy everything from the output and send it to Android Device now the content needs to be pasted into `~/.ssh/authorized_keys` inside termux.
Now do `sshd` in termux to start the server.

# To SSH into Android from the Remote Host

   Type this command from within a Terminal

     > ssh -p 8022 IPofYourAndroid 

# To SFTP into Android from the Remote Host

  Type this command from within a Terminal

    > sftp -P 8022 IPofYourAndroid 
    
## References
(https://github.com/tomhiggins/TermuxSSHDsetup)
