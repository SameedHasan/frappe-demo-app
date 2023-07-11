## Demo App Installation Guide

#### Step 1: Python3 Installation

Open your linux terminal and follow the steps below to install python3

```bash
sudo apt update
```

```bash
sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libreadline-dev libssl-dev libffi-dev libsqlite3-dev wget libbz2-dev
```

```bash
wget https://www.python.org/ftp/python/3.10.6/Python-3.10.6.tgz
```

```bash
tar -xf Python-3.10.6.tgz
```

```bash
cd Python-3.10.6
```

```bash
sudo ./configure --enable-optimizations
```

```bash
sudo make altinstall
```

To Verify if Python3.10 is installed successfully, Run the below command

```bash
python3 -V
```

#### Step 2: Frappe-Bench Setup

Follow the steps below to setup Frappe Bench Environment

##### Step 2.1: Install git

```bash
sudo apt-get install git
```

##### Step 2.2: install python-dev

```bash
sudo apt-get install python3-dev
```

##### Step 2.3: Install setuptools and pip (Python's Package Manager)

```bash
sudo apt-get install python3-setuptools python3-pip
```

##### Step 2.4: Install virtualenv

```bash
sudo apt-get install virtualenv
```

```bash
sudo apt install python3.10-venv
```

##### Step 2.5: Install MariaDB 10.3 stable package

For ubuntu 20.04

```bash
sudo apt-get install software-properties-common
```

```bash
sudo apt-key adv --fetch-keys 'https://mariadb.org/mariadb_release_signing_key.asc'
```

```bash
sudo add-apt-repository 'deb [arch=amd64,arm64,ppc64el] https://ftp.icm.edu.pl/pub/unix/database/mariadb/repo/10.3/ubuntu focal main'
```

```bash
sudo apt update
```

```bash
sudo apt install mariadb-server
```

For ubuntu 18.04

```bash
sudo apt-get install software-properties-common dirmngr apt-transport-https
```

```bash
sudo apt-key adv --fetch-keys 'https://mariadb.org/mariadb_release_signing_key.asc'
```

```bash
sudo add-apt-repository 'deb [arch=amd64,arm64,ppc64el] https://mirrors.aliyun.com/mariadb/repo/10.3/ubuntu bionic main'
```

```bash
sudo apt update
```

```bash
sudo apt install mariadb-server
```

IMPORTANT :During this installation you'll be prompted to set the MySQL root password. If you are not prompted for the same You can initialize the MySQL server setup by executing the following command

```bash
sudo mysql_secure_installation
```

##### Step 2.6: MySQL database development files

```bash
sudo apt-get install libmysqlclient-dev
```

##### Step 2.7: Edit the mariadb configuration ( unicode character encoding )

```bash
sudo nano /etc/mysql/my.cnf
```

Add this to the my.cnf file

```bash
[mysqld]
character-set-client-handshake = FALSE
character-set-server = utf8mb4
collation-server = utf8mb4_unicode_ci

[mysql]
default-character-set = utf8mb4
```

Now press (Ctrl-X) to exit

```bash
sudo service mysql restart
```

##### Step 2.8: Install Redis

```bash
sudo apt-get install redis-server
```

##### Step 2.9: Install Node.js 16.X package

```bash
sudo apt-get install curl
curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt-get install -y nodejs
```

##### Step 2.10: Install Yarn

```bash
sudo npm install -g yarn
```

##### Step 2.11: Install wkhtmltopdf

```bash
sudo apt-get install xvfb libfontconfig wkhtmltopdf
```

##### Step 2.12: Install frappe-bench

```bash
sudo -H pip3 install frappe-bench
```

```bash
bench --version
```

##### Step 2.13: Initialize the frappe bench & install frappe latest version

```bash
bench init frappe-bench --frappe-branch version-14

cd frappe-bench/
bench start
```

##### Step 2.14: Create a site in frappe bench

```bash
bench new-site mysite.test
```

Set the newly created site as default site

```bash
bench use mysite.test
```

##### Step 2.15: Clone the App from github

```bash
bench get-app https://github.com/SameedHasan/frappe-demo-app.git
```

##### Step 2.16: Install the cloned app on site

```bash
 bench install-app demo_app
```

To confirm if the app was installed, run the following command:

```bash
 bench list-apps
```

##### Step 2.17: Start the Bench

```bash
 bench start
```

#### License

MIT
