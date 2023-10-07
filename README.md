# linux_install_notes
在linux下安装配置qt环境的记录.目前vcpkg安装测试过的库`opencv`,`numcpp`,`boost`,`onnxruntime-gpu`.

### ubuntu安装后补充安装的包
```bash
sudo apt install git curl zip unzip tar neofetch oneko
```

### ubuntu安装qt补充的包
```bash
sudo apt install libxcb-xinerama0 libxcb-xinerama0-dev libgl1-mesa-dev cmake ninja-build clang clang-format llvm lldb 
```

### 安装qt需要切换国内源,否则龟速
```bash
中科大: http://mirrors.ustc.edu.cn/qtproject/

清华: https://mirrors.tuna.tsinghua.edu.cn/qt/

上海交大: http://mirrors.sjtug.sjtu.edu.cn/qt/

CNNIC: https://mirrors.cnnic.cn/qt/

阿里云: https://mirrors.aliyun.com/qt/

腾讯云: https://mirrors.cloud.tencent.com/qt/

```

### ubuntu安装qt的配色方案
```bash
git clone https://github.com/lilmik/QtCreator-Color-Schemes.git
```

### ubuntu系列使用vcpkg安装opencv必备的库

```bash
sudo apt install bison gperf nasm libx11-dev libxft-dev libxext-dev libdbus-1-dev libxi-dev libxtst-dev libgl1-mesa-dev libgles2-mesa-dev libglu1-mesa-dev libtool libudev-dev libx11-xcb-dev libxcursor-dev libxdamage-dev libxinerama-dev libxrandr-dev build-essential gcc g++ cmake ninja-build python3-distutils pkg-config
```

### ubuntu系列使用qt碰到的问题,并附解决方案
在linux下安装配置clang环境后,无法使用clang编译c++文件,然后提示qt缺少部分库文件.因为未找到`libstdc++-12-dev`对应的更高版本,所以clang整体换为12版.

```bash
sudo apt install clang-12 libstdc++-12-dev libxcb-cursor0 libxcb-cursor-dev
```

### ubuntu安装vcpkg

```bash
cd ~
git clone https://github.com/Microsoft/vcpkg.git
./vcpkg/bootstrap-vcpkg.sh
```

### ubuntu安装vcpkg后配置~/.bashrc

```bash
nano ~/.bashrc

# vcpkg
export PATH="/home/$USER/vcpkg/:$PATH"

source ~/.bashrc
```

### ubuntu系列使用vcpkg安装numcpp必备的库

```bash
sudo apt install autoconf-archive
```


### openSuse使用vcpkg安装opencv的库名和ubuntu不一样，需要使用注意
https://mirrors.ustc.edu.cn/help/opensuse.html
更换国内源，提高更新下载速度，我使用的是openSUSE Tumbleweed版本.
确认当前配置的软件源；
```bash
sudo zypper lr -d
```
禁用原有软件源；
```bash
sudo zypper mr -da
```
对于 openSUSE Tumbleweed，只需执行：
```bash
sudo zypper ar -fcg 'https://mirrors.ustc.edu.cn/opensuse/tumbleweed/repo/oss' USTC:OSS
sudo zypper ar -fcg 'https://mirrors.ustc.edu.cn/opensuse/tumbleweed/repo/non-oss' USTC:NON-OSS
sudo zypper ar -fcg 'https://mirrors.ustc.edu.cn/opensuse/update/tumbleweed' USTC:UPDATE
```
对于 openSUSE Tumbleweed安装完毕后，补充系统基础包包括：
```bash
sudo zypper in opi git nano cmake ninja bash-completion gcc gcc-c++ neofetch 
```

openSUSE Tumbleweed配置使用vcpkg尝试安装opencv，补充安装的包有：
```bash
sudo zypper in bison gperf nasm libdbus-c++-devel libXi-devel libXtst-devel libX11-devel libXft-devel libXext-devel Mesa-libEGL-devel Mesa-libGLESv2-devel Mesa-libGL-devel Mesa-libglapi-devel Mesa-libGLESv3-devel libtool libudev1 libX11-xcb1 libXcursor-devel libXdamage-devel libXinerama-devel libXrandr-devel
```
