# Script generated with Bloom
pkgdesc="ROS - Creates the joint and velocity controllers."
url='http://ros.org/wiki/multi_jackal_control'

pkgname='ros-kinetic-multi-jackal-control'
pkgver='0.0.5_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-controller-manager'
'ros-kinetic-diff-drive-controller'
'ros-kinetic-gazebo-ros-control'
'ros-kinetic-hector-gazebo-plugins'
'ros-kinetic-interactive-marker-twist-server'
'ros-kinetic-joint-state-controller'
'ros-kinetic-nav-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-roslaunch'
'ros-kinetic-std-msgs'
'ros-kinetic-tf'
'ros-kinetic-urdf'
'ros-kinetic-xacro'
)

depends=('ros-kinetic-controller-manager'
'ros-kinetic-diff-drive-controller'
'ros-kinetic-gazebo-ros-control'
'ros-kinetic-hector-gazebo-plugins'
'ros-kinetic-interactive-marker-twist-server'
'ros-kinetic-joint-state-controller'
'ros-kinetic-nav-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-std-msgs'
'ros-kinetic-tf'
'ros-kinetic-urdf'
'ros-kinetic-xacro'
)

conflicts=()
replaces=()

_dir=multi_jackal_control
source=()
md5sums=()

prepare() {
    cp -R $startdir/multi_jackal_control $srcdir/multi_jackal_control
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

