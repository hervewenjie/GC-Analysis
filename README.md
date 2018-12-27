# GC-Analysis
jdk9

Parallel Scavenge
Heap的实现在psYoungGen.cpp
gc算法实现在psScavenge.cpp

PSScavenge::invoke_no_policy()
  -> create gc task queue
      -> enqueue root task(universe)
      -> enqueue root task(jni_handles)
      ...
      -> enqueue root task(object_synchronizer)
          -> queque execute and wait
