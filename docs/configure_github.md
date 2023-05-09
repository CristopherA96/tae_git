# Configure Github


## GitHub authentication
---

There are some ways to configure GitHub account to be able to clone or create a repository:

- **Personal Token:** only applies for HTTPS.
- **SSH key:** applies for SSH remote URL.

!!! info
    Both options assume you have your `git` configured.

### SSH
---

<div style="text-align: justify">
The most common way to authenticate to GitHub is using <u>SSH keys</u>, because using <u>personal tokens</u> means that when the token expires you have to create another one and that becomes tedious. Therefore, ssh keys are a better option for authentication, since as long as the key is active it will not ask you to enter your username or password every time you want to interact with GitHub.
</div>

#### Create SSH key
---

!!! example
    Check if ssh-keygen is installed
    ```yaml
        $ which ssh-keygen                                  ; # Verify you have ssh-keygen package, if not:
        $ sudo apt install openssh-client                   ; # Install openssh package
    ```
    ```yaml
        ; # 1. CREATE SSH KEY

        $ ssh-keygen -t ed25519 -C "your_github_email@email_provider.com"          ; # Option 1: using ed25519 algorithm (Recommended)
        # or
        $ ssh-keygen -t rsa -b 4096 -C "your_github_email@email_provider.com"      ; # Option 2. using RSA with 4096 bits for security

            ; # It will show you information like the following
        
                Generating public/private <rsa,ed25519> key pair.
                Enter file in which to save the key (/home/<your_user>/.ssh/id_rsa): <path-with-different-keyname>
                Enter passphrase (empty for no passphrase): <type-pass>
                Enter same passphrase again: <type-pass>
        
        ; # 2. ADD SSH KEY TO ssh-agent
        
        $ eval '$(ssh-agent -s)'                                                    ; # Start SSH agent in background
            ; # It will show you information like the following
                Agent pid <id>
        
        $ ssh-add ~/.ssh/<keyname>                                                  ; # Add your SSH private key to ssh-agent
    ```
!!! warning
    If this is your first time adding a key to GitHub, you can use any encryption algorithm that your system supports, but if you already had keys added and they are of type `RSA` you should delete everything about that key with GitHub in the `known_hosts` file or update `SHA-1` to `SHA-2`. This is due to problems that were found with that type of algorithm on GitHub, which will prevent you from getting the `Error: Permission denied (publickey)`.

#### Add SSH key to GitHub
---

The steps to add SSH key are:

1. Go to <a href="https://github.com/" target="_blank" rel="noopener">GitHub</a>.
2. **Sign in** if you haven't already.
3. In the top right corner of the page, click on your profile picture, then **Settings**.
4. Click on SSH and GPG keys.
5. Click on New SSH key.
6. Add a descriptive title for your SSH key.
7. Choose Authentication Key.
8. In terminal: `cat ~/.ssh/<keyname>.pub`, and copy-paste output in **Key** section.
9. Add SSH key.

<center>
    <figure markdown>
        ![ssh](){ width="500" }
        <figcaption>**Figure 1:** Window to add your <u>public SSH key</u> information..</figcaption>
    </figure>
</center>







    