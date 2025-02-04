---
title: Setup
---

::::::::::::::::::::::::::::::prereq

In this lesson we use Git from the Unix Shell. Some previous experience with the shell is expected, but isn’t mandatory.

::::::::::::::::::::::::::::::

## Computer

Participants must work on a computer with a Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) on which they have administrative privileges.

## Software Setup

To participate in this workshop, you will need to prepare the following (if you haven't already):

#### Install Shell and Git
   
:::tab

### Windows
For Windows, we only have to install Git, as we will use the Shell that comes with it.

Download the Git for Windows [installer](https://gitforwindows.org/). Then run the installer and follow the steps below:

   1. Click on "Next" four times (two times if you've previously installed Git). You don't need to change anything in the Information, location, components, and start menu screens.
   2. From the dropdown menu, "Choosing the default editor used by Git", select "Use the Nano editor by default" (NOTE: you will need to scroll up to find it) and click on "Next".
   3. On the page that says "Adjusting the name of the initial branch in new repositories", select "Override the default branch name for new repositories", ensure that the textbox says "main" and click on "Next".
   4. Ensure that "Git from the command line and also from 3rd-party software" is selected and click on "Next". (If you don't do this Git Bash will not work properly, requiring you to remove the Git Bash installation, re-run the installer and to select the "Git from the command line and also from 3rd-party software" option.)
   5. Select "Use bundled OpenSSH".
   6. Ensure that "Use the native Windows Secure Channel Library" is selected and click on "Next".
   7. Ensure that "Checkout Windows-style, commit Unix-style line endings" is selected and click on "Next".
   8. Ensure that "Use Windows' default console window" is selected and click on "Next".
   9. Ensure that "Default (fast-forward or merge) is selected and click "Next"
   10. Ensure that "Git Credential Manager" is selected and click on "Next".
   11. Ensure that "Enable file system caching" is selected and click on "Next".
   12. Click on "Install".
   13. Click on "Finish" or "Next".

To test if this has worked, you should be able to open the "Git Bash" program from your start menu. In the window that opens, type `git --version` and press Enter. The output should show something like this:

```bash
$ git --version
git version 2.47.0.windows.1
```

### Mac  
Most versions of MacOS will have git preinstalled, you can check by running:

```bash
$ git --version
```
If it is not available, you can install git through homebrew by running:

```bash
brew install git
``` 

### Linux
If Git is not already available on your machine you can install this package via your distro's package manager. Debian/Ubuntu run `sudo apt-get install git` and for Fedora run `sudo dnf install git`.

:::
  
#### Setup GitHub 

You will need an account for [GitHub](https://github.com/) to follow episodes 7, 8, 9 in this lesson.

1. To sign up for an account, navigate to https://github.com/ and follow the prompts.
2. Verify your email address.
3. Configure GitHub authentication.

You must authenticate before you can access certain resources on GitHub.
Each way of accessing GitHub supports different authentication method. For example, you can authenticate with GitHub via the command line using Secure Shell Protocol (SSH) or you can authenticate with GitHub via browser using two-factor authentication (2FA). In our lesson we shall use both.

:::tab

### SSH   

To set up SSH for your GitHub account, follow these steps:

1. Generate an SSH public/private keypair on your local machine if you don't already have one.

To check your local machine for existing SSH keys, run the following command in the terminal:

```bash
    ls -al ~/.ssh
```

Then check the directory listing to see if you already have a public SSH key. By default, the filenames of supported public keys for GitHub are one of the following.

```bash
    id_rsa.pub
    id_ecdsa.pub
    id_ed25519.pub
```

If you receive an error that ~/.ssh does not exist, you do not have an existing SSH key pair in the default location. You can create a new SSH key pair in the next step. If you do have an existing SSH key pair, you can skip the next step.

2. Generate a new SSH key.

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```
When you're prompted to "Enter a file in which to save the key", you can press Enter to accept the default file location. 

3. Add your SSH key to the ssh-agent.

```bash
# Start the ssh-agent in the background
eval "$(ssh-agent -s)"
# Add your SSH private key to the ssh-agent
ssh-add ~/.ssh/id_ed25519
```

4. Add SSH Key to GitHub Account

Finally, you need to add your SSH key to your GitHub account. To do this, you need to copy the SSH key to your clipboard. You can do this by running the following command:

```bash     
cat ~/.ssh/id_ed25519.pub
```

Then, copy the output to your clipboard. Next, navigate to your GitHub account settings, and click on SSH and GPG keys. Click on the New SSH key button, and paste your key into the Key field. Click Add SSH key to add your key to your GitHub account.

### 2FA 

To set up 2FA for your GitHub account, follow these steps:

1. If you already use an authenticator app, like [Google Authenticator](https://support.google.com/accounts/answer/1066447?hl=en&co=GENIE.Platform%3DiOS&oco=0) on your smartphone for example, add GitHub to that app.
2. If you have access to a smartphone but do not already use an authenticator app, install one and add GitHub to the app.
3. Optionally, you can add a passkey to your account. Passkeys are similar to security keys. However, passkeys satisfy both password and 2FA requirements, so you can sign in to your account in one step.

:::

:::callout

#### About passphrases for SSH keys

With SSH keys, if someone gains access to your computer, the attacker can gain access to every system that uses that key. To add an extra layer of security, you can add a passphrase to your SSH key, however it will require to enter passphrase **every time**. It is possible to avoid entering the passphrase every time you connect by means of securely saving your passphrase in the SSH agent. We recommend not dealing with passphrases in the scope of this lesson. 

:::

Refer to the GitHub [documentation](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/about-authentication-to-github) for more details about authentication.


#### Confirm that everything works

You should now be able to open a terminal window and execute the following commands:

#### Git

```bash
$ git --version
```
which will return (something similar to):

```bash
git version 2.34.1
```

#### Github access & SSH connection

```bash
ssh git@github.com
```

which will return:

```bashreturning
Hi [username]! You've successfully authenticated, but GitHub does not provide shell access.
Connection to github.com closed.
```

### If something does not work

Follow the corresponding setup instructions. If you still need help, send us an [email](mailto:training@esciencecenter.nl).
