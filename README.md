기존 ROS의 Logging module에서 UTC 기준 Unix time으로 timestamping 되던 것을
ISO Format Local time으로 찍히도록 변경한 구현입니다.
아래와 같이 빌드한 후 catkin workspace에서 catkin clean 이후 catkin build를 수행하시면 됩니다.

```
cd ~/
git clone git@github.com:nearthlab/rosconsole.git
cd rosconsole
mkdir build
cd build
cmake ..
make
echo "source $HOME/rosconsole/build/devel/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

그리고 아래와 같이 rospy logging module을 ros 디렉토리로 복사해주세요
```
cd ~/rosconsole
sudo rm /opt/ros/kinetic/lib/python2.7/dist-packages/rosgraph/roslogging.pyc
sudo cp roslogging.py /opt/ros/kinetic/lib/python2.7/dist-packages/rosgraph/roslogging.py
```
