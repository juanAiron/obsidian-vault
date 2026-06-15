### Linux
##### Install SQL Server
- lsb_release -rs
##### 22.04 Microsoft repo install SQL Server
1. Add Microsoft signing key
	curl https://packages.microsoft.com/keys/microsoft.asc | sudo tee /etc/apt/trusted.gpg.d/microsoft.asc

2. Add the SQL Server repo
	sudo curl -o /etc/apt/sources.list.d/mssql-server.list \
	https://packages.microsoft.com/config/ubuntu/22.04/mssql-server-2022.list

3. Update and install
	sudo apt-get update
	sudo apt-get install -y mssql-server

Edition: 2
Password: 218redeemed!

##### Add Microsoft Repository & Install
Installation
	wget http://archive.ubuntu.com/ubuntu/pool/main/o/openldap/libldap-2.5-0_2.5.20+dfsg-0ubuntu0.22.04.1_amd64.deb
	
	sudo dpkg -i libldap-2.5-0_2.5.20+dfsg-0ubuntu0.22.04.1_amd64.deb

##### Start
	sudo systemctl start mssql-server
	systemctl status mssql-server

##### Install sqlcmd
Run these one at a time:
###### Add Microsoft repo for tools
sudo curl -o /etc/apt/sources.list.d/mssql-tools.list \
  https://packages.microsoft.com/config/ubuntu/22.04/prod.list

###### Update and install
sudo apt-get update
sudo apt-get install -y mssql-tools18 unixodbc-dev

###### Add sqlcmd to your PATH permanently
echo 'export PATH="$PATH:/opt/mssql-tools18/bin"' >> ~/.bashrc
source ~/.bashrc

##### Test Connection
sqlcmd -S localhost -U SA -P 'YourPassword' -C
### AI & Automation

### Core Essentials
1. **Git** - *sudo apt install git*
2. **SSH** - *sudo apt install openssh-server*
3. **HTOP** - *sudo apt install htop btop*
4. **tree** - *sudo apt install tree*
5. **Curl** - *sudo apt install curl*
6. **Widget** - *sudo apt install wget*
7. **net-tools** - *sudo apt install net-tools*
8. **nmap** - *sudo apt install nmap*
9. **tldr** - *sudo apt install tldr*
10. **bzip2** - *sudo apt install bzip2 -y* 
### Code Editors & Documentation
1. **[[VS Code]]** - *sudo apt install  code --classic*
2.  **[[Obsidian]]** - *sudo snap install obsidian --classic*
3. **[[Draw.io]]** - *sudo snap install drawio*
### Cloud & Infrastructure

### Containers

### Dev Tools
1. **Node.js** - curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
2. **Python 3** - *sudo apt install python3*
3. **pip** - *sudo apt install python3-pip*
4. **venv** - *sudo apt install python3-venv*
### Databases
1. **MySQL/MariaDB** - *sudo apt install mysql-server*
2. 
### Data Science & Machine Learning

### System Admin

### Web Development 

**sudo lsof -i :80** *(check who uses port 80)*

1. **NGINX** - *sudo apt install nginx*
2. **Apache2** - *sudo apt install apache2*
3. **PHP** - *sudo apt install php*
	1. sudo apt install php-mysql
	2. sudo apt install php-curl
	3. sudo apt install php-gd
	4. sudo apt install php-mbstring
	5. sudo apt install php-xml
	6. sudo apt install php-xmlrpc
	7. sudo apt install php-soap
	8. sudo apt install php-intl
	9. sudo apt install php-zip
	10. sudo apt install php-imagick
### Audio Mixing
1. **Demucs** - sudo apt-get install ffmpeg
			sudo apt-get install soundstretch
