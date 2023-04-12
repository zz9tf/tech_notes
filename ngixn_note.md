# Nginx

Here is a note for nginx install and usage on mac

## Install method

Here I used method from [How to Set Up XGINX on Mac for test](https://adamtheautomator.com/nginx-on-mac/)

The terminal script is:
```
# Create a source folder under your home directory
mkdir ~/src && cd ~/src

# Download and extract the PCRE source
curl -OL https://ftp.exim.org/pub/pcre/pcre-8.45.tar.gz
tar -xf pcre-8.45.tar.gz && rm pcre-8.45.tar.gz

# Download and extract the OpenSSL source files
curl -OL http://www.openssl.org/source/openssl-1.1.1m.tar.gz
tar -xf openssl-1.1.1m.tar.gz && rm openssl-1.1.1m.tar.gz

# Download and extract the NGINX source files
curl -OL http://nginx.org/download/nginx-1.20.2.tar.gz
tar -xf nginx-1.20.2.tar.gz && rm nginx-1.20.2.tar.gz
# List the files/folders in the working directory
ls -l

# Enter the NGINX source folder
cd nginx-1.20.2

# Create the NGINX configuration
## Parameters:
## --with-pcre=../pcre-8.45/ : Specifies the PCRE source location
## --with-http_ssl_module : Enables the HTTPS support
## --with-openssl=../openssl-1.1.1m/ : Specifies the OpenSSL source. Required by the http_ssl_module
./configure --with-pcre=../pcre-8.45/ --with-http_ssl_module --with-openssl=../openssl-1.1.1m/

# Compile NGINX
make
# Install NGINX
sudo make install
# Append NGINX to the /etc/paths file
echo /usr/local/nginx/sbin | sudo tee -a /etc/paths
```

Terminate my term2, then run:

```
sudo nginx
```

Now, I can see my local nginx webpage.
![image](https://user-images.githubusercontent.com/77183284/231596648-8bd9304a-bbeb-481d-914a-dd6e83342139.png)


## Usage

Location of default webpage directory

```
/usr/local/nginx/html
```

Location of config file directory

```
/usr/local/nginx/conf
```

The useful file for further configuration, which is located at `/usr/local/nginx/conf/nginx.conf`

<img width="182" alt="image" src="https://user-images.githubusercontent.com/77183284/231597395-a307540c-cad7-4599-842e-69182d499166.png">

Stop nginx(ie. to stop default web port 80)

```
sudo nginx -s stop
```

Start nginx

```
sudo nginx
```
