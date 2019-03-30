# Multi-MAV GCS

Application for managing multiple Pixhawk-based ROS robots. This was supposed to be part of my senior design project, but we had some... how do I put this diplomatically... *team issues,* and I was even worse at managing people who don't care then than I am now. So, in early May, I threw this together in a few days so that we had at least *something* to present.

From https://ttech.click/multi-mav-gcs:

## Setting up the Multi-MAV GCS

### Dependencies

- [ROS Kinetic](https://wiki.ros.org/kinetic)
    - [mavros](https://wiki.ros.org/mavros)
- [Python 2.7](https://docs.python.org/2.7/)
    - [PyGObject](https://pygobject.readthedocs.io/)
    - [PIL](https://pillow.readthedocs.io/)
    - [requests](https://python-requests.org/)
    - [requests-cache](https://requests-cache.readthedocs.io/)
- [GTK+ 3.0](https://www.gtk.org/)
- [git](https://git-scm.com/)

On Ubuntu, follow the [ROS installation instructions][1], and then run:

```shell
$ sudo apt-get install ros-kinetic-mavros \
        python-{gi,gi-dev,gi-cairo,pil,requests,requests-cache} \
        libgtk-3-{0,dev} gir1.2-gtk-3.0 git
```

### Installation

1.  Install the dependencies (see above).

2.  Create a catkin workspace (see [Creating a workspace for catkin][2]) and
    `cd` into its `src` directory.

3.  Clone `multi_mav_gcs` into the directory with `git clone
    https://github.com/NighttimeDriver50000/multi_mav_gcs.git`.

4.  `cd` up out of the `src` directory, and run `catkin_make`.

### Running

1.  Start up the mavros nodes in their respective [namespaces][3]. You don't
    actually have to do this before the other steps. You do need to have a
    running `roscore` before step 3, though.

2.  In the catkin workspace, run `source devel/setup.bash` (or the appropriate
    setup script if your shell isn't `bash`).

3.  Run `rosrun multi_mav_gcs multi_mav_gcs.py`.

4.  Add the namespaces using the textbox and button at the top of the sidebar.

[1]: https://wiki.ros.org/kinetic/Installation/Ubuntu
[2]: https://wiki.ros.org/catkin/Tutorials/create_a_workspace
[3]: https://wiki.ros.org/roslaunch/XML/group
