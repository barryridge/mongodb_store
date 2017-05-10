
mongodb_store
==================

This package wraps up MongoDB database server in ROS, allowing it to be used to store configuration parameters.

See `mongodb_store/README.md` for further details

## Installation for Ubuntu 16.04/ROS Kinetic

This fork was created for easing upgrades to Ubuntu 16.04/ROS Kinetic.
It relies on a legacy version of `MongoDB` and should therefore be
considered as a temporary solution until such a time as `mongodb_store`
is updated to use the latest `MongoDB` API.

### Prerequisites

Install the [26compat](https://github.com/mongodb/mongo-cxx-driver/tree/26compat) branch of
[mongodb-cxx-driver](https://github.com/mongodb/mongo-cxx-driver) as follows:
```bash
sudo apt-get install scons mongodb
git clone -b 26compat https://github.com/mongodb/mongo-cxx-driver.git
cd mongo-cxx-driver
sudo scons --full --use-system-boost --prefix=/usr/local --ssl --sharedclient --disable-warnings-as-errors install-mongoclient
```

### Installation
The `mongodb-dev` ROS package is no longer available under Kinetic, so the
rosdep references to it have been removed in `package.xml` in both the
`mongodb_store` and `mongodb_log` packages in this fork.
Just clone into `catkin_ws` and build as usual:
```bash
cd ~/catkin_ws/src
git clone https://github.com/barryridge/mongodb_store
cd ..
catkin_make
```
