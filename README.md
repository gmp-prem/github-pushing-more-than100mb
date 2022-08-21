# Pushing files with size more than 100MB on GitHub remote side
This repository is the tutorial on how to push files more than 100mb on GitHub using the tool Git LFS and GitHub desktop on Linux Ubuntu

This tutorial was provided to work on Linux Ubuntu and recommended to work with GitHub desktop which can be installed via
this [link](https://gist.github.com/berkorbay/6feda478a00b0432d13f1fc0a50467f1)

Git LFS will provide the ability to push files with more than 100mb on github, to perform that process

0. Install the Github Desktop

    0.1 download the Github desktop
    ```
    sudo wget https://github.com/shiftkey/desktop/releases/download/release-2.9.3-linux3/GitHubDesktop-linux-2.9.3-linux3.deb
    ```
    0.2 extract file
    ```
    tar -xf git-lfs-linux-amd64-v3.2.0.tar.gz 
    ```
    0.3 cd to your extracted files

    0.4 make the install bash script executable
    ```
    chmod 755 install.sh
    ```
    0.5 start installing from bash script
    ```
    sudo ./install.sh
    ```

1. Install the Git LFS

    1.1 install curl 
    ```
    sudo apt-get update && sudo apt-get install curl -y
    ```
    1.2 download the Github desktop
    ```
    curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.deb.sh | sudo bash
    ```

1. Create the remote and local repo and sync between two first. This step, the external Git GUI can be used to provide
easy access between remote side and local side

    **PS. the easiest way to work between the remote repo and the local repo is through the GitHub Desktop, which can be installed through the link mentioned above and give this repo's user a star !**

4. Init the Git LFS on the local side, after the repo on remote and local are created and synchronized
    ```
    git lfs install
    ```

5. Track the desired files
    ```
    git lfs track "yourfilename.py"
    ```
    ** or If wanna track entire file in the repo, use this, this will track all  source codes and folders in the local repo
    ```
    git lfs track *
    ```

6. Also track the .gitattributes, this hidden file is the file that stores which files you wanna track
    ```
    git add .gitattributes
    ```

7. In this step, we will staging the changes files, can add the single file
    ```
    git add yourfile.py
    ```
    ** or the entire local repo for the first commit, using this command
    ```
    git add *
    ```

8. Commit the added file(s)
    ```
    git commit -m "Manage files with Git LFS"
    ```

9. Push !
    ```
    git push origin main
    ```

PS. for the official link of Git LFS is [here](https://git-lfs.github.com/)
