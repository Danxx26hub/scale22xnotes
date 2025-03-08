# scale22xnotes
notes from scale

https://chatgpt.com/share/67ca18db-e168-8006-9484-d800e294d092


The version available from MX Linux’s default repositories (and therefore via apt-get) is tied to the underlying Debian release, which is why you’re seeing Podman 3.x. A recommended way to get a newer version (such as 5.x) is to install it from the official Kubic repository maintained by the libcontainers project. This repository is designed to provide more up-to-date packages for Podman on Debian‑based systems.

Below are the typical steps you can follow (adjusting for your base Debian version if needed):

1. **Add the Kubic Repository**  
   Create a new file (e.g. `/etc/apt/sources.list.d/devel:kubic:libcontainers:stable.list`) and add the following line. For MX Linux 21.3 (based on Debian Bullseye), use:  
   ```bash
   echo "deb http://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/Debian_11/ /" | sudo tee /etc/apt/sources.list.d/devel:kubic:libcontainers:stable.list
   ```

2. **Import the GPG Key**  
   Download and add the repository’s GPG key so that your system can verify the packages:  
   ```bash
   wget -nv https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/Debian_11/Release.key -O Release.key
   sudo apt-key add - < Release.key
   ```

3. **Update and Install Podman**  
   Finally, update your package lists and install Podman:  
   ```bash
   sudo apt-get update
   sudo apt-get install podman
   ```

This method should give you access to the more current version (5.x) of Podman compared to the older version available from MX Linux’s default repositories.

> Note: Always verify the repository URL and instructions against the [official Podman installation documentation](https://podman.io/getting-started/installation) or the Kubic repo page in case there are updates or changes for your specific Debian base version.


# Running LLM locally talk


* LLM a subset of Genarative AI 
   a. Generates something new.
   b. LLM's are text based and deal with words / languages
   c. Are Probablistic. based on probability (Anticipates what you are going to say next)

* Privacy & Security
   a. No Data leaves your machine / network.
   b. Sensitive data / info stays under your control
   c. Every LLM is vulnerable to Jailbreaking & prompt injection.
   d. Model Bias and poisining.


