# Script generated with Bloom
pkgdesc="ROS - Spawns the Jackal model."
url='http://ros.org/wiki/multi_jackal_description'

pkgname='ros-kinetic-multi-jackal-description'
pkgver='0.0.5_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-gazebo-ros'
'ros-kinetic-lms1xx'
'ros-kinetic-nav-msgs'
'ros-kinetic-pointgrey-camera-description'
'ros-kinetic-pointgrey-camera-driver'
'ros-kinetic-robot-state-publisher'
'ros-kinetic-roslaunch'
'ros-kinetic-tf'
'ros-kinetic-urdf'
'ros-kinetic-xacro'
)

depends=('ros-kinetic-gazebo-ros'
'ros-kinetic-lms1xx'
'ros-kinetic-nav-msgs'
'ros-kinetic-pointgrey-camera-description'
'ros-kinetic-pointgrey-camera-driver'
'ros-kinetic-robot-state-publisher'
'ros-kinetic-tf'
'ros-kinetic-urdf'
'ros-kinetic-xacro'
)

conflicts=()
replaces=()

_dir=multi_jackal_description
source=()
md5sums=()

prepare() {
    cp -R $startdir/multi_jackal_description $srcdir/multi_jackal_description
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

