# Script generated with Bloom
pkgdesc="ROS - Localization and navigation for the Jackal."
url='http://ros.org/wiki/multi_jackal_nav'

pkgname='ros-kinetic-multi-jackal-nav'
pkgver='0.0.5_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-move-base'
'ros-kinetic-robot-localization'
'ros-kinetic-roslaunch'
'ros-kinetic-tf'
)

depends=('ros-kinetic-move-base'
'ros-kinetic-robot-localization'
'ros-kinetic-tf'
)

conflicts=()
replaces=()

_dir=multi_jackal_nav
source=()
md5sums=()

prepare() {
    cp -R $startdir/multi_jackal_nav $srcdir/multi_jackal_nav
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

