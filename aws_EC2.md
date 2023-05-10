# Deploy project on aws EC2 with docker + react + express + Django


## Install

### Install docker

```
sudo yum install docker -y
```

### Install docker compose

From [link](https://stackoverflow.com/questions/63708035/installing-docker-compose-on-amazon-ec2-linux-2-9kb-docker-compose-file)

```
sudo curl -L https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

docker-compose version

sudo service docker start
```

You will get:

<img width="277" alt="image" src="https://user-images.githubusercontent.com/77183284/231896125-8f855f51-e883-4c2e-891e-7f038131c9af.png">


### Install node

From [link](https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/setting-up-node-on-ec2-instance.html)

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
. ~/.nvm/nvm.sh
nvm install 16
node -e "console.log('Running Node.js ' + process.version)"
```

### Install git

```
sudo yum install git
```
### Setup sshkey for ec2

```
ssh-keygen -t rsa -C "your-email@gmail.com"
```

Then

```
cat ~/.ssh/id_rsa.pub
```

### Domain name

from [link](https://www.youtube.com/watch?v=hRSj2n-XKGM)
