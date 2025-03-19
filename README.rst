===========
README
===========

HyperCache: Efficient Page Cache Virtualization for Containerized Image Service


Building
========

HyperCache is multi-platform software intended to be buildable on all modern
Linux platforms, OS-X, Win32 (via the Mingw64 toolchain) and a variety
of other UNIX targets. The simple steps to build HyperCache are:

.. code-block:: shell

  mkdir build
  cd build
  ../configure
  make


.. code-block:: shell
  ./build/qemu-system-x86_64 -machine pc,accel=kvm,usb=off -enable-kvm \
  -smp 2 -cpu host \
  -m 2G,slots=2,maxmem=4G \
  -kernel /mnt/bzImage \
  -append "rootwait quiet root=/dev/vda rw console=ttyS0" \
  -drive "file=/mnt/ubuntu20.04.img,if=virtio,format=raw" \
  -object "rng-random,filename=/dev/urandom,id=rng0" \
  -nographic
