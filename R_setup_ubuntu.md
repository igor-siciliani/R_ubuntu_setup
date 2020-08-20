# Install for Data Science
Guide to install R version on Ubuntu 18.04.
Open your linux terminal to run this guide and follow the next steps.

### verify your ubuntu distribution

```
lsb_release -a
```

### choose R version to install on https://cloud.r-project.org/bin/linux

```
sudo add-apt-repository 'deb https://cloud.r-project.org/bin/linux/ubuntu bionic-cran35/'
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9
sudo apt update
sudo apt install r-base
```

## install linux libs

```
sudo apt-get update && sudo apt-get install -y \
pandoc \
pandoc-citeproc \
vim \ 
libgeos-dev \ 
libpq-dev \
libgdal-dev \
libudunits2-dev \
libcurl4-gnutls-dev \
libcurl4-openssl-dev \
libcairo2-dev \
libxt-dev \
libpcre2-dev \
libxml2-dev \
libfontconfig1-dev\
xtail \
wget
```
## Install Java

```
wget https://download.java.net/java/ga/jdk11/openjdk-11_linux-x64_bin.tar.gz -O /tmp/openjdk-11_linux-x64_bin.tar.gz
sudo mkdir -p /usr/lib/jvm
sudo tar xfvz /tmp/openjdk-11_linux-x64_bin.tar.gz --directory /usr/lib/jvm
rm -f /tmp/openjdk-11_linux-x64_bin.tar.gz
```

## Config JAVA

Set JAVA as an environment variable:

```
sudo nano /etc/environment
```

Then , write: 
```
JAVA_HOME="/usr/lib/jvm/jdk-11/"  
```

Save the file (crtl+X > Yes) and run:

```
sudo R CMD javareconf
```


## Installing rJava (Optional)

```
sudo apt-get -y update && sudo apt-get install -y \
r-cran-rjava
```

If you get some error try to add an extra PPA that 
provides newer version of extra R packages

- example:
```
sudo add-apt-repository ppa:marutter/c2d4u3.5
sudo apt update
sudo apt install r-cran-rjava
```

## Installing ODBC stuff
```
sudo apt-get install -y \
curl

sudo curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add -
sudo curl https://packages.microsoft.com/config/debian/9/prod.list > /etc/apt/sources.list.d/mssql-release.list
sudo apt-get update

sudo apt-get install -y \
unixodbc-dev

sudo apt-get update -qyy
```
## Install MySQL client:

```
sudo apt-get install -y libmysqlclient-dev
```


## More linux libs (Optional)

```
sudo apt-get update && sudo apt-get install -y \
libgsl-dev \
libudunits2-dev
```

