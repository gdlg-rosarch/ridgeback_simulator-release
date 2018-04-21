# Script generated with Bloom
pkgdesc="ROS - Plugin which uses directional friction to simulate mecanum wheels."
url='http://wiki.ros.org/mecanum_gazebo_plugin'

pkgname='ros-kinetic-mecanum-gazebo-plugin'
pkgver='0.0.2_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('gazebo'
'ros-kinetic-catkin'
'ros-kinetic-rosconsole'
'ros-kinetic-roslint'
)

depends=('gazebo'
'ros-kinetic-rosconsole'
)

conflicts=()
replaces=()

_dir=mecanum_gazebo_plugin
source=()
md5sums=()

prepare() {
    cp -R $startdir/mecanum_gazebo_plugin $srcdir/mecanum_gazebo_plugin
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

