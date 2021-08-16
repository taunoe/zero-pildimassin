# Zero Pildimassin

Raspberry Pi Zero W + kaamera

## SSH

* [SSH: Remote control your Raspberry Pi](https://magpi.raspberrypi.org/articles/ssh-remote-control-raspberry-pi)

Activate SSH in Raspbian.

Get Raspberry IP address:

    hostname -I
    
or just hostname:

    hostname
    
Connect via SSH: username@hostname or username@ip.

Example:

    ssh pi@192.168.8.1

### Graphical interface (X session) over SSH

    ssh -Y pi@192.168.8.1
    scratch &
    
### Copy files from your local computer to Pi

    scp [source] pi@[IP]:[destination]
    scp Downloads\MagPi83.pdf pi@192.168.0.41:/home/pi/MagPi

## Install Go-lang

* [How to Install Go on the Raspberry Pi](https://www.jeremymorgan.com/tutorials/raspberry-pi/install-go-raspberry-pi/)

Armv6 version for Raspberry Pi.

    mkdir ~/src && cd ~/src
    wget https://dl.google.com/go/go1.16.7.linux-armv6l.tar.gz
    sudo tar -C /usr/local -xzf go1.16.7.linux-armv6l.tar.gz
    rm go1.16.7.linux-armv6l.tar.gz
    
Edit `~/.profile` file. Add the following:

    PATH=$PATH:/usr/local/go/bin
    GOPATH=$HOME/go

Update your shell and check Go version:

    source ~/.profile
    go version
    
## Install GoCV

The GoCV package provides Go language bindings for the OpenCV 4 computer vision library.

* [GoCV Raspbian installation](https://github.com/hybridgroup/gocv#raspbian)

    cd src
    git clone https://github.com/hybridgroup/gocv.git
    cd gocv
    make install_raspi
    

## Links

* [Remote Access](https://www.raspberrypi.org/documentation/computers/remote-access.html)
