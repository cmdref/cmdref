# 🚀 Ultimate CLI Command Cheatsheet
┌─[✓]─[user@terminal]─[~/cmd-ref]
└──╼ $ figlet "CMD REF"

  ██████╗███╗   ███╗██████╗     ██████╗ ███████╗███████╗
 ██╔════╝████╗ ████║██╔══██╗    ██╔══██╗██╔════╝██╔════╝
 ██║     ██╔████╔██║██║  ██║    ██████╔╝█████╗  █████╗  
 ██║     ██║╚██╔╝██║██║  ██║    ██╔══██╗██╔══╝  ██╔══╝  
 ╚██████╗██║ ╚═╝ ██║██████╔╝    ██║  ██║███████╗██║     
  ╚═════╝╚═╝     ╚═╝╚═════╝     ╚═╝  ╚═╝╚══════╝╚═╝     

 > Your Ultimate Command Line Reference Guide 🚀
 > Master the terminal with this comprehensive cheatsheet
>
>
>
```bash
┌─[✓]─[user@terminal]─[~/cheatsheet]
└──╼ $ echo "Welcome to CLI Mastery!"

    ██████╗██╗     ██╗     ███╗   ███╗ █████╗ ███████╗████████╗███████╗██████╗ ██╗   ██╗
   ██╔════╝██║     ██║     ████╗ ████║██╔══██╗██╔════╝╚══██╔══╝██╔════╝██╔══██╗╚██╗ ██╔╝
   ██║     ██║     ██║     ██╔████╔██║███████║███████╗   ██║   █████╗  ██████╔╝ ╚████╔╝ 
   ██║     ██║     ██║     ██║╚██╔╝██║██╔══██║╚════██║   ██║   ██╔══╝  ██╔══██╗  ╚██╔╝  
   ╚██████╗███████╗██║     ██║ ╚═╝ ██║██║  ██║███████║   ██║   ███████╗██║  ██║   ██║   
    ╚═════╝╚══════╝╚═╝     ╚═╝     ╚═╝╚═╝  ╚═╝╚══════╝   ╚═╝   ╚══════╝╚═╝  ╚═╝   ╚═╝   

    > Your comprehensive guide to command line domination 🔥
    > From basic navigation to advanced system administration
```

---

## 📚 Table of Contents

- [🚀 Terminal Basics](#-terminal-basics)
- [📁 Files & Directories](#-files--directories)
- [📝 Text Processing](#-text-processing)
- [⚙️ System Information](#️-system-information)
- [🌐 Network Commands](#-network-commands)
- [🔀 Git Commands](#-git-commands)
- [🐳 Docker Commands](#-docker-commands)
- [⌨️ Keyboard Shortcuts](#️-keyboard-shortcuts)
- [🎯 Advanced Tips](#-advanced-tips)

---

## 🚀 Terminal Basics

```bash
# Navigation Essentials
pwd                    # Print working directory
cd /path/to/directory  # Change directory
cd ..                  # Go up one level
cd ~                   # Go to home directory
cd -                   # Go to previous directory

# Listing Files
ls -la                 # List all files (detailed + hidden)
ls -lh                 # Human readable file sizes
ls -lt                 # Sort by modification time
tree                   # Display directory structure
```

<details>
<summary><b>🎯 Pro Navigation Tips</b></summary>

```bash
# Quick Directory Navigation
pushd /path            # Save current dir and change
popd                   # Return to saved directory
dirs -v                # Show directory stack

# Fuzzy Finding (if fzf installed)
cd $(find . -type d | fzf)  # Interactive directory selection
```
</details>

---

## 📁 Files & Directories

### File Operations
```bash
# Creating & Copying
touch filename.ext     # Create empty file
cp source dest         # Copy file
cp -r dir1 dir2        # Copy directory recursively
mv old_name new_name   # Move/rename file

# Deleting (⚠️ BE CAREFUL!)
rm filename            # Delete file
rm -rf directory/      # Delete directory and contents
```

### Finding Files
```bash
# Find by name
find . -name "*.txt"           # Find all .txt files
find . -iname "*.PDF"          # Case insensitive search
find . -type f -name "*config*" # Find files with 'config' in name

# Find by size
find . -size +100M             # Files larger than 100MB
find . -size -1k               # Files smaller than 1KB

# Find by date
find . -mtime -7               # Modified in last 7 days
find . -atime +30              # Accessed more than 30 days ago
```

<details>
<summary><b>🔍 Advanced Find Examples</b></summary>

```bash
# Execute commands on found files
find . -name "*.log" -exec rm {} \;     # Delete all .log files
find . -name "*.py" -exec wc -l {} \;   # Count lines in Python files

# Modern alternatives
fd filename                             # Faster alternative to find
locate filename                         # Quick search using database
```
</details>

---

## 📝 Text Processing

### Viewing Files
```bash
cat filename           # Display entire file
less filename          # Paginated view (better for large files)
head -20 filename      # First 20 lines
tail -20 filename      # Last 20 lines
tail -f filename       # Follow file changes (perfect for logs!)
```

### Searching in Files
```bash
# Grep - The Search Master
grep "pattern" file              # Basic search
grep -r "pattern" directory/     # Recursive search
grep -i "pattern" file           # Case insensitive
grep -n "pattern" file           # Show line numbers
grep -v "pattern" file           # Invert match (exclude pattern)
grep -E "pattern1|pattern2" file # Multiple patterns (extended regex)
```

### Text Manipulation
```bash
# Sorting & Filtering
sort filename          # Sort lines alphabetically
sort -n filename       # Sort numerically
sort -r filename       # Reverse sort
uniq filename          # Remove duplicates (requires sorted input)
sort file | uniq -c    # Count occurrences

# Counting & Statistics
wc filename            # Word, line, character count
wc -l filename         # Count lines only
wc -w filename         # Count words only
```

<details>
<summary><b>⚡ Power User Text Commands</b></summary>

```bash
# Stream Editor (sed)
sed 's/old/new/g' file         # Replace all occurrences
sed 's/old/new/gi' file        # Replace (case insensitive)
sed -n '1,10p' file            # Print lines 1-10
sed '/pattern/d' file          # Delete lines matching pattern

# AWK - Programming Language for Text
awk '{print $1}' file          # Print first column
awk -F',' '{print $2}' file    # Use comma as delimiter
awk 'NR>1 {print}' file        # Skip header line

# Modern Alternatives
rg "pattern"                   # ripgrep - faster grep
bat filename                   # Better cat with syntax highlighting
```
</details>

---

## ⚙️ System Information

### Process Management
```bash
# Viewing Processes
ps aux                 # List all processes
ps aux | grep process  # Find specific process
top                    # Real-time process viewer
htop                   # Better interactive process viewer
pgrep process_name     # Find process ID by name

# Killing Processes
kill PID               # Terminate process by ID
kill -9 PID            # Force kill process
killall process_name   # Kill all processes by name
pkill -f pattern       # Kill processes matching pattern
```

### System Resources
```bash
# Memory & Storage
free -h                # Memory usage (human readable)
df -h                  # Disk space usage
du -sh directory/      # Directory size
du -h --max-depth=1    # Size of subdirectories

# System Information
uname -a               # System information
uptime                 # System uptime and load
lscpu                  # CPU information
lsblk                  # List block devices
```

### File Permissions
```bash
# Viewing Permissions
ls -l filename         # Show file permissions

# Changing Permissions (Octal notation)
chmod 755 file         # rwxr-xr-x
chmod 644 file         # rw-r--r--
chmod +x script.sh     # Make executable

# Ownership
chown user:group file  # Change ownership
sudo chown -R user:group directory/  # Recursive ownership change
```

<details>
<summary><b>🔧 System Monitoring Commands</b></summary>

```bash
# Advanced System Monitoring
iostat -x 1            # I/O statistics every second
vmstat 1               # Virtual memory statistics
netstat -tuln          # Network connections
ss -tuln               # Modern alternative to netstat
lsof -i :80            # Show what's using port 80

# Service Management (systemd)
systemctl status service_name     # Check service status
systemctl start service_name      # Start service
systemctl enable service_name     # Enable service at boot
```
</details>

---

## 🌐 Network Commands

### Connectivity Testing
```bash
# Basic Network Diagnostics
ping google.com        # Test connectivity
ping -c 4 google.com   # Send only 4 packets
traceroute google.com  # Trace route to destination
mtr google.com         # Continuous traceroute

# DNS Lookup
nslookup domain.com    # Basic DNS lookup
dig domain.com         # Detailed DNS information
dig @8.8.8.8 domain.com # Use specific DNS server
```

### Network Information
```bash
# Interface Information
ifconfig               # Network interface configuration
ip addr show           # Show IP addresses (modern)
ip route show          # Show routing table

# Network Connections
netstat -tuln          # Show listening ports
ss -tuln               # Modern alternative (faster)
lsof -i                # Show network connections by process
```

### File Transfer
```bash
# Download Files
curl -O url            # Download file
curl -L url            # Follow redirects
wget url               # Alternative downloader
wget -c url            # Resume download

# Secure Transfer
scp file user@host:/path      # Copy file over SSH
rsync -av source/ dest/       # Sync directories
rsync -av --progress src/ dst/ # Show progress
```

<details>
<summary><b>🌐 Advanced Network Tools</b></summary>

```bash
# Network Analysis
tcpdump -i eth0                    # Capture packets
nmap -sP 192.168.1.0/24           # Scan network for hosts
nc -zv hostname 80                # Check if port is open

# HTTP Testing
curl -X POST -d "data" url        # POST request
curl -H "Header: value" url       # Custom header
curl -w "%{http_code}" url        # Show HTTP status code
```
</details>

---

## 🔀 Git Commands

### Repository Setup
```bash
# Initialize & Clone
git init               # Initialize new repository
git clone url          # Clone remote repository
git remote add origin url        # Add remote
git remote -v          # Show remotes
```

### Basic Workflow
```bash
# Status & Changes
git status             # Show working tree status
git diff               # Show unstaged changes
git diff --staged      # Show staged changes

# Staging & Committing
git add .              # Stage all changes
git add filename       # Stage specific file
git commit -m "message"          # Commit with message
git commit -am "message"         # Stage and commit
```

### Branching & Merging
```bash
# Branch Management
git branch             # List branches
git branch new-branch  # Create new branch
git checkout branch-name         # Switch branch
git checkout -b new-branch       # Create and switch
git merge branch-name  # Merge branch
git branch -d branch-name        # Delete branch
```

### Remote Operations
```bash
# Sync with Remote
git push origin main   # Push to remote
git pull origin main   # Pull from remote
git fetch origin       # Fetch without merge
git push -u origin branch        # Push and set upstream
```

<details>
<summary><b>🔥 Advanced Git Operations</b></summary>

```bash
# History & Information
git log --oneline      # Compact commit history
git log --graph        # Show branch graph
git show commit-hash   # Show commit details
git blame filename     # Show who changed each line

# Undoing Changes
git reset --soft HEAD~1    # Undo last commit (keep changes)
git reset --hard HEAD~1    # Undo last commit (discard changes)
git revert commit-hash     # Create new commit that undoes changes

# Stashing
git stash              # Temporarily save changes
git stash pop          # Apply and remove stash
git stash list         # List all stashes
```
</details>

---

## 🐳 Docker Commands

### Container Management
```bash
# Running Containers
docker run image       # Run container
docker run -it image bash        # Interactive container
docker run -d -p 8080:80 image   # Detached with port mapping

# Container Operations
docker ps              # List running containers
docker ps -a           # List all containers
docker stop container_id         # Stop container
docker rm container_id           # Remove container
docker exec -it container_id bash # Execute command in container
```

### Image Management
```bash
# Image Operations
docker images          # List images
docker pull image:tag  # Download image
docker build -t name . # Build image from Dockerfile
docker rmi image_id    # Remove image
docker system prune    # Clean up unused resources
```

### Docker Compose
```bash
# Compose Operations
docker-compose up      # Start services
docker-compose up -d   # Start in background
docker-compose down    # Stop and remove containers
docker-compose logs    # View logs
docker-compose ps      # List services
```

<details>
<summary><b>🐋 Advanced Docker Commands</b></summary>

```bash
# Debugging & Inspection
docker logs container_id           # View container logs
docker inspect container_id       # Detailed container info
docker stats                       # Real-time resource usage
docker top container_id            # Running processes in container

# Volume Management
docker volume ls                   # List volumes
docker volume create volume_name   # Create volume
docker run -v volume_name:/path image # Mount volume

# Network Management
docker network ls                  # List networks
docker network create network_name # Create network
```
</details>

---

## ⌨️ Keyboard Shortcuts

### Essential Terminal Shortcuts
```bash
# Process Control
Ctrl + C               # Kill current process
Ctrl + Z               # Suspend process (use 'fg' to resume)
Ctrl + D               # Exit shell or end input

# Navigation & Editing
Ctrl + A               # Move to beginning of line
Ctrl + E               # Move to end of line
Ctrl + U               # Clear line before cursor
Ctrl + K               # Clear line after cursor
Ctrl + L               # Clear screen
Ctrl + R               # Search command history
```

### History & Completion
```bash
# Command History
!!                     # Repeat last command
!n                     # Repeat command number n
!string                # Repeat last command starting with string
history                # Show command history

# Tab Completion
Tab                    # Complete command/filename
Tab Tab                # Show all possible completions
```

<details>
<summary><b>⚡ Pro Terminal Shortcuts</b></summary>

```bash
# Advanced Navigation
Alt + B                # Move back one word
Alt + F                # Move forward one word
Ctrl + W               # Delete word before cursor
Alt + D                # Delete word after cursor

# Process Management
Ctrl + S               # Pause output
Ctrl + Q               # Resume output
jobs                   # List active jobs
fg %1                  # Bring job 1 to foreground
bg %1                  # Send job 1 to background
```
</details>

---

## 🎯 Advanced Tips

### Command Chaining
```bash
# Logical Operators
command1 && command2   # Run command2 if command1 succeeds
command1 || command2   # Run command2 if command1 fails
command1 ; command2    # Run command2 regardless

# Pipes & Redirection
command | grep pattern # Pipe output to grep
command > file         # Redirect output to file
command >> file        # Append output to file
command 2>&1           # Redirect stderr to stdout
```

### Aliases & Functions
```bash
# Creating Aliases (add to ~/.bashrc or ~/.zshrc)
alias ll='ls -la'
alias la='ls -A'
alias ..='cd ..'
alias grep='grep --color=auto'

# Useful Custom Aliases
alias h='history'
alias c='clear'
alias df='df -h'
alias free='free -h'
alias ps='ps aux'
```

### Environment Variables
```bash
# Viewing Variables
env                    # Show all environment variables
echo $PATH             # Show PATH variable
echo $HOME             # Show home directory

# Setting Variables
export VAR_NAME=value  # Set environment variable
export PATH=$PATH:/new/path    # Add to PATH
```

<details>
<summary><b>🚀 Power User Combinations</b></summary>

```bash
# One-Liners for Common Tasks
find . -name "*.log" -mtime +7 -delete    # Delete old log files
ps aux | grep -v grep | grep process      # Find process without grep in results
du -sh */ | sort -h                       # Directory sizes sorted
netstat -tuln | grep :80                  # Check if port 80 is listening

# Monitoring Shortcuts
watch -n 1 'ps aux | grep process'       # Monitor process every second
tail -f /var/log/syslog | grep ERROR     # Monitor errors in real-time
```
</details>

---

## 🔥 Quick Reference Cards

### File Permissions Octal Chart
```
7 = rwx (read, write, execute)
6 = rw- (read, write)
5 = r-x (read, execute)
4 = r-- (read only)
3 = -wx (write, execute)
2 = -w- (write only)
1 = --x (execute only)
0 = --- (no permissions)
```

### Common Port Numbers
```
22  - SSH
80  - HTTP
443 - HTTPS
3306 - MySQL
5432 - PostgreSQL
6379 - Redis
27017 - MongoDB
```

### Exit Codes
```
0   - Success
1   - General error
2   - Misuse of shell command
126 - Command not executable
127 - Command not found
130 - Script terminated by Ctrl+C
```

---

## 📚 Resources & Further Learning

```bash
# Built-in Help
man command            # Manual page for command
command --help         # Help for command
info command           # Info documentation
which command          # Location of command
type command           # Command type information
```

### Recommended Tools
- **fzf** - Fuzzy finder for files and commands
- **ripgrep (rg)** - Faster grep alternative
- **bat** - Better cat with syntax highlighting
- **htop** - Interactive process viewer
- **fd** - Simple, fast alternative to find
- **exa** - Modern ls replacement

---

## 🤝 Contributing

Found a useful command that's missing? Have a better way to do something? 

1. Fork this repository
2. Add your commands following the existing format
3. Submit a pull request

Let's make this the ultimate CLI reference together! 🚀

---

## ⭐ Star This Repository

If this cheatsheet helped you become a command line ninja, please give it a star! ⭐

```bash
┌─[✓]─[user@terminal]─[~/cheatsheet]
└──╼ $ echo "Happy hacking! 🔥"

    > Remember: With great power comes great responsibility
    > Always double-check destructive commands (especially rm -rf)
    > When in doubt, use man pages or --help
    > Practice makes perfect - keep exploring!
```

---

<div align="center">

**Made with ❤️ and ☕ by developers, for developers**

[![GitHub stars](https://img.shields.io/github/stars/yourusername/cli-cheatsheet?style=social)](https://github.com/yourusername/cli-cheatsheet)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

</div>








# ⭐ cmdref — The Terminal Awakens
plese ignore this is just a test
<font color="orange">Orange text here</font>
<font color="#ff00ff">Magenta text</font>

![C](https://img.shields.io/badge/C-00ff66?style=for-the-badge)
![M](https://img.shields.io/badge/M-00ff66?style=for-the-badge)
![D](https://img.shields.io/badge/D-00ff66?style=for-the-badge)
&nbsp;&nbsp;
![R](https://img.shields.io/badge/R-ff0033?style=for-the-badge)
![E](https://img.shields.io/badge/E-ff0033?style=for-the-badge)
![F](https://img.shields.io/badge/F-ff0033?style=for-the-badge)

![C](https://img.shields.io/badge/C-00ff66?style=for-the-badge&labelColor=000000&color=000000)
![M](https://img.shields.io/badge/M-00ff66?style=for-the-badge&labelColor=000000&color=000000)
![D](https://img.shields.io/badge/D-00ff66?style=for-the-badge&labelColor=000000&color=000000)
&nbsp;&nbsp;
![R](https://img.shields.io/badge/R-00ff66?style=for-the-badge&labelColor=ffffff&color=ffffff)
![E](https://img.shields.io/badge/E-00ff66?style=for-the-badge&labelColor=ffffff&color=ffffff)
![F](https://img.shields.io/badge/F-00ff66?style=for-the-badge&labelColor=ffffff&color=ffffff)

<pre style="background:#000; color:#00ff66; padding:5px; line-height:0.5;">
 .----------------.  .----------------.  .----------------.   .----------------.  .----------------.  .----------------. 
| .--------------. || .--------------. || .--------------. | | .--------------. || .--------------. || .--------------. |
| |     ______   | || | ____    ____ | || |  ________    | | | |  _______     | || |  _________   | || |  _________   | |
| |   .' ___  |  | || ||_   \  /   _|| || | |_   ___ `.  | | | | |_   __ \    | || | |_   ___  |  | || | |_   ___  |  | |
| |  / .'   \_|  | || |  |   \/   |  | || |   | |   `. \ | | | |   | |__) |   | || |   | |_  \_|  | || |   | |_  \_|  | |
| |  | |         | || |  | |\  /| |  | || |   | |    | | | | | |   |  __ /    | || |   |  _|  _   | || |   |  _|      | |
| |  \ `.___.'\  | || | _| |_\/_| |_ | || |  _| |___.' / | | | |  _| |  \ \_  | || |  _| |___/ |  | || |  _| |_       | |
| |   `._____.'  | || ||_____||_____|| || | |________.'  | | | | |____| |___| | || | |_________|  | || | |_____|      | |
| |              | || |              | || |              | | | |              | || |              | || |              | |
| '--------------' || '--------------' || '--------------' | | '--------------' || '--------------' || '--------------' |
 '----------------'  '----------------'  '----------------'   '----------------'  '----------------'  '----------------' 

                                                     
 _______ _______ _______     _______ _______ _______ 
|\     /|\     /|\     /|   |\     /|\     /|\     /|
| +---+ | +---+ | +---+ |   | +---+ | +---+ | +---+ |
| |   | | |   | | |   | |   | |   | | |   | | |   | |
| |C  | | |M  | | |D  | |   | |R  | | |E  | | |F  | |
| +---+ | +---+ | +---+ |   | +---+ | +---+ | +---+ |
|/_____\|/_____\|/_____\|   |/_____\|/_____\|/_____\|
                                                     

 ____ ____ ____ _________ ____ ____ ____ 
||C |||M |||D |||       |||R |||E |||F ||
||__|||__|||__|||_______|||__|||__|||__||
|/__\|/__\|/__\|/_______\|/__\|/__\|/__\|
 
┌───────┐ ┌───────┐ ┌───────┐   ┌───────┐ ┌───────┐ ┌───────┐
│   C   │ │   M   │ │   D   │   │   R   │ │   E   │ │   F   │
└───────┘ └───────┘ └───────┘   └───────┘ └───────┘ └───────┘

   _|_|_|  _|      _|  _|_|_|    _|_|_|                  _|_| 
_|        _|_|  _|_|  _|    _|  _|    _|    _|_|      _|     
_|        _|  _|  _|  _|    _|  _|_|_|    _|_|_|_|  _|_|_|_| 
_|        _|      _|  _|    _|  _|    _|  _|          _|     
  _|_|_|  _|      _|  _|_|_|    _|    _|    _|_|_|    _|     
 
</pre>
.-------. .-------. .-------.   .-------. .-------. .-------.
|   C   | |   M   | |   D   |   |   R   | |   E   | |   F   |
'-------' '-------' '-------'   '-------' '-------' '-------'

<pre style="background:#000; color:#00ff66; padding:10px; font-weight:bold; text-shadow: 0 0 8px #00ff66;">
┌───────┐ ┌───────┐ ┌───────┐   ┌───────┐ ┌───────┐ ┌───────┐
│   C   │ │   M   │ │   D   │   │   R   │ │   E   │ │   F   │
└───────┘ └───────┘ └───────┘   └───────┘ └───────┘ └───────┘
</pre>
<pre>
<span style="color: #00ff66;">┌───────┐ ┌───────┐ ┌───────┐</span>
<span style="color: yellow;">│   C   │ │   M   │ │   D   │</span>
<span style="color: #00ff66;">└───────┘ └───────┘ └───────┘</span>
</pre>

<svg viewBox="0 0 240 80" xmlns="http://www.w3.org/2000/svg">
  <style>
    .small {
      font: italic 13px sans-serif;
    }
    .heavy {
      font: bold 30px sans-serif;
    }

    /* Note that the color of the text is set with the    *
     * fill property, the color property is for HTML only */
    .Rrrrr {
      font: italic 40px serif;
      fill: red;
    }
  </style>

  <text x="20" y="35" class="small">My</text>
  <text x="40" y="35" class="heavy">cat</text>
  <text x="55" y="55" class="small">is</text>
  <text x="65" y="55" class="Rrrrr">Grumpy!</text>
</svg>
  _|_|_|  _|      _|  _|_|_|    _|_|_|                  _|_| 
_|        _|_|  _|_|  _|    _|  _|    _|    _|_|      _|     
_|        _|  _|  _|  _|    _|  _|_|_|    _|_|_|_|  _|_|_|_| 
_|        _|      _|  _|    _|  _|    _|  _|          _|     
  _|_|_|  _|      _|  _|_|_|    _|    _|    _|_|_|    _|     

<img align="right" alt="GIF" height="160px" src="https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExZmp5OWs2amxieWEycmptbWkwNWo4bGltOTdseWNqbzJ4MHQ5NndubCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/W2x2NyL5Of6JW/giphy.gif" />

## I'm a  Developer

<!-- in README.md -->


- 🌱 I am currently learning more about  development.
- 📫 What is the best way to contact me? [Linkedin](https://www.linkedin.com/in/)
- 😄 Pronouns: He/Him

[![GitHub](https://img.shields.io/badge/Github-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/#)
[![Linkedin](https://img.shields.io/badge/Linkedin-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/#/)
[![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/#)
[![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)](https://www.reddit.com/user/#)

[![Apple](https://img.shields.io/badge/Apple-MacBook_Pro_2019-999999?style=for-the-badge&logo=apple&logoColor=white)]()

---

<img align="right" alt="GIF" height="170px" src="[https://media.giphy.com/media/J5B1Y8QZnzXXbLQIBu/giphy.gif](https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExZmp5OWs2amxieWEycmptbWkwNWo4bGltOTdseWNqbzJ4MHQ5NndubCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/W2x2NyL5Of6JW/giphy.gif)" />


---

<!--START_SECTION:waka-->
![Code Time](http://img.shields.io/badge/Code%20Time-87%20hrs%2026%20mins-blue)

**I'm an Early 🐤** 

```text
🌞 Morning                73 commits          ███████░░░░░░░░░░░░░░░░░░   27.86 % 
🌆 Daytime                117 commits         ███████████░░░░░░░░░░░░░░   44.66 % 
🌃 Evening                17 commits          ██░░░░░░░░░░░░░░░░░░░░░░░   06.49 % 
🌙 Night                  55 commits          █████░░░░░░░░░░░░░░░░░░░░   20.99 % 
```


📊 **This Week I Spent My Time On** 

```text
🕑︎ Time Zone: America/Chicago

💬 Programming Languages: 
No Activity Tracked This Week

🔥 Editors: 
No Activity Tracked This Week
```


 Last Updated on 10/08/2025 18:50:08 UTC
<!--END_SECTION:waka-->


---


[![Golang](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)]()
[![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)]()
[![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)]()
[![Vim](https://img.shields.io/badge/Vim-%2311AB00.svg?&style=for-the-badge&logo=vim&logoColor=white)]()


<img src="https://imgur.com/rilHVxA.png"/> 



<table align= "center">
  <tr>
     <td align="center" width="140" height="112.43">
      <a href="#macropower-tech" >
        <img src="./react-original.svg" width="48" height="48" alt="React.js" />
      </a>
      <br>React.js
    </td>
    <td align="center"  width="140" height="112.43">
      <a href="#macropower-tech" >
        <img src="./react-original.svg" width="48" height="48" alt="React Native" />
      </a>
      <br>React Native
    </td>
    <td align="center"  width="140" height="112.43">
      <a href="#macropower-tech">
        <img src="./javascript-original.svg" width="48" height="48" alt="JavaScript" />
      </a>
      <br>JavaScript
    </td>
    <td align="center"  width="140" height="112.43">
      <a href="#macropower-tech">
        <img src="./typescript-original.svg" width="48" height="48" alt="TypeScript" />
      </a>
      <br>TypeScript
    </td>
    <td align="center"  width="140" height="112.43">
      <a href="#macropower-tech">
        <img src="./sass-original.svg" width="48" height="48" alt="Sass" />
      </a>
      <br>Sass
    </td>
    <tr>
     <td align="center" width="140" height="112.43">
      <a href="#macropower-tech">
        <img src="./graphql.svg" width="48" height="48" alt="GraphQL" />
      </a>
      <br>GraphQL
    </td>
    <td align="center"  width="140" height="112.43">
      <a href="#macropower-tech">
        <img src="./nextjs.svg" width="48" height="48" alt="Next.js" />
      </a>
      <br>Next.js
    </td>
    </br>
    <td align="center"  width="140" height="112.43">
      <a href="#macropower-tech">
        <img src="./Firebase_Logo_Standard_Lockup.svg" width="48" height="48" alt="Firebase" />
      </a>
      <br>Firebase
    </td>
    <td align="center"  width="140" height="112.43">
      <a href="#macropower-tech">
        <img src="./styled-components.svg" width="48" height="48" alt="FStyled-components" />
      </a>
      <br>Styled-components
    </td>
    <td align="center"  width="140" height="112.43">
      <a href="#macropower-tech">
        <img src="./tailwind.svg" width="65" height="50" alt="Tailwind" />
      </a>
      <br>Tailwind
    </td>
   </tr>
     <tr>
     <td align="center" width="140" height="112.43">
      <a href="#macropower-tech">
        <img src="./sdk.svg" width="48" height="48" alt="Expo" />
      </a>
      <br>Expo
    </td>
    <td align="center"  width="140" height="112.43">
      <a href="#macropower-tech">
        <img src="./redux.svg" width="48" height="48" alt="Next.js" />
      </a>
      <br>Redux
    </td>
    </br>
    <td align="center"  width="140" height="112.43">
      <a href="#macropower-tech">
        <img src="./react-original.svg" width="48" height="48" alt="Context API" />
      </a>
      <br>Context API
    </td>
    <td align="center"  width="140" height="112.43">
      <a href="#macropower-tech">
        <img src="./wagmi_light.svg" width="48" height="48" alt="wagmi.svg" />
      </a>
      <br>Wagmi
    </td>
    <td align="center"  width="140" height="112.43">
      <a href="#macropower-tech">
        <img src="./ethers.svg" width="65" height="50" alt="ethers" />
      </a>
      <br>Ethers.js
    </td>
   </tr>
  </tr>
  
</table>
</br>



<!-- <table align= "center">
<td align="center"  width="240" height="112.43">
      <a href="#macropower-tech">
        <img height="250px" width="200px" src="./casino.gif"/>
      </a>
       <br>Casino roulette Project   
  
</td>
  
</table>
-->




<table align= "center">
  <td align="center"  width="240" height="112.43">
   <p  style="margin-top:12px">
  📫 You can reach me:
     </P
  </br>
  <a href="https://www.linkedin.com/in/thalesbmc/"><img src="https://cdn2.iconfinder.com/data/icons/social-media-2285/512/1_Linkedin_unofficial_colored_svg-128.png" width="80">
  </br>
  </br>
  <a href="mailto:thalesbmc@gmail.com"><img src="./gmail.png" width="80"></a>

</td>
</table>
<br>

</br>
<br>
<br>

</br>








> [!NOTE]
> Top languages are only a metric of the languages my public code consists of and doesn't reflect my experience or skill level.

<p align="center">
<pre>
<span style="color:#00FF00">
          ⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣤⣴⣶⣾⣿⣷⣶⣤⣄⡀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⣴⣾⣿⣿⣿⠿⠛⠛⠻⠿⣿⣿⣿⣦⣄⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⢠⣾⣿⣿⠿⠋⠀⠀⠀⠀⠀⠀⠀⠀⠙⠿⣿⣿⣦⡀⠀
⠀⠀⠀⠀⠀⠀⢠⣿⣿⠟⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⢻⣿⣿⡄
⠀⠀⠀⠀⠀⠀⣿⣿⡏⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢹⣿⣿
⠀⠀⠀⠀⠀⠀⣿⣿⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⣿⣿
⠀⠀⠀⠀⠀⠀⣿⣿⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣿⣿
⠀⠀⠀⠀⠀⠀⢿⣿⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢠⣿⡿
⠀⠀⠀⠀⠀⠀⠈⢿⣿⣦⣀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣀⣤⣾⣿⡿⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠙⠻⣿⣿⣶⣤⣤⣤⣤⣤⣤⣶⣾⣿⣿⠿⠛⠁⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⠛⠻⠿⢿⣿⡿⠿⠟⠛⠉⠀⠀⠀⠀⠀⠀
</span>
</pre>
</p>

<p align="center"> <img src="https://img.shields.io/badge/Bash-000000?style=for-the-badge&logo=gnu-bash&logoColor=00FF00" /> <img src="https://img.shields.io/badge/Linux-000000?style=for-the-badge&logo=linux&logoColor=00FF00" /> <img src="https://img.shields.io/badge/Git-000000?style=for-the-badge&logo=git&logoColor=00FF00" /> <img src="https://img.shields.io/badge/Neovim-000000?style=for-the-badge&logo=neovim&logoColor=00FF00" /> <img src="https://img.shields.io/badge/Markdown-000000?style=for-the-badge&logo=markdown&logoColor=00FF00" /> <img src="https://img.shields.io/badge/Star%20Wars%20Logic-000000?style=for-the-badge&logo=reverbnation&logoColor=00FF00" /> </p>

<p align="center"> <img src="https://github-readme-stats.vercel.app/api?username=cmdref&show_icons=true&theme=chartreuse-dark&hide_border=true&icon_color=00FF00&title_color=00FF00&text_color=FFFFFF&bg_color=000000" alt="cmdref's GitHub stats" width="48%" /> <img src="https://github-readme-streak-stats.herokuapp.com/?user=cmdref&theme=highcontrast&hide_border=true&stroke=00FF00&ring=00FF00&fire=00FF00&currStreakLabel=00FF00" alt="cmdref's streak" width="48%" /> </p>
<p align="center"> <img src="https://komarev.com/ghpvc/?username=cmdref&color=00FF00&style=flat-square" alt="visitor badge" /> </p> <p align="center"> <b>⚡ The Force flows through the Terminal ⚡</b> </p> ```

⠉⠉⠉⠉⠁⠀⠀⠀⠀⠒⠂⠰⠤⢤⣀⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠛⠻⢤⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠠⠀⠐⠒⠒⠀⠀⠈⠉⠉⠉⠉⢉⣉⣉⣉⣙⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⢀⡀⠤⠒⠒⠉⠁⠀⠀⠀⠀⠳⣤⣀⣀⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠈⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⣶⠛⠛⠉⠛⠛⠶⢦⣤⡐⢀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣰⡿⠁⠀⠀⠀⠀⠀⠀⠀⠈⠉⢳⣦⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣿⡇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⠳⡤⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢹⣇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠙⢷⣤⣀⣀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠉⠙⠛⠛⠳⠶⢶⣦⠤⣄⡀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⠳⣄⠉⠑⢄⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠳⡀⠀⠁
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠱⡄⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢰⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡄


<!-- ===== STAR WARS HACKER README FOR cmdref ===== -->

<h1 align="center">🌌🛡️ cmdref — The Force of the CLI Awakens 🛡️🌌</h1>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Share+Tech+Mono&size=26&pause=1000&color=00FF00&center=true&vCenter=true&width=1000&lines=💻+Jedi+of+the+Command+Line;🛰️+Automation+Bounty+Hunter;⚡+Galactic+Scripting+Master;🛡️+Guardian+of+Code;👾+Hacker+of+the+Outer+Rim" alt="Typing animation" />
</p>

---

<p align="center">
  <img src="https://media.giphy.com/media/oEI9uBYSzLpBK/giphy.gif" alt="Matrix Rain" width="100%" />
</p>

---

## 🚀 Galactic Navigation

<p align="center">
  <a href="https://github.com/cmdref/command-line-cheatsheet">
    <img src="https://img.shields.io/badge/⚔️%20CLI%20Cheatsheet-000000?style=for-the-badge&logo=gnu-bash&logoColor=00FF00" />
  </a>
  <a href="https://github.com/cmdref/cli-shortcuts">
    <img src="https://img.shields.io/badge/🛸%20CLI%20Shortcuts-000000?style=for-the-badge&logo=neovim&logoColor=00FF00" />
  </a>
  <a href="https://github.com/cmdref/terminal-tricks">
    <img src="https://img.shields.io/badge/💫%20Terminal%20Tricks-000000?style=for-the-badge&logo=linux&logoColor=00FF00" />
  </a>
  <a href="https://github.com/cmdref/docs-hub">
    <img src="https://img.shields.io/badge/📚%20Docs%20Hub-000000?style=for-the-badge&logo=markdown&logoColor=00FF00" />
  </a>
</p>

---

## 📜 Jedi Console Log



$ whoami
> cmdref — Keeper of the Galactic CLI Scrolls

$ sudo use_the_force --light
> Initiating lightsaber... ⚔️ | Target: Bug Fixes

$ ls -lah /galactic/repos
> command-line-cheatsheet/
> cli-shortcuts/
> terminal-tricks/
> docs-hub/

$ ./jump_to_hyperspace.sh
> ⚡ Entering lightspeed... Hold on to your scripts!


**Note:** Before pasting: upload your custom images/GIFs into the repo (e.g. `assets/` folder).  
I reference `./assets/` paths below — if you don't upload them, the README will still work using the public GIFs included.

<p align="center">
  <!-- logo - upload your logo to assets/cmdref_logo.png -->
  <img src="./assets/cmdref_logo.png" alt="cmdref logo" width="180" />
</p>

<p align="center">
  💻⚡ **Jedi of the CLI** &nbsp;|&nbsp; 🛰️ **Automation Bounty Hunter** &nbsp;|&nbsp; 🛡️ **Code Guardian** &nbsp;|&nbsp; 👾 **Cyberpunk Builder**  
  🔮 Turning commands into galaxies — *welcome to the holo-net.*
</p>

<p align="center">
  <img src="https://img.shields.io/badge/CLI%20Jedi-000000?style=for-the-badge&logo=gnu-bash&logoColor=00FF00" alt="CLI" />
  <img src="https://img.shields.io/badge/Automation-000000?style=for-the-badge&logo=github-actions&logoColor=00FF00" alt="Automation" />
  <img src="https://img.shields.io/badge/Cyberpunk-000000?style=for-the-badge&logo=neovim&logoColor=00FF00" alt="Cyberpunk" />
  <img src="https://img.shields.io/badge/Docs-000000?style=for-the-badge&logo=markdown&logoColor=00FF00" alt="Docs" />
</p>

---

<p align="center">
  <!-- neon typing animation -->
  <img src="https://readme-typing-svg.demolab.com?font=Share+Tech+Mono&size=28&pause=1000&color=00FF00&center=true&vCenter=true&width=820&lines=The+Terminal+Awakens;A+New+CLI+Hope;Binary+Flows+Through+The+Force" alt="typing" />
</p>

---

<p align="center">
  <!-- matrix / binary rain - public GIF fallback used if you don't upload your own -->
  <img src="./assets/cmdref_binary_rain.gif" alt="binary rain (local)" width="820" onerror="this.onerror=null; this.src='https://media.giphy.com/media/oEI9uBYSzLpBK/giphy.gif'">
</p>

---

<div align="center">

<pre><code>
$ whoami
> cmdref

$ uname -a
> Galactic CLI Archivist • Automation Bounty Hunter • Open Source Rebel

$ ls ~/repos
> command-line-cheatsheet/  cli-shortcuts/  terminal-tricks/  docs-hub/

$ ./activate_force_mode.sh
> 01001000 01000001 01000011 01001011 01000101 01010010 00100000 01000001 01000011 01010100 01001001 01010110 01000001 01010100 01000101 01000100
</code></pre>

</div>

---

### 🌌 Featured Repositories (HoloNet Links)

| Repo | Description |
|------|-------------|
| **[command-line-cheatsheet](https://github.com/cmdref/command-line-cheatsheet)** | Ancient Jedi scrolls of CLI commands, examples & quick snippets. |
| **[cli-shortcuts](https://github.com/cmdref/cli-shortcuts)** | Lightspeed shortcuts, aliases and dotfiles to speed your workflow. |
| **[terminal-tricks](https://github.com/cmdref/terminal-tricks)** | Force-powered terminal hacks, tools and one-liners. |
| **[docs-hub](https://github.com/cmdref/docs-hub)** | Organized documentation for scripts, patterns & workshops. |

---

<p align="center">
  <!-- custom generated hero image (upload the PNG/GIF you received) -->
  <img src="./assets/cmdref_cyberhero.png" alt="cmdref cyber hero (upload assets/cmdref_cyberhero.png)" width="820" />
</p>

---

<p align="center">
  <!-- binary / neon animations - public GIFs used as fallback visuals -->
  <img src="./assets/cmdref_binary_loop.gif" alt="binary loop (local)" width="280" onerror="this.onerror=null; this.src='https://media.giphy.com/media/xT9IgzoKnwFNmISR8I/giphy.gif'">
  &nbsp;&nbsp;
  <img src="./assets/cmdref_neon_circuit.gif" alt="neon circuit (local)" width="280" onerror="this.onerror=null; this.src='https://media.giphy.com/media/YQitE4YNQNahy/giphy.gif'">
  &nbsp;&nbsp;
  <img src="./assets/cmdref_hacker_screen.gif" alt="hacker screen (local)" width="280" onerror="this.onerror=null; this.src='https://media.giphy.com/media/du3J3cXyzhj75IOgvA/giphy.gif'">
</p>

---

<p align="center">
  <pre>
   _______  _________ _______  _______ _________
  (  ____ \(  ___  )(  ____ )(  ____ \\__   __/
  | (    \/| (   ) || (    )|| (    \/   ) (   
  | (_____ | (___) || (____)|| (_____    | |   
  (_____  )|  ___  ||     __)(_____  )   | |   
        ) || (   ) || (\ (         ) |   | |   
  /\____) || )   ( || ) \ \__/\____) |   | |   
  \_______)|/     \||/   \__/\_______)   )_(   
  </pre>
</p>

<p align="center">💻 <b>The Force Will Be With Your Terminal. Always.</b> 💻</p>

---

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=cmdref&color=00FF00&style=flat-square" alt="visitor count" />
</p>

---

## How to set this up (quick)
1. Create a repo named exactly `cmdref` (if you want this README to render on your profile, your repo name must match your username).  
2. Add a folder `assets/` to the repo and upload these files (recommended filenames):
   - `assets/cmdref_logo.png` — your logo (180×180 or similar)
   - `assets/cmdref_cyberhero.png` — hero image (the generated PNG/GIF)
   - `assets/cmdref_binary_rain.gif` — binary rain GIF (optional)
   - `assets/cmdref_binary_loop.gif` — small looping binary (optional)
   - `assets/cmdref_neon_circuit.gif` — neon circuit GIF (optional)
   - `assets/cmdref_hacker_screen.gif` — hacker screen GIF (optional)
3. Create `README.md` at the root and paste this whole file (you may paste inside a code block in your editor, but **do not** wrap the final README content itself with triple backticks in the file).
4. Commit & push. GitHub will render it on your profile.

---

## Want me to do this for you?
If you want I can:
- generate the **custom glitch/GIFs with `cmdref` in binary** and provide files ready to upload, or
- produce a single **SVG animated starfield + typing header** (pure SVG so it's crisp and fast).

Which one would you like next: **(A)** custom GIF pack with username, or **(B)** animated SVG starfield + typed crawl?



<!-- CYBER STAR WARS FUTURISTIC GITHUB PROFILE -->

<!-- Logo -->
<p align="center">
  <img src="YOUR_LOGO_URL" alt="Logo" width="200" />
</p>

<!-- Cyber Bio -->
<p align="center">
  💻⚡ Jedi of the CLI&nbsp;&nbsp;|&nbsp;&nbsp;🛰️ Automation Bounty Hunter&nbsp;&nbsp;|&nbsp;&nbsp;🛡️ Code Guardian&nbsp;&nbsp;|&nbsp;&nbsp;👾 Cyberpunk Builder&nbsp;&nbsp;|&nbsp;&nbsp;🔮 Turning Commands into Galaxies
</p>

<!-- Neon Badges -->
<p align="center">
  <img src="https://img.shields.io/badge/CLI%20Jedi-000000?style=for-the-badge&logo=gnu-bash&logoColor=00FF00" />
  <img src="https://img.shields.io/badge/Automation%20Bounty%20Hunter-000000?style=for-the-badge&logo=gear&logoColor=00FF00" />
  <img src="https://img.shields.io/badge/Cyberpunk%20Builder-000000?style=for-the-badge&logo=neovim&logoColor=00FF00" />
  <img src="https://img.shields.io/badge/Code%20Guardian-000000?style=for-the-badge&logo=github&logoColor=00FF00" />
</p>

<!-- Typing Animation -->
<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Share+Tech+Mono&size=30&pause=1000&color=00FF00&center=true&vCenter=true&width=800&lines=The+Terminal+Awakens;A+New+CLI+Hope;Cyber+Futuristic+Knowledge+Base;Binary+Code+Flows+Through+The+Force" alt="Typing SVG" />
</p>

---

<!-- Binary Matrix Rain GIF -->
<p align="center">
  <img src="https://media.giphy.com/media/oEI9uBYSzLpBK/giphy.gif" width="800" alt="Binary Rain" />
</p>

---

<!-- Star Wars Opening Crawl -->
<p align="center">
  <img src="https://media.giphy.com/media/3o7abldj0b3rxrZUxW/giphy.gif" width="600" alt="Star Wars Crawl" />
</p>

---

<!-- Hacker Terminal -->
<div align="center">

<pre><code class="language-bash">
$ whoami
> jedi-cli-master

$ uname -a
> Galactic CLI Archivist • Automation Bounty Hunter • Open Source Rebel

$ ls ~/repos
> command-line-cheatsheet/  cli-shortcuts/  terminal-tricks/  docs-hub/

$ ./execute_force.sh
> 01001000 01000001 01000011 01001011 01000101 01010010 00100000 01000001 01000011 01010100 01001001 01010110 01000001 01010100 01000101 01000100
</code></pre>

</div>

---

### 🌌 Featured Repositories (HoloNet Links)

| Repo | Description |
|------|-------------|
| **[command-line-cheatsheet](https://github.com/YOUR_USERNAME/command-line-cheatsheet)** | Ancient Jedi scrolls of CLI commands and usage examples. |
| **[cli-shortcuts](https://github.com/YOUR_USERNAME/cli-shortcuts)** | Lightspeed shortcuts and aliases for your workflow. |
| **[terminal-tricks](https://github.com/YOUR_USERNAME/terminal-tricks)** | Force-powered terminal hacks. |
| **[docs-hub](https://github.com/YOUR_USERNAME/docs-hub)** | Complete Jedi archives for developers. |

---

<!-- Binary Animation -->
<p align="center">
  <img src="https://media.giphy.com/media/xT9IgzoKnwFNmISR8I/giphy.gif" width="500" alt="Binary Animation" />
</p>

---

<!-- Glitchy ASCII Logo -->
<p align="center">
<pre>
  _______ _________ _______  _______ _________
 (  ____ \\__   __/(  ___  )(  ____ \\__   __/
 | (    \/   ) (   | (   ) || (    \/   ) (   
 | (_____    | |   | (___) || (_____    | |   
 (_____  )   | |   |  ___  |(_____  )   | |   
       ) |   | |   | (   ) |      ) |   | |   
 /\____) |   | |   | )   ( |/\____) |   | |   
 \_______)   )_(   |/     \|\_______)   )_(   
</pre>
</p>

---

<!-- Glitch Animation -->
<p align="center">
  <img src="https://media.giphy.com/media/l0MYGB5Hq9Xc2p6uY/giphy.gif" width="500" alt="Glitch Animation" />
</p>

---

<!-- More Cyber GIFs -->
<p align="center">
  <img src="https://media.giphy.com/media/du3J3cXyzhj75IOgvA/giphy.gif" width="300" alt="Hacker Screen" />
  <img src="https://media.giphy.com/media/26tn33aiTi1jkl6H6/giphy.gif" width="300" alt="Neon Binary" />
  <img src="https://media.giphy.com/media/YQitE4YNQNahy/giphy.gif" width="300" alt="Neon Circuit" />
</p>

---

<p align="center">💻 <b>The Force Will Be With Your Terminal. Always.</b> 💻</p>

---

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=YOUR_USERNAME&color=00FF00&style=flat-square" />
</p>


<!-- CYBER STAR WARS FUTURISTIC GITHUB PROFILE -->

<!-- Logo -->
<p align="center">
  <img src="YOUR_LOGO_URL" alt="Logo" width="200" />
</p>

<!-- Neon Glowing Typing Animation -->
<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Share+Tech+Mono&size=30&pause=1000&color=00FF00&center=true&vCenter=true&width=700&lines=The+Terminal+Awakens;A+New+CLI+Hope;Cyber+Futuristic+Knowledge+Base" alt="Typing SVG" />
</p>

---

<!-- Star Wars Opening Crawl GIF -->


---

<!-- Hacker Terminal -->
<div align="center">

<pre><code class="language-bash">
$ whoami
> jedi-cli-master

$ uname -a
> Galactic CLI Archivist • Automation Bounty Hunter • Open Source Rebel

$ ls ~/repos
> command-line-cheatsheet/  cli-shortcuts/  terminal-tricks/  docs-hub/
</code></pre>

</div>

---

<!-- Badges -->
<p align="center">
  <img src="https://img.shields.io/badge/Linux-000000?style=for-the-badge&logo=linux&logoColor=00FF00" />
  <img src="https://img.shields.io/badge/Terminal-000000?style=for-the-badge&logo=gnu-bash&logoColor=00FF00" />
  <img src="https://img.shields.io/badge/Jedi-000000?style=for-the-badge&logo=star-wars&logoColor=00FF00" />
  <img src="https://img.shields.io/badge/Docs-000000?style=for-the-badge&logo=markdown&logoColor=00FF00" />
</p>

---

### 🌌 Featured Repositories (HoloNet Links)

| Repo | Description |
|------|-------------|
| **[command-line-cheatsheet](https://github.com/YOUR_USERNAME/command-line-cheatsheet)** | Ancient Jedi scrolls of CLI commands and usage examples. |
| **[cli-shortcuts](https://github.com/YOUR_USERNAME/cli-shortcuts)** | Lightspeed shortcuts and aliases for your workflow. |
| **[terminal-tricks](https://github.com/YOUR_USERNAME/terminal-tricks)** | Force-powered terminal hacks. |
| **[docs-hub](https://github.com/YOUR_USERNAME/docs-hub)** | Complete Jedi archives for developers. |

---

<!-- Glitchy ASCII Logo -->
<p align="center">
<pre>
  _______ _________ _______  _______ _________
 (  ____ \\__   __/(  ___  )(  ____ \\__   __/
 | (    \/   ) (   | (   ) || (    \/   ) (   
 | (_____    | |   | (___) || (_____    | |   
 (_____  )   | |   |  ___  |(_____  )   | |   
       ) |   | |   | (   ) |      ) |   | |   
 /\____) |   | |   | )   ( |/\____) |   | |   
 \_______)   )_(   |/     \|\_______)   )_(   
</pre>
</p>

---

<!-- Glitch Animation -->
<p align="center">
  <img src="https://media.giphy.com/media/l0MYGB5Hq9Xc2p6uY/giphy.gif" width="500" alt="Glitch Animation" />
</p>

---

<p align="center">💻 <b>The Force Will Be With Your Terminal. Always.</b> 💻</p>

---

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=YOUR_USERNAME&color=00FF00&style=flat-square" />
</p>



<p align="center">
  <img src="YOUR_LOGO_URL" alt="Logo" width="200" />
</p>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&pause=1000&color=00FF00&center=true&vCenter=true&width=700&lines=Welcome+to+my+Terminal;Cyber+Futuristic+CLI+Repo;Command+Line+Shortcuts+%26+Docs" alt="Typing SVG" />
</p>

---

<div align="center">

<pre><code class="language-bash">
$ whoami
> YOUR_NAME_OR_HANDLE

$ uname -a
> Futuristic CLI Enthusiast • Docs Builder • Automation Nerd

$ ls ~/repos
> command-line-cheatsheet/  cli-shortcuts/  terminal-tricks/  docs-hub/
</code></pre>

</div>

---

<p align="center">
  <img src="https://img.shields.io/badge/Linux-000000?style=for-the-badge&logo=linux&logoColor=00FF00" alt="Linux" />
  <img src="https://img.shields.io/badge/Terminal-000000?style=for-the-badge&logo=gnu-bash&logoColor=00FF00" alt="Bash" />
  <img src="https://img.shields.io/badge/Docs-000000?style=for-the-badge&logo=markdown&logoColor=00FF00" alt="Docs" />
  <img src="https://img.shields.io/badge/CLI-000000?style=for-the-badge&logo=command-line&logoColor=00FF00" alt="CLI" />
</p>

---

### 📂 Featured Repositories

| Repo | Description |
|------|-------------|
| **[command-line-cheatsheet](https://github.com/YOUR_USERNAME/command-line-cheatsheet)** | A comprehensive list of useful CLI commands and examples. |
| **[cli-shortcuts](https://github.com/YOUR_USERNAME/cli-shortcuts)** | Shortcuts and aliases to speed up your workflow. |
| **[terminal-tricks](https://github.com/YOUR_USERNAME/terminal-tricks)** | Tips & tricks for terminal power users. |
| **[docs-hub](https://github.com/YOUR_USERNAME/docs-hub)** | Centralized documentation for scripts, dotfiles and tutorials. |

---

<pre>
     _______  _______  _______ _________ _______  _        _       
    (  ____ \(  ___  )(  ____ )\__   __/(  ___  )( \      ( \      
    | (    \/| (   ) || (    )|   ) (   | (   ) || (      | (      
    | (__    | (___) || (____)|   | |   | |   | || |      | |      
    |  __)   |  ___  ||     __)   | |   | |   | || |      | |      
    | (      | (   ) || (\ (      | |   | |   | || |      | |      
    | (____/\| )   ( || ) \ \__   | |   | (___) || (____/\| (____/\
    (_______/|/     \||/   \__/   )_(   (_______)(_______/(_______/
</pre>

<p align="center">💻 <b>Hack the Terminal, Rule the Workflow</b> 💻</p>

---

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=cmdref&color=00FF00&style=flat-square" alt="visitor-count" />
</p>

---

**Quick checklist before you paste**
- Replace `YOUR_USERNAME` with your GitHub handle.
- Replace `YOUR_LOGO_URL` with an uploaded image URL (you can upload `logo.png` into the repo and use `/YOUR_USERNAME/logo.png`).
- **Important:** When copying from this chat, do **not** include the triple backticks that wrap this block here — paste the raw Markdown into `README.md`.

Would you like me to:
- add a neon SVG glow effect (animated) for the heading, or  
- produce a small animated GIF terminal for the top (I can show how to embed it), or  
- convert the plain ASCII footer into a clean SVG logo?

Tell me which and I’ll add it directly into this README.



<h3 align="center">A passionate developer from India</h3>

**cmdref/cmdref** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
  
<h3 align="left">Connect with me: cmdref@protonmail.com</h3>
<p align="left">
</p>

<h3 align="left">Languages and Tools:</h3>
<p align="left"> <a href="https://developer.android.com" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/android/android-original-wordmark.svg" alt="android" width="40" height="40"/> </a> <a href="https://www.cprogramming.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/c/c-original.svg" alt="c" width="40" height="40"/> </a> <a href="https://www.w3schools.com/css/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" alt="css3" width="40" height="40"/> </a> <a href="https://www.java.com" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="java" width="40" height="40"/> </a> <a href="https://www.mongodb.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original-wordmark.svg" alt="mongodb" width="40" height="40"/> </a> <a href="https://www.nginx.com" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nginx/nginx-original.svg" alt="nginx" width="40" height="40"/> </a> <a href="https://www.perl.org/" target="_blank" rel="noreferrer"> <img src="https://api.iconify.design/logos-perl.svg" alt="perl" width="40" height="40"/> </a> <a href="https://vuejs.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/vuejs/vuejs-original-wordmark.svg" alt="vuejs" width="40" height="40"/> </a> </p>



<!-- Cyber Futuristic GitHub Profile README -->

<!-- Banner / Logo -->
<p align="center">
  <img src="YOUR_LOGO_URL" alt="Logo" width="200" />
</p>

<!-- Animated Typing Header -->
<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&pause=1000&color=00FF00&center=true&vCenter=true&width=435&lines=Welcome+to+my+Terminal;Cyber+Futuristic+CLI+Repo;Command+Line+Shortcuts+%26+Docs" alt="Typing SVG" />
</p>

---

<!-- Hacker Terminal Style -->
<div align="center">
  
```bash
$ whoami
> cyber.dev

$ uname -a
> Futuristic CLI Enthusiast | Docs Builder | Automation Nerd

$ ls ~/repos
> command-line-cheatsheet/  cli-shortcuts/  terminal-tricks/  docs-hub/

✅ Shows **green text** in GitHub’s rendered README preview.  

---

## **Option 2: Use an image of the ASCII art**
You can make your ASCII art green in a terminal, screenshot it, and embed like:

```md
<p align="center">
  <img src="https://raw.githubusercontent.com/cmdref/assets/main/kali-ascii-green.png" alt="Kali ASCII" />
</p>

```ansi
[0;32m
          ⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣤⣴⣶⣾⣿⣷⣶⣤⣄⡀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⣴⣾⣿⣿⣿⠿⠛⠛⠻⠿⣿⣿⣿⣦⣄⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⢠⣾⣿⣿⠿⠋⠀⠀⠀⠀⠀⠀⠀⠀⠙⠿⣿⣿⣦⡀⠀
⠀⠀⠀⠀⠀⠀⢠⣿⣿⠟⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⢻⣿⣿⡄
⠀⠀⠀⠀⠀⠀⣿⣿⡏⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢹⣿⣿
⠀⠀⠀⠀⠀⠀⣿⣿⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⣿⣿
⠀⠀⠀⠀⠀⠀⣿⣿⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣿⣿
⠀⠀⠀⠀⠀⠀⢿⣿⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢠⣿⡿
⠀⠀⠀⠀⠀⠀⠈⢿⣿⣦⣀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣀⣤⣾⣿⡿⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠙⠻⣿⣿⣶⣤⣤⣤⣤⣤⣤⣶⣾⣿⣿⠿⠛⠁⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⠛⠻⠿⢿⣿⡿⠿⠟⠛⠉⠀⠀⠀⠀⠀⠀
[0m




