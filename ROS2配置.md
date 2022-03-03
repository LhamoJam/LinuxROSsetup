+ 每次启用: `call C:\opt\ros\foxy\x64\local_setup.bat`
+ dashing提示colcon找不到:`pip3 install -U colcon-common-extensions`
+ 各种找不到问题: https://www.cnblogs.com/tuxinbang/p/10705419.html
  ```shell
  sudo apt update && sudo apt install -y \
  build-essential \
  cmake \
  git \
  python3-colcon-common-extensions \
  python3-pip \
  python-rosdep \
  python3-vcstool \
  wget

  sudo -H python3 -m pip install -U \
  argcomplete \
  flake8 \
  flake8-blind-except \
  flake8-builtins \
  flake8-class-newline \
  flake8-comprehensions \
  flake8-deprecated \
  flake8-docstrings \
  flake8-import-order \
  flake8-quotes \
  pytest-repeat \
  pytest-rerunfailures
  ```