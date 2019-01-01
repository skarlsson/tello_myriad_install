# tello_myriad_install

#tello stuff

```
sudo apt install sudo libopencv-dev python3-opencv ffmpeg libavdevice-dev libavfilter-dev mplayer
sudo pip3 install imutils pynput pygame av image ffmpeg-python opencv-python
```

```
mkdir tello
cd tello
git clone https://github.com/hanyazou/TelloPy
cd TelloPy
/usr/bin/python3 setup.py bdist_wheel
sudo pip3 install dist/tellopy-*.dev*.whl --upgrade
cd ..
```

```
git clone https://github.com/Ubotica/telloCV.git
cd ..
```

Test your tello
```
cd TelloPy/tellopy/examples
/usr/bin/python3 ./keyboard_and_video.py
```



# get openvino intel
https://software.intel.com/en-us/articles/OpenVINO-Install-Linux

```
cd ~/Downloads/
export VINO_VERSION=2018.5.445
tar -zxf l_openvino_toolkit_p_$VINO_VERSION.tgz
cd l_openvino_toolkit_p_$VINO_VERSION
sudo -E ./install_cv_sdk_dependencies.sh
sudo ./install_GUI.sh

echo "source /opt/intel/computer_vision_sdk/bin/setupvars.sh" >> ~/.bashrc
. ~/.bashrc

cd /opt/intel/computer_vision_sdk/deployment_tools/model_optimizer/install_prerequisites
sudo ./install_prerequisites.sh

sudo usermod -a -G users "$(whoami)"

cd /opt/intel/computer_vision_sdk/install_dependencies
./install_NCS_udev_rules.sh 
```

# reboot and test you installation
```
cd /opt/intel/computer_vision_sdk/deployment_tools/demo/
./demo_squeezenet_download_convert_run.sh -d=MYRIAD
```


