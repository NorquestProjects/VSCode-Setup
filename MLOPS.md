<!-- <p align = "center" draggable=”false” ><img src="link to image here" 
     width="200px"
     height="auto"/>
</p> -->



## <h1 align="center" id="heading">:wave: Welcome to MLOPS!!</h1>

Welcome to the beginning of your journey to deploying Machine Learning Models! 🎉 Follow these steps to get your development environment teed up! 


## :books: Quick Review
We will be using some terminal commands, so let's make sure you know what they are and what they do! 

| Command      | Stands For |  Description |
| ----------- | ----------- | -------------|
| `ls`      | long listing       | lists all files and directories in the present working directory |
| `ls -a`  | long listing all   |  lists hidden files as well |
| `cd {dirname}`      | change directory       | to change to a particular directory |
| `cd ~`   | change directory home        | navigate to HOME directory |
| `cd ..`      | change directory up       | move one level up |
| `cat {filename}`   | concatenate        | displays the file content |
| `sudo`      | superuser       | allows regular users to run programs with the security privileges of the superuser or root |
| `mv {filename} {newfilename}`   | move        | renames the file to new filename |
| `clear`      | clear       | clears the terminal screen |
| `mkdir {dirname}`   | make directory        | create new directory in present working directory or at specified path |
| `rm {filename}`   | remove        | remove file with given filename |
| `touch {filename}.{ext}`   | touch        | create new empty file |
| `rmdir {dirname}`   | remove directory        | deletes a directory |
| `ssh {username}@{ip-address} or {hostname}`   | secure shell        | login into a remote Linux machine using SSH |

<p></p>

## :hammer_and_wrench: Tools We'll Be Using
We will also be using a few tools such as `git`, `conda`, and `pip`.
<details>
<summary>Git</summary>

Git is a free and open source distributed version control system designed to handle everything from small to very large projects. These are the commands we will be using with `git`:

`git clone` -> clone a remote repository to your local computer

`git add` -> add files to a commit

`git commit -m {message}` -> commit changes with a message

`git push` -> push commit to remote repository
</details>

<details>
<summary>Conda & Pip</summary>

Conda is an open-source, cross-platform, language-agnostic package manager and environment management system. We will use `pip` within `conda` environments to manage our package installations. `pip` is Python's package management system. `conda` comes with Anaconda. And Anaconda is a convenient way to set up your Python programming environment since it comes with an enviornment management tool (`conda`) and comes with extra packages that are commonly used in data science and ML.

Some commands we will use in this lesson when it comes to `conda` and `pip`:

`conda create --name mlops-course python=3.8 pip` -> This creates a virtual environment. A virtual environment is a Python environment such that the Python interpreter, libraries, amnd scripts installed into it are isolated from those installed on other environments and any libraries installed on the system. So basically, this allows you to keep all your project's code/dependencies/libraries separated from other projects. You are specifically saying to create said environment with the name `mlops-course`, use `python` version 3.8, and use `pip` as your package manager. The command `conda` invokes the underlying logic to actually make the virtual environment and manages said environments for you.

`conda activate mlops-course` -> This activates the virtual environment you made with the above command for your current terminal session.

`pip install numpy pandas matplotlib jupyter` -> This installs the four packages mentioned - `numpy`, `pandas`, `jupyter` and `matplotlib`. `numpy` is used for scientific computing, `pandas` is used for data analysis, and `matplotlib` is used for data graphics. `jupyter` is discussed later in this tutorial in depth! `pip` is the Python package manager and you are telling it to `install` the listed packages to your environment.
</details>

<p></p>

## :rocket: Let's Get Started! 
Let's start off by setting up our environment!  Review the environment setup instructions for the local environment that you'll be using in this course.
<details>
  <summary>Windows</summary>


* Install [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install) using Powershell

```powershell
wsl --install -d Ubuntu-20.04
```
* Install [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab) (You can even make it your [default!](https://devblogs.microsoft.com/commandline/windows-terminal-as-your-default-command-line-experience/))
* Install [Ubuntu](https://www.microsoft.com/en-us/p/ubuntu/9pdxgncfsczv?activetab=pivot:overviewtab)

* Make sure you've install the correct version with the command `wsl -l -v`
    
(If you find yourself getting stuck on the WSL2 install, [here](https://www.youtube.com/watch?v=VMZH9Pj2dXw&ab_channel=StefanRows) is a link to video instructions)

Give it a test drive! 

![WindowsTerminal](https://user-images.githubusercontent.com/72572922/160048214-37f08855-8b29-4c13-9d25-e0f69806f752.jpg)

Continue by installing the following tools using [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab) to setup your environment. When prompted, make sure to add `conda` to `init`.

| Tool | Purpose | Command                                                                                           |
| :-------- | :-------- | :------------------------------------------------------------------------------------------------ |
| :snake: **Anaconda**  | Python & ML Toolkits | `wget https://repo.anaconda.com/archive/Anaconda3-2021.11-Linux-x86_64.sh` <br> `bash Anaconda3-2021.11-Linux-x86_64.sh` <br> `source ~/.bashrc` |
| :octocat: **Git**  | Version Control | `sudo apt update && sudo apt upgrade` <br> `sudo apt install git-all`   |
| :memo: **VS Code** | Development Environment | [Download](https://code.visualstudio.com/download) |

</details>

<details>
  <summary>Linux (Debian/Ubuntu)</summary>

Open terminal using <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>T</kbd>. Enter the following commands in terminal to setup your environment. When prompted, make sure to add `conda` to `init`.
| Tool | Purpose | Command                                                                                           |
| :-------- | :-------- | :------------------------------------------------------------------------------------------------ |
| :snake: **Anaconda**  | Python & ML Toolkits | `wget https://repo.anaconda.com/archive/Anaconda3-2021.11-Linux-x86_64.sh` <br> `bash Anaconda3-2021.11-Linux-x86_64.sh` <br> `source ~/.bashrc` |
| :octocat: **Git**  | Version Control | `sudo apt update && sudo apt upgrade` <br> `sudo apt install git-all`   |
| :memo: **VS Code** | Development Environment | [Download](https://code.visualstudio.com/download) |

</details>

<details>
  <summary>macOS</summary>

To get started, we need to download the MacOS package manager, <strong>Homebrew</strong> :beer:, so that we can download the tools we'll be using in the course. If you don't already have Homebrew installed, run the following commands:

1. Open terminal using <kbd>⌘</kbd>+<kbd>Space</kbd> and type `terminal`.

2. Install Homebrew using the command below, following the command prompts:

    `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"` 

3. Update Homebrew (This may take a few minutes)

    `git -C /usr/local/Homebrew/Library/Taps/homebrew/homebrew-core fetch --unshallow`

    `git -C /usr/local/Homebrew/Library/Taps/homebrew/homebrew-cask fetch`
     
4. Install the `wget` command to continue following along
     `brew install wget`

Enter the following commands in terminal to setup your environment. When prompted, make sure to add `conda` to `init`.

| Tool | Purpose | Command                                                                                           |
| :-------- | :-------- | :------------------------------------------------------------------------------------------------ |
| :snake: **Anaconda**  | Python & ML Toolkits | `wget https://repo.anaconda.com/archive/Anaconda3-2021.11-MacOSX-x86_64.sh` <br> `bash Anaconda3-2021.11-MacOSX-x86_64.sh` <br> `source ~/.bashrc` |
| :octocat: **Git**  | Version Control | `brew install git`   |
| :memo: **VS Code** | Development Environment | [Download](https://code.visualstudio.com/download) |

</details>

<p></p>


## <img src="https://upload.wikimedia.org/wikipedia/commons/f/f3/Visual_Studio_Code_0.10.1_icon.png" height=40px/> Let's configure our VS Code environment!

<details>
  <summary>Install the IntelliCode Extension</summary>

  IntelliCode is an AI-powered code completion extension to boost coding productivity. :sunglasses:

  1. Click the `Extensions` <img src="images/vscode_extensions_tab.png" width=30px/> tab in the navigation panel on the left side of VS Code. 

  2. Type "IntelliCode" in the search bar.

  3. Click `install` <img src="images/vscode_install.png" width=30px/> on the <ins><strong>Microsoft IntelliCode Extension</strong></ins>

</details>

<details>
  <summary>Install the Jupyter Notebook Extension</summary>

  1. Click the `Extensions` <img src="images/vscode_extensions_tab.png" width=30px/> tab on the left side of the window.

  2. Type "Python" in the search bar.

  3. Click `Install` <img src="images/vscode_install.png" width=30px/>  on the <ins><strong>Microsoft Jupyter Notebook Extension</strong></ins>

</details>

<details>
  <summary>Set the Python Interpreter</summary>

  1. Open VS Code and click on `New File...`

  2. Open the Command Pallette 
    <strong>(Mac: </strong></ins> <kbd>Shift</kbd><kbd>⌘</kbd>+<kbd>P</kbd> 
    ,<strong> Windows: </strong></ins> <kbd>Ctrl</kbd>+<kbd>P</kbd>)

  3. Type "Python" in the search bar.

  4. Click on `New Python File`

  5. Open the Command Pallette again.  Can you remember the shortcut?  If    not, see #2 above again.

  6. Type "Python Interpreter".

  7. Click on `Python: Select Interpreter`

  8. Select the `Conda` environment that you installed earlier. 
  
  <p align = "center" draggable=”false”>
  <img src="images/vscode_mlops_interpreter.png"> 
  </p>

  9. Now you're ready to start coding!

</details>

<p> </p>

## <img src="https://octodex.github.com/images/original.png" width=40px/> Let's Make Sure That GitHub is Ready to Roll!

If you don't already have one, make an account on [Github](https://github.com/)!  

<details>
  <summary>Github SSH Setup</summary>
  Secure Shell Protocol (SSH) provides a secure communication channel of an unsecured network.  Let's set it up!
  
  <p></p>

  1. Generate a Private/Public SSH Key Pair.
    
  ```console
  ssh-keygen -o -t rsa -C "your email address for github"
  ```

  2. Save file pair.  Default location `~/.ssh/id_rsa` is fine! 
  

  3. At the prompt, type in a secure passphrase.
  4. Copy the contents of the public key that we will share with GitHub. 

     * Mac: `pbcopy < ~/.ssh/id_rsa.pub` 

     * Windows (WSL): `clip.exe < ~/.ssh/id_rsa.pub`
     Note: Your key should be in a Publisher file named id_rsa.pub. Open the publisher file as a notepad to view.

     * Linux: `xclip -sel c < ~/.ssh/id_rsa.pub`
  
  5. Go to your GitHub account and go to `Settings`. 
  
  6. Under `Access`, click on the `SSH and GPG keys` tab on the left.

  ![Access Section](images/github_access_section.png)

  7. Click on the `New SSH Key` button.
  
  ![New SSH Key](images/github_new_ssh_key.png)
  
  8. Name the key, and paste the public key that you copied. Click the `Add SSH Key` button
  

  ![Add SSH Key](images/github_add_ssh_key.png)

</details>

<details>
  <summary>Viewing the Repositories</summary>

Login and click on the top right user icon, then go to `repositories`. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/37101144/162326947-3bfb4451-9854-41e8-9014-a02ed1322d66.png">
</p>
</details>


<details>
  <summary>Creating a New Repository</summary>

When viewing the respository page, click on `New` and proceed to create your repo.

<p align="center">
  <img src="https://user-images.githubusercontent.com/37101144/162327218-e1429ab2-2b24-4822-95bf-4411c2eb4a84.png">
</p>
<hr>

**Filling Respository Details**

Create the repository by inputting the following:
* `Repo name`
* `Repo description`
* Make repo `public`
* Add a `README`
* Add `.gitignore` (Python template)
* Add `license` (choose MIT)

Then click `Create Repository`.

<p align="center">
  <img src="https://user-images.githubusercontent.com/37101144/162327471-262a0931-c188-4976-8185-e70c4d108f71.png">
</p>

</details>

<details>

<summary>Clone Your Repo</summary>

  1. Open your terminal and navigate to a place where you would like to make a directory to hold all your files for this class using the command `cd`. 


  ```console
  cd {directory name}
  ```
  
  2. Once there, make a top level directory using `mkdir`. 

  ```console
  mkdir {directory name}
  ```

  3. `cd` into it and make another directory called `code`. 

  ```console
  cd {directory name}
  ```

  ```console
  mkdir code
  ```

  4. `cd` into it and run your `git clone {your repo url}` command. 

  ```console
  cd code
  ```

  ```console
  git clone {your repo url}
  ```

</details>

<details>
  
### That's it for now!  And so it begins.... :)
