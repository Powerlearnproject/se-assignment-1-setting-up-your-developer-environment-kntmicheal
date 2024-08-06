
1. Operating System: Windows 11 (Version 22H1)

            Detailed Setup:
            - Download the Windows 11 ISO from the Microsoft website
            - Create a bootable USB using the Media Creation Tool
            - Boot from the USB and begin installation
            - Choose "Custom: Install Windows only (advanced)"
            - Select the drive for installation and format if necessary
            - Follow on-screen instructions to complete installation
            - After installation, open Windows Update and install all available updates
            - Configure basic settings:
            - Enable Windows Defender
            - Set up Windows Hello for biometric login
            - Configure privacy settings according to your preferences
            - Install necessary drivers (graphics, network, etc.)

2. Text Editor / IDE: Visual Studio Code 
Detailed Setup:
            - Download VS Code installer from code.visualstudio.com
            - Run the installer, selecting the following options:
            - Add "Open with Code" action to Windows Explorer file context menu
            - Add "Open with Code" action to Windows Explorer directory context menu
            - Register Code as an editor for supported file types
            - Add to PATH
            - Launch VS Code
            - Install extensions:
            - Python (ms-python.python)
            - GitLens (eamodio.gitlens)
            - MySQL (cweijan.vscode-mysql-client2)
            - Docker (ms-azuretools.vscode-docker)
            - Prettier (esbenp.prettier-vscode)
            - ESLint (dbaeumer.vscode-eslint)
            - Configure settings:
            - Enable Auto Save: File > Auto Save
            - Set up format on save: 
                1. Open settings (Ctrl+,)
                2. Search for "format on save"
                3. Check the box for "Editor: Format On Save"

3. Version Control: Git  and GitHub

            Detailed Setup:
            - Download Git for Windows from git-scm.com
            - Run the installer with these options:
            - Select components: 
                - Git Bash Here
                - Git GUI Here
                - Git LFS (Large File Support)
                - Associate .git* configuration files with the default text editor
                - Associate .sh files to be run with Bash
            - Choose the default editor (e.g., Visual Studio Code)
            - Let Git decide the default branch name
            - Adjust your PATH environment: Git from the command line and also from 3rd-party software
            - Use the OpenSSL library
            - Checkout Windows-style, commit Unix-style line endings
            - Use MinTTY
            - Default pull behavior: Fast-forward or merge
            - Use Git Credential Manager
            - Enable file system caching
            - Enable symbolic links

GitHub Setup:
            - Go to github.com and create an account
            - Verify your email address
            - Set up two-factor authentication:
            - Go to Settings > Security > Two-factor authentication
            - Choose between SMS or authenticator app method
            - Generate an SSH key:
            - Open Git Bash
            - Run: `ssh-keygen -t ed25519 -C "your_email@example.com"`
            - Add the SSH key to your GitHub account:
                - Copy the contents of ~/.ssh/id_ed25519.pub
                - On GitHub, go to Settings > SSH and GPG keys > New SSH key
                - Paste your key and save

Initialize Git Repository:
- Open your project folder in Git Bash
- Run: `git init`
                - Create a .gitignore file:
                ```
                # Python
                __pycache__/
                *.py[cod]
                *$py.class
                venv/

                # VS Code
                .vscode/

                # Database
                *.sqlite3

                # Environment variables
                .env

                # Logs
                *.log
                ```
            - Make your first commit:
            ```
            git add .
            git commit -m "Initial commit: Project setup and .gitignore"
            ```
            - Create a new repository on GitHub
            - Link your local repository:
            ```
            git remote add origin git@github.com:yourusername/your-repo-name.git
            git branch -M main
            git push -u origin main
            ```

4. Programming Language: Python (Version 3.10.10)

            Detailed Setup:
            - Download Python 3.10.10 installer from python.org
            - Run the installer, selecting:
            - Install launcher for all users (recommended)
            - Add Python 3.10 to PATH
            - Customize installation
                - Optional Features: select all
                - Advanced Options:
                - Install for all users
                - Associate files with Python
                - Create shortcuts for installed applications
                - Add Python to environment variables
                - Precompile standard library
            - Open Command Prompt to verify installation: `python --version`
            - Update pip: `python -m pip install --upgrade pip`

5. Package Manager: pip and virtualenv

            Detailed Setup:
            - Verify pip installation: `pip --version`
            - Install virtualenv: `pip install virtualenv`
            - Create a project directory: `mkdir my_project && cd my_project`
            - Create a virtual environment: `python -m venv venv`
            - Activate the virtual environment:
            - On Windows: `venv\Scripts\activate`
            - Create a requirements.txt file for your project dependencies
            - Install project dependencies: `pip install -r requirements.txt`

6. Database: MySQL (Version 8.0.33)

            Detailed Setup:
            - Download MySQL Installer from dev.mysql.com
            - Run the installer, choosing:
            - Developer Default (includes MySQL Server, Workbench, Shell, and Python Connector)
            - Follow the installation wizard:
            - Choose "Standalone MySQL Server"
            - Set root password
            - Configure Windows Service: MySQL80, Start at System Startup
            - After installation, open MySQL Workbench
            - Create a new connection:
            - Connection Name: LocalInstance
            - Hostname: 127.0.0.1
            - Port: 3306
            - Username: root
            - Test the connection to verify it's working

7. Virtualization: Docker Desktop (Version 4.18.0)

                Detailed Setup:
                - Enable Hyper-V and Windows Subsystem for Linux 2 (WSL 2):
                - Open PowerShell as Administrator
                - Run: `dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart`
                - Run: `dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart`
                - Restart your computer
                - Download and install the WSL 2 Linux kernel update package
                - Download Docker Desktop installer from docker.com
                - Run the installer, choosing:
                - Enable Hyper-V Windows Features
                - Use WSL 2 instead of Hyper-V
                - After installation, start Docker Desktop
                - Open PowerShell and verify installation: `docker --version`

8. Additional VS Code Extensions and Configurations

                Detailed Setup:
                - Install additional extensions:
                - Live Server (ritwickdey.liveserver)
                - Code Spell Checker (streetsidesoftware.code-spell-checker)
                - Configure Python linting:
                - Open VS Code settings (Ctrl+,)
                - Search for "python linting"
                - Enable pylint
                - Set up code formatting:
                - Install Black: `pip install black`
                - In VS Code settings, set "Python › Formatting: Provider" to "black"
                - Enable format on save for Python files

Challenges faced in installation

Python Path Configuration

            Challenge: Python not recognized in Command Prompt after installation.
            Solution:

            Ensure "Add Python to PATH" was selected during installation
            Manually add Python to the system PATH:

            Search for "Environment Variables" in Windows search
            Edit the PATH variable
            Add entries for Python installation directory and Scripts folder

Virtual Environment Issues

        Challenge: Difficulty in creating or activating virtual environments.
        Solution:

        Ensure virtualenv is installed: pip install virtualenv
        Check if the virtual environment is created in the correct directory
MySQL Connection Problems

        Challenge: Unable to connect to MySQL server after installation.
        Solution:

        Verify MySQL service is running in Windows Services
        Check if the correct port (usually 3306) is being used
        Ensure firewall is not blocking MySQL connections