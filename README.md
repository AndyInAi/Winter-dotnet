# Winter-dotnet

```sh

echo "
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy main restricted universe multiverse
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-updates main restricted universe multiverse
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-backports main restricted universe multiverse
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-security main restricted universe multiverse
" > /etc/apt/sources.list

export DEBIAN_FRONTEND=noninteractive

apt update -y

apt install -y wget

wget -O ~/packages-microsoft-prod.deb \
        https://packages.microsoft.com/config/ubuntu/22.04/packages-microsoft-prod.deb

dpkg -i ~/packages-microsoft-prod.deb

apt update -y

apt install -y dotnet-sdk-8.0

if [ ! -d ~/Winter-dotnet ]; then cd ~/ ; git clone https://github.com/AndyInAi/Winter-dotnet.git; fi

cd ~/Winter-dotnet

dotnet run --urls http://0.0.0.0:8080

# starting HTTP server at http://0.0.0.0:8080

```
