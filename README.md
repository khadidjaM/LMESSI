# LMESSI

This is the LMESSI isax based time-series index for Long Sequences.

Input:

• Data File Path. e.g. /mnt/CEA/data/SDSSR.bin
• Query length (number of points). e.g. 1750
• Queries File Path. e.g. /mnt/CEA/query/SDSSRQueries.bin
• Output Directory Path. e.g. /mnt/CEA/result
• Dataset Size (number of points). e.g. 7642056
• Queries size (number of queries). e.g. 100
• K size (number of nearest neighbours to find). e.g. 10
• leaf size. e.g. 50000
• cpu-type (number of cores in number of CPUs). e.g. 42 for 4 cores in 2 CPUs


Install:

autoconf
./configure
make

if you have an error try:

autoreconf
./configure
make

Then, you can run:

./LMESSI --help


Command:

cd bin
./LMESSI −−dataset /mnt/CEA/data/SDSSR.bin −−leaf-size 50000
−−cpu-type 42 −−dataset-size 7642056 −−queries /mnt/CEA/query/SDSSRQueries.bin
−−queries-size 100 −−query-length 1750 −−k-size 10 −−output /mnt/CEA/result/


Output:

• Result file : position and correlation value


PS：the SIMD lower bound distance calculation code is only for 16 segments.  The real distance calculation is only for Multiples of 8.
if you use other parameters please use their SISD version (remove "_SIMD").
