# Week 1 Assignment: Getting Started

In this assignment, you will be setting up your local development environment, creating the accounts that you need to use throughout the semester, and configuring access to these accounts so that you can work with them programmatically! 

Everyone’s local development (dev) environment will be slightly different. You’ll find the tools that work best for you as you progress throughout your career! This dev environment set up is designed to help us have minimal variation during the class so that bugs are easier to fix, and help is easier to provide. 

If you follow all of these instructions, you should have everything you need to get started on next week’s assignment, and hit the ground running. 

If you come from a more technical background, and have already formed strict opinions and preferences about your dev environment, you are welcome to use the tooling that you prefer. That said, should you run into issues related to your dev environment, the MIS547 Instructor and TAs will not provide assistance. 

<aside>
💡 The deliverables for this assignment are:

</aside>

<aside>
💡 Definition of Done:
1. Installed homebrew or choclatey [ ]
2. Installed Docker desktop [ ]
3. Installed python, pyenv, and poetry [ ]
4. Installed VSCode [ ]
5. Set up a GitHub account [ ]
6. Created an AWS Account [ ]
7. Created a GCP Account [ ]
8. Created an Azure Account [ ]
9. Created a DigitalOcean Account [ ]
10. Created a Slack Account [ ]
11. Installed git and set your email address and username [ ]
12. Cloned the Week 1 repository [ ]
13. Joined the MIS547 Slack [ ]

</aside>

# Part 1: Setting up Your Local Development Environment

## Step 1: Install a system package manager

What is a system package manager? System package managers allow us to manage software that isn’t packaged as an executable. Rather than visiting a software vendor’s website (for example, Microsoft VSCode), and downloading some software that we then install using our operating system’s user interfaces (UIs) or graphical user interfaces (GUIs), system package managers let us use software that is designed to run from a command line interface (CLI). 

For more about CLIs, see this explanation here. 

If you are using MacOS, you will use [Homebrew](https://brew.sh/) as your system package manager. If you are using Windows, you will use [Chocolatey](https://chocolatey.org/) as your system package manager. 

### MacOS

1. Open a terminal or shell prompt of your choosing. 
    
    You can open a terminal by going to the looking glass icon in the top right of your desktop (this is called a SpotlightSearch), selecting it, and then typing “terminal”, and hitting enter. 
    
    Hint: When your terminal launches, in the dock that shows all of your running programs, “right” click (two-finger click) on terminal, select options, and then select “Keep in Dock.” This will pin terminal to dock so you never have to search for it again. 
    
2. Copy and paste the following line into your terminal and then hit enter

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Windows

1. Open an administrative shell 
    
    You can open a shell by selecting the Windows icon, then searching for ‘Powershell’ 
    
    When the powershell icon appears, right click on it and then choose ‘Run as administrator’ .
    
    A User Account Control dialog will open and ask if you’re sure if you want to run as administrator. Select “Yes”.
    
    Another way of launching an administrative shell is to use the Run dialog. Press Windows+R to open the run dialog. Type `ps` into the box and then press CTRL+SHIFT+ENTER to run the command. This will launch PowerShell with admin privileges. 
    
2. The next thing we need to do is make sure we can use PowerShell in the way we want to. Run the following command:

```powershell
Get-ExecutionPolicy
```

Check the output of this command. If it returns `Restricted` , then run the following:

```powershell
Set-ExecutionPolicy AllSigned
```

Now, run the following command:

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

If you don’t see any errors, you’re ready to use Choclatey 🙂

Type the following to ensure that Chocolatey is installed:

```powershell
choco
```

## Step 2: Install Docker Desktop

### MacOS

Visit the following URL: [https://docs.docker.com/desktop/install/mac-install/](https://docs.docker.com/desktop/install/mac-install/) and follow the applicable installation instructions depending on the kind of mac you have. (Hint: if you have an M1-M3 chip, you’ll want to install Docker Desktop for Mac with Apple silicon). Otherwise, install Docker Desktop for Mac with Intel Chip.

You can confirm that docker is installed by running

```bash
open -a Docker
```

### Windows

1. First, you need to install something called the Windows Subsytem for Linux. 
    
    Open a Powershell prompt in administrative mode ([see the instructions in Step 1](https://www.notion.so/Week-1-Assignment-Getting-Started-8ada3cb6d2414bcba6afa1ca71344ced?pvs=21))
    
    Now, run:
    

```powershell
wsl --install
```

1. Download and Install Docker Desktop
    1. Visit this webpage to download the Docker desktop package: [https://docs.docker.com/desktop/install/windows-install/](https://docs.docker.com/desktop/install/windows-install/)
    2. When it downloads, double click on the installer
    3. When prompted ensure that the “Use WSL2 instead of Hyper-V” option on the configuration page is selected.
    4. Follow the instructions on the installation wizard.
    5. When successful, close to complete the install process.
2. Lastly, if your admin account on your computer is different to your user account (this is common if you are borrowing a computer from the library, for example), you need to add your user account to the docker-users group.
    1. Open the Run dialog
    2. Search for Computer Management
    3. There is a tab called “Local Users and Groups”. Click on Groups, and then right click on “docker-users”
    4. Add your user account to the docker users group.
    5. Sign out and sign back in for changes to take effect.

## Step 3: Set Up Important Python Dev Tools

1. First, we’ll install pyenv. We’ll use pyenv to install and manage different python versions!

We’ll use Momebrew (MacOS) and Chocolately (Windows) to install pyenv

### MacOS

```bash
brew install pyenv
```

### Windows

```powershell
choco install pyenv-win
```

1. Now, let’s use pyenv to install Python v. 3.12.2

### MacOS or Windows

```bash
pyenv install -v 3.12.1
```

You can see which versions of python are locally available by typing:

```bash
pyenv versions
```

3. Now, we’ll install poetry, a python package manager that makes it a lot more straightforward to check dependencies and avoid dependency hell. 

### MacOS

```bash
brew install poetry
```

### Windows

```bash
curl -sSL https://install.python-poetry.org | python3 -
```

Once Poetry is installed and in your path, you can check that you can use poetry by running:

```bash
poetry --version
```

## Step 5: Download and install the latest versions of Git

[https://git-scm.com/downloads](https://git-scm.com/downloads)

Set your username in git: [https://docs.github.com/en/get-started/getting-started-with-git/setting-your-username-in-git](https://docs.github.com/en/get-started/getting-started-with-git/setting-your-username-in-git)

Set your email address in git: [https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-email-preferences/setting-your-commit-email-address](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-email-preferences/setting-your-commit-email-address)

If you would like to tour git and GitHub more thoroughly before we get going, check out their great documentation [here](https://skills.github.com/)

## Step 4: Install VSCode

We’ll be using VSCode throughout the semester for our projects. If you prefer a different IDE, that’s awesome, but just know that if you run into issues with your non-VSCode IDE specifically, we will not be able to help you troubleshoot. 

1. Install VSCode:
    1. Navigate to [https://code.visualstudio.com/download](https://code.visualstudio.com/download) and select the appropriate download for your operating system. 
    2. Once VSCode is downloaded, install it using the installation wizard. 
    3. Launch VSCode 
2. Next, we’ll install some VSCode extensions that will come in handy throughout the semester
    1. [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
    2. [Remote](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh)
    3. [Terraform](https://marketplace.visualstudio.com/items?itemName=HashiCorp.terraform)
    4. [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
    5. [Docker extension](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)

# Part 2: Create Accounts

## Step 1: Set up a GitHub account

1. If you don’t already have a GitHub account, create one [here](https://github.com/signup)
2. Sign up for the GitHub student developer pack by joining the GitHub global campus program [here](https://www.notion.so/Week-1-Assignment-Getting-Started-8ada3cb6d2414bcba6afa1ca71344ced?pvs=21)
3. Personalize your profile by following the instructions [here](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/customizing-your-profile/personalizing-your-profile)
4. Create a new repository in your GitHub account
5. Add access token and save it in your config

## Step 2: Create accounts on AWS, GCP, Azure, DO, and DockerHub using your GitHub student developer pack

1. AWS Directions: 
    1. https://docs.aws.amazon.com/accounts/latest/reference/manage-acct-creating.html
2. GCP Directions: 
    1. About GCP for Students :https://support.google.com/google-cloud-higher-ed/answer/10324788?hl=en&ref_topic=10322095&sjid=2512220335938741820-NC
    2. Link for requesting:  https://cloud.google.com/edu/students?hl=en
3. Azure Directions: 
    1. https://azure.microsoft.com/en-gb/pricing/offers/ms-azr-0144p/
4. DigitalOcean Directions: 

## Step 3: Create an account on DockerHub

1. DockerHub directions

## Step 4: Create a Slack account

1. Create a Slack Account
    1. Slack directions
    2. Join the MIS547 Fall 2024 Slack Channel 

## Step 4: Set up your local project directory

This is just a recommendation of how to structure your project directories for this class. You can of course use whatever structure you’d like to, this is supposed to be a helpful guide for organizing your tasks. 

### MacOS

1. Start in your home directory
2. Create a directory called MIS547 by typing the following in a terminal or command prompt:
    
    ```bash
    mkdir MIS547
    ```
    
3. Now, enter into that directory by typing the following:
    
    ```bash
    cd MIS547
    ```
    
4. In that folder, create a directory for week 1
    
    ```bash
    mkdir week1
    ```
    

### Windows

## Step 5: Clone the Week 1 repository from the MIS547 Organization into your week1 directory

1. Link to Repository
2. 

By selecting the following checkmarks, I attest that I have followed the instructions and have confirmed that I can do or did the following.