# linux_install_notes
在linux下安装配置qt环境的记录。目前vcpkg安装测试过的库`opencv`,`numcpp`,`boost`,`onnxruntime-gpu`.

### ubuntu安装qt补充的库
```bash
sudo apt install libxcb-xinerama0 libxcb-xinerama0-dev libgl1-mesa-dev clang clang-format llvm lldb
```

### ubuntu系列使用vcpkg安装opencv必备的库

```bash
sudo apt install bison gperf nasm libx11-dev libxft-dev libxext-dev libdbus-1-dev libxi-dev libxtst-dev libgl1-mesa-dev libgles2-mesa-dev libglu1-mesa-dev libtool libudev-dev libx11-xcb-dev libxcursor-dev libxdamage-dev libxinerama-dev libxrandr-dev build-essential gcc g++ cmake ninja-build python3-distutils pkg-config
```



### ubuntu系列使用vcpkg安装numcpp必备的库

```bash
sudo apt install autoconf-archive
```



### openSuse使用vcpkg安装opencv有些库无法找到替代,暂时未成功安装
