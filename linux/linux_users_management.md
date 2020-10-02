# Linux Users Management:

## Creating new user in RedHat/Amazon Linux and login the server via new user:
1. To add a new user to the system:
      Use `adduser` command and followed by the name of the user you wish to create.
      Example: `sudo adduser admin`
2. To Switch the new user:
      `sudo su admin`
3. To Connect server via admin user:
      First we want to create a “.ssh” folder in users home
      `cd ~`
      `mkdir .ssh`
4. Change the file permissions of the `.ssh` directory to `700` (this means only the file owner can read, write, or open the directory).
      `chmod 700 .ssh`
5. Create a file named `authorized_keys` in the `.ssh` directory.
      `touch .ssh/authorized_keys`
6. Change the file permissions of the `authorized_keys` file to `600` (this means only the file owner can read or write to the file)
      `chmod 600 .ssh/authorized_keys`
7. Generate a new key-pair in your local computer by using the following command.
      `ssh-keygen -f admin`
8. When you create a key-pair it will generate two keys public Key and private key, public key is for you to login to the server and private key is deployed in `.ssh/authorized_keys`
9. Save that public key in `.ssh/authorized_keys` file
10. Now try to login to the admin user with admin private key(Open git bash where you generated key-pairs).
      `ssh -i admin admin@public-ip/public-dns`