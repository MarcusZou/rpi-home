# Raspberry Pi at Home



Raspberry PI at Home

| rpi_name | ip_addr       | specs                                                        | os              | user | password     | relocated? |
| -------- | ------------- | ------------------------------------------------------------ | --------------- | ---- | ------------ | ---------- |
| Ed-Rpi3B | 192.168.0.133 | [rpi3b_spec](https://www.raspberrypi.com/products/raspberry-pi-3-model-b/) | Raspbian-buster | pi   | Pi=3.1415926 | Yes to YVR |
| Mc-Rpi2B | 192.168.0.134 | [rpi-2b_spec](https://www.raspberrypi.com/products/raspberry-pi-2-model-b/) | Raspbian-buster | pi   | Pi=3.1415926 | No in YYC  |
|          |               |                                                              |                 |      |              |            |

Note: All the RPi can be VNC-connected.

## The best way to upgrade Python to be 3.8.12

First install the dependencies needed to build:

```
sudo apt-get update
sudo apt-get install -y build-essential tk-dev libncurses5-dev libncursesw5-dev libreadline6-dev libdb5.3-dev libgdbm-dev libsqlite3-dev libssl-dev libbz2-dev libexpat1-dev liblzma-dev zlib1g-dev libffi-dev
```

Compile (yes… it takes a while, grab a coffee and get me one to!!)

```
wget https://www.python.org/ftp/python/3.8.12/Python-3.8.12.tar.xz
tar xf Python-3.8.12.tar.xz
cd Python-3.8.12
./configure --enable-optimizations --prefix=/usr
make
sudo make altinstall
```

And remove the files you don’t need anymore

```
cd ..
sudo rm -r Python-3.8.12
rm Python-3.8.12.tar.xz
. ~/.bashrc
```

Let’s make Python 3.8 the default version, make aliases

```
sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.8.12
```

And verify:

```
python -V
```

That's it.

