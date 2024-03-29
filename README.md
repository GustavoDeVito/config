## Windows
  - [Choco](https://www.liquidweb.com/kb/how-to-install-chocolatey-on-windows/)
  - [Visual Studio Code](https://code.visualstudio.com/download)
  - [Git](https://git-scm.com/downloads) - [*Config*](https://git-scm.com/book/pt-br/v2/Começando-Configuração-Inicial-do-Git) - [*SSH*](https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent?platform=linux)
  - [Font Powerline](https://gist.github.com/stramel/658d702f3af8a86a6fe8b588720e0e23)
  - [FiraCode](https://dev.to/josuerodriguez98/installing-firacode-on-windows-and-ubuntu-1fn1)
  - [Inter](https://fonts.google.com/specimen/Inter)
  - [JetBrains Mono](https://www.jetbrains.com/pt-br/lp/mono/)

<br />

## WLS 2
    
*Install Distro*

```bash
wsl --install -d distro
```

*Uninstall Distro*

```bash
wsl --unregister -d distro
```
    
*Config file*

```bash
touch C:\Users\<username>\.wslconfig
```

```bash
vim C:\Users\<username>\.wslconfig
```

```txt
[wsl2]
memory=8GB
processos=4
swap=2GB
```

<br />

## WSL 2 - Ubuntu

```bash
sudo apt update
sudo apt install vim curl wget git unzip
```

<br />

## WSL 2 - [wslu](https://wslutiliti.es/wslu/)

<br />
  
### Zsh

*Install*

```bash
sudo apt install zsh
```

*Defaullt Shell*

```bash
chsh -s /usr/bin/zsh
```

*Close Terminal and open again (option 2)*

<br />

### Oh My Zsh
    
*Install*

```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
    
#### Plugins: 
  - [F-Sy-H](https://github.com/zdharma/fast-syntax-highlighting)
  - [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)
  - [zsh-completions](https://github.com/zsh-users/zsh-completions)

#### Theme:
  - [powerlevel10k](https://github.com/romkatv/powerlevel10k)

<br />

*Config*

```bash
code ~/.zshrc
```

```txt
[zshrc]

ZSH_THEME="powerlevel10k/powerlevel10k"

plugins=(git git-flow F-Sy-H zsh-autosuggestions zsh-completions)
```
    
```bash
source ~/.zshrc
```

```bash
#Reset Config
p10k configure
```

<br />

## WSL 2 - Docker

*Install*

```bash
sudo apt update && sudo apt upgrade
sudo apt remove docker docker-engine docker.io containerd runc
sudo apt-get install \
apt-transport-https \
ca-certificates \
curl \
gnupg \
lsb-release
```
    
*Add Docker repo in sources - Ubuntu*

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo \
"deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
$(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
      
*Install Docker-Engine*

```bash
sudo apt-get update
```

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

 *Permission*
 
```bash
sudo usermod -aG docker $USER
```

*Install Docker Compose*

```bash
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

*Service Docker*
 
```bash
sudo service docker start
```

<br />

## WSL 2 - Node.js

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
source ~/.bashrc
source ~/.zshrc
```

```bash
nvm ls-remote
nvm install (node-version)
```

*yarn*
```bash
npm install --global yarn
```

<br />

## WSL 2 - Java

```bash
sudo apt install openjdk-17-jdk openjdk-17-jre
java --version
javac --version
```

<br />

### WSL 2 - Maven

```bash
wget https://mirrors.estointernet.in/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz
tar -xvf apache-maven-3.6.3-bin.tar.gz
sudo mv apache-maven-3.6.3 /opt/
vim ~/.zshrc
source ~/.zshrc
mvn --version
```

```txt
[zshrc]
M2_HOME=/opt/apache-maven-3.6.3
PATH=$M2_HOME/bin:$PATH
```

<br />

### WSL 2 - Oracle Instant Client

```bash
sudo mkdir /opt/oracle
cd /opt/oracle

sudo wget https://download.oracle.com/otn_software/linux/instantclient/214000/instantclient-basic-linux.x64-21.4.0.0.0dbru.zip
sudo unzip instantclient-basic-linux.x64-21.4.0.0.0dbru.zip

sudo apt update
sudo apt install libaio1

sudo sh -c "echo /opt/oracle/instantclient_21_4 > /etc/ld.so.conf.d/oracle-instantclient.conf"
sudo ldconfig

sudo rm -rf instantclient-basic-linux.x64-21.4.0.0.0dbru.zip
```

<br />

### WSL 2 - Golang

```bash
# https://golang.org/dl/
wget https://golang.org/dl/go1.x.x.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf go1.x.x.linux-amd64.tar.gz
```

```bash
echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.zshrc
source ~/.zshrc
go version
```

<br />

## WSL 2 - Python

```bash
sudo apt update
sudo apt upgrade
sudo apt install python3
sudo apt install python3-pip
```

<br />

### WSL 2 - Jupyter Notebook

```bash
pip3 install notebook

# Run Server: python3 -m notebook
```

<br />

## NodeJS - NextJS

```bash
npm init @eslint/config

yarn add --dev @typescript-eslint/parser @typescript-eslint/eslint-plugin eslint
yarn add --dev eslint-plugin-react-hooks
yarn add --dev --exact prettier
yarn add --dev eslint-config-prettier eslint-plugin-prettier
yarn add --dev eslint-plugin-import-helpers
```

<br />

### NodeJS - NextJS - ESLint
```
//.eslintrc.json
{
    "env": {
        "browser": true,
        "es2021": true
    },
    "settings": {
        "react": {
            "version": "detect"
        }
    },
    "extends": [
        "eslint:recommended",
        "plugin:react/recommended",
        "plugin:@typescript-eslint/recommended",
        "plugin:prettier/recommended",
        "prettier"
    ],
    "parser": "@typescript-eslint/parser",
    "parserOptions": {
        "ecmaVersion": "latest",
        "sourceType": "module"
    },
    "plugins": [
        "react",
        "@typescript-eslint",
        "react-hooks",
        "eslint-plugin-import-helpers"
    ],
    "rules": {
        "react-hooks/rules-of-hooks": "error",
        "react-hooks/exhaustive-deps": "warn",
        "react/react-in-jsx-scope": "off",
        "prettier/prettier": "error",
        "import-helpers/order-imports": [
            "warn",
            {
                "newlinesBetween": "always",
                "groups": [
                    ["/^react/", "/^next/"],
                    ["/@mui/", "/@next/"],
                    "module",
                    "/^@shared/",
                    "/absolute/",
                    [
                        "parent",
                        "sibling",
                        "index"
                    ]
                ],
                "alphabetize": {
                    "order": "asc",
                    "ignoreCase": true
                }
            }
        ]
    }
}
```

<br />

### NodeJS - NextJS - Prettier
```text
//.prettierrc
{
    "trailingComma": "none",
    "semi": true,
    "singleQuote": false
}
```

<br />

### NodeJS - NextJS - VSCode Settings
```text
//.vscode/settings.json
{
    "editor.formatOnSave": false,
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
    }
}
```
