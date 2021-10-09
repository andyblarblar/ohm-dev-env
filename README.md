### Ohm-dev-env

This repository holds a dev environment for working with Ohm in ROS1 Noetic. It's designed for use with vscode and docker, to spin up a pre configured ROS
environment even on windows or mac machines.

# Requirements 

You need a docker engine + docker compose installed. This means docker desktop for windows or mac. 

You will also need vscode with the remote containers extension installed.

# Usage

root and vscode users have the password of 1234.

1. Clone this repo using ``` git clone https://github.com/andyblarblar/ohm-dev-env --recurse-submodules --remote```. This will both clone this repo as well as the latest commit from Ohm master in src/Ohm.

2. Open vscode in the cloned folder. This should have a 'open in remote container' prompt appear in the bottom right. Click this. If this does not show up, then click the green icon in the bottom right and do the same.

3. This may take a while to build depending on the machine you're on. Once done, it will reopen vscode in the container.

4. Now, try to run ``` catkin build ```. If it fails due to missing dependencies, then run `rosdep install --from-paths src --ignore-src -r -y`. 

5. Ohm is a submodule, so changes made to it will be attempted to commit to the main Ohm repo. You may want to change this submodule to point to a fork to solve this.

# Tips

- vscode's terminal can get very slow. Try clearing it to solve this issue.
- Modifying the dockerfile will require you to rebuild the image. To do this, click on the remotes button and select `rebuild container`.
- The `rocker` program can be used to run gui applications using this container. This is a bit advanced, so I won't cover all the details here. I may add better gui support in the future though.