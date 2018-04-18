# Script generated with Bloom
pkgdesc="ROS - turtle_tf demonstrates how to write a tf broadcaster and listener with the turtlesim. The tutle_tf_listener commands turtle2 to follow turtle1 around as you drive turtle1 using the keyboard."
url='http://ros.org/wiki/turtle_tf'

pkgname='ros-melodic-turtle-tf'
pkgver='0.2.2_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-melodic-catkin'
'ros-melodic-geometry-msgs'
'ros-melodic-roscpp'
'ros-melodic-rospy'
'ros-melodic-std-msgs'
'ros-melodic-tf'
'ros-melodic-turtlesim'
)

depends=('ros-melodic-geometry-msgs'
'ros-melodic-roscpp'
'ros-melodic-rospy'
'ros-melodic-std-msgs'
'ros-melodic-tf'
'ros-melodic-turtlesim'
)

conflicts=()
replaces=()

_dir=turtle_tf
source=()
md5sums=()

prepare() {
    cp -R $startdir/turtle_tf $srcdir/turtle_tf
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/melodic/setup.bash ] && source /opt/ros/melodic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/melodic \
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

