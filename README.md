# shuffle_lock
Implementation of shuffle lock on linux kernel v6.2.

[paper](https://gts3.org/assets/papers/2019/kashyap:shfllock.pdf)

![Static Badge](https://img.shields.io/badge/linux-6.2.0-EABE41)

## 1) Installation
### Linux
```sh
apt-get install build-essential libncurses5 libncurses5-dev bin86 kernel-package libssl-dev bison flex libelf-dev

git clone --depth 1 --branch v6.2 git://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git

cd linux
make defconfig
make -j
make modules
make install
make modules_install
reboot
```

### Linter: clang-format
```sh
wget https://apt.llvm.org/llvm.sh
chmod +x llvm.sh
sudo ./llvm.sh 11
```

## 2) Execute Kernel Module
### 1. build
```sh
cd modules/shuffle_lock
make
```
### 2. load
```sh
insmod shuffle_lock.ko
```
### 3. unload
```sh
rmmod shuffle_lock
```
### 4. clean
```sh
make clean
```
