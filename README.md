# StreamingHLL_withVectors

Cardinality estimation, also known as count-distinct, is the problem of finding the number of different elements in a set with repeated elements. Among the many approximate algorithms proposed for this task, HyperLogLog (HLL) has established itself as the state of the art  due to its ability to accurately estimate cardinality over a large range of values using a small memory footprint. When elements arrive in a stream, as in the case of most networking applications, improved techniques are possible.
We specifically propose a new algorithm that improves the accuracy of cardinality estimation by grouping counters, and by using their new organization to further track all updates within a given counter size range (compared with just the last update as in the standard HLL). Results show that when using the same number of counters, one configuration of the new scheme reduces the relative error by approximately 0.86x using the same amount of memory as the streaming HLL and another configuration achieves a similar accuracy reducing the memory needed by approximately 0.85x.

## Requirements
```
sudo apt-get install python2.7
python2.7 -m pip install xxhash
python2.7 -m pip install numpy 
python2.7 -m pip install scipy
python2.7 -m pip install dpkt
```


## Simulation - Synthetic stream
```
python2.7 StreamHLL_Vec-uniformsim.py  
```

## Simulation - Stream from pcap
```
python2.7 StreamHLL_Vec-pcapsim.py <file_list>
```

File list is a text file in which each line reports the path to the trace to test. Multiple line in this file will produce multiple independent analysis.
