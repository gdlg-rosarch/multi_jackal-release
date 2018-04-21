# Script generated with Bloom
pkgdesc="ROS - The Jackal simulation base that combines all components."
url='http://ros.org/wiki/multi_jackal_base'

pkgname='ros-kinetic-multi-jackal-base'
pkgver='0.0.5_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-roslaunch'
)

depends=('ros-kinetic-controller-manager'
'ros-kinetic-gazebo-ros'
'ros-kinetic-interactive-marker-twist-server'
'ros-kinetic-multi-jackal-control'
'ros-kinetic-multi-jackal-description'
'ros-kinetic-multi-jackal-nav'
'ros-kinetic-robot-localization'
'ros-kinetic-robot-state-publisher'
'ros-kinetic-tf'
'ros-kinetic-urdf'
'ros-kinetic-xacro'
)

conflicts=()
replaces=()

_dir=multi_jackal_base
source=()
md5sums=()

prepare() {
    cp -R $startdir/multi_jackal_base $srcdir/multi_jackal_base
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

