examples
========

Code Examples

Blog

http://psy-lob-saw.blogspot.com/2013/03/single-producerconsumer-lock-free-queue.html

Cache lines size 64 byte.


cache line 1(64byte)  -------Object 1,Object 2 (Unpadded objects in same cache line)
cache line 2 (64 byte)  ------- Padded Object1(7 empty single long)
cache line 2 (64 byte)  ------- Padded Object2(7 empty single long)


If two threads access cache line 1 for accessing Object 1 and Object 2,one of the thread have to wait for the other thread execution. Because the Other thread owns the ownership of cache line 1.

If the objects are padded (64 bytes.) Then there is no need to wait for the ownership of the cache line,since Objects are in the different cache line.

Its Synchronisation in kind in hardware level.
