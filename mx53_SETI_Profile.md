# Profiling SETI@Home on Cortex-A8 #

mounting rootfs from SATA.
```

Tue Aug 30 04:13:34 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted CPU_CYCLES events (Number of CPU cycles) with a unit mask of 0x00 (No unit mask) count 100000
CPU_CYCLES:100000|
  samples|      %|
------------------
  1985153 99.4009 seti_boinc
	CPU_CYCLES:100000|
	  samples|      %|
	------------------
	  1985026 99.9936 seti_boinc
	      127  0.0064 [vectors] (tgid:4827 range:0xffff0000-0xffff1000)
     6316  0.3163 oprofiled
	CPU_CYCLES:100000|
	  samples|      %|
	------------------
	     6313 99.9525 oprofiled
	        3  0.0475 [vectors] (tgid:5286 range:0xffff0000-0xffff1000)
     2742  0.1373 libc-2.11.1.so
     1290  0.0646 bash
	CPU_CYCLES:100000|
	  samples|      %|
	------------------
	     1263 97.9070 bash
	       27  2.0930 [vectors] (tgid:5387 range:0xffff0000-0xffff1000)
      718  0.0360 ld-2.11.1.so
      311  0.0156 libavahi-common.so.3.5.1
      174  0.0087 libapt-pkg-libc6.10-6.so.4.8.0
      166  0.0083 libavahi-core.so.6.0.1
       44  0.0022 ntpd
       32  0.0016 avahi-daemon
	CPU_CYCLES:100000|
	  samples|      %|
	------------------
	       30 93.7500 [vectors] (tgid:3356 range:0xffff0000-0xffff1000)
	        2  6.2500 avahi-daemon
       31  0.0016 tr
       24  0.0012 apt-get
	CPU_CYCLES:100000|
	  samples|      %|
	------------------
	       19 79.1667 apt-get
	        5 20.8333 [vectors] (tgid:4505 range:0xffff0000-0xffff1000)
       17 8.5e-04 gawk
       15 7.5e-04 grep
       15 7.5e-04 libpthread-2.11.1.so
       14 7.0e-04 rsyslogd
	CPU_CYCLES:100000|
	  samples|      %|
	------------------
	       13 92.8571 rsyslogd
	        1  7.1429 [vectors] (tgid:3135 range:0xffff0000-0xffff1000)
       12 6.0e-04 sudo
	CPU_CYCLES:100000|
	  samples|      %|
	------------------
	       10 83.3333 sudo
	        2 16.6667 [vectors] (tgid:5387 range:0xffff0000-0xffff1000)
       10 5.0e-04 dash
        6 3.0e-04 libpam.so.0.82.2
        5 2.5e-04 libdl-2.11.1.so
        3 1.5e-04 libncurses.so.5.7
        3 1.5e-04 ftp
	CPU_CYCLES:100000|
	  samples|      %|
	------------------
	        2 66.6667 ftp
	        1 33.3333 [vectors] (tgid:4508 range:0xffff0000-0xffff1000)
        3 1.5e-04 libstdc++.so.6.0.13
        2 1.0e-04 mkdir
        2 1.0e-04 libcrypto.so.0.9.8
        2 1.0e-04 id
        1 5.0e-05 cat
        1 5.0e-05 ls
        1 5.0e-05 libgcc_s.so.1
        1 5.0e-05 libm-2.11.1.so
        1 5.0e-05 librt-2.11.1.so
        1 5.0e-05 imuxsock.so
        1 5.0e-05 cron
        1 5.0e-05 sshd
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted CPU_CYCLES events (Number of CPU cycles) with a unit mask of 0x00 (No unit mask) count 100000
samples  %        image name               symbol name
765953   38.5841  seti_boinc               top_sum2(float**, PoTPlan*)
438399   22.0839  seti_boinc               top_sum3(float**, PoTPlan*)
387164   19.5030  seti_boinc               top_sum4(float**, PoTPlan*)
334930   16.8717  seti_boinc               top_sum5(float**, PoTPlan*)
12037     0.6064  seti_boinc               sw_sum2_t31(float**, PoTPlan*)
7250      0.3652  seti_boinc               find_pulse(float const*, int, float, int, int)
6997      0.3525  seti_boinc               t_funct(int, int, int)
2987      0.1505  seti_boinc               strchr
2505      0.1262  seti_boinc               __ieee754_log
2497      0.1258  seti_boinc               n1_64
2241      0.1129  seti_boinc               t1_32
1640      0.0826  seti_boinc               analyze_pot(float*, int, ChirpFftPair_t&)
1606      0.0809  seti_boinc               v_BaseLineSmooth(float (*) [2], int, int, int)
1599      0.0805  seti_boinc               Laligned
1520      0.0766  seti_boinc               ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
1355      0.0683  seti_boinc               n1_32
1269      0.0639  seti_boinc               t1_16
1074      0.0541  seti_boinc               q1_8
863       0.0435  seti_boinc               __divsi3
826       0.0416  seti_boinc               t1_8
779       0.0392  seti_boinc               t1_4
768       0.0387  seti_boinc               q1_4
614       0.0309  seti_boinc               lcgf(double, double)
610       0.0307  seti_boinc               v_GetPowerSpectrum(float (*) [2], float*, int)
596       0.0300  seti_boinc               find_triplets(float const*, int, float, int, int)
587       0.0296  seti_boinc               __ieee754_pow
513       0.0258  seti_boinc               _int_malloc
456       0.0230  seti_boinc               memcpy
441       0.0222  seti_boinc               __exp1
366       0.0184  seti_boinc               n1_8
310       0.0156  seti_boinc               malloc
296       0.0149  seti_boinc               memset
289       0.0146  seti_boinc               FindSpikes(float*, int, int, SETI_WU_INFO&)
249       0.0125  seti_boinc               time_to_ra_dec(double, double*, double*)
226       0.0114  seti_boinc               SpikeProgressUnits(int)
221       0.0111  seti_boinc               logl
218       0.0110  seti_boinc               _int_free
180       0.0091  seti_boinc               GetPulsePoTLen(long, int*, int*)
177       0.0089  seti_boinc               analysis_config::analysis_config()
166       0.0084  seti_boinc               malloc_consolidate
145       0.0073  seti_boinc               calc_detection_freq(double, double, double)
133       0.0067  seti_boinc               free
127       0.0064  [vectors] (tgid:4827 range:0xffff0000-0xffff1000) [vectors] (tgid:4827 range:0xffff0000-0xffff1000)
118       0.0059  seti_boinc               workunit_grp::workunit_grp()
112       0.0056  seti_boinc               pulse::pulse()
100       0.0050  seti_boinc               GetProgressUnitSize(int, int)
99        0.0050  seti_boinc               operator new(unsigned int)
93        0.0047  seti_boinc               cnvt_bin_hz(int, int)
90        0.0045  seti_boinc               seti_analyze(ANALYSIS_STATE&)
85        0.0043  seti_boinc               splitter_config::splitter_config()
83        0.0042  seti_boinc               tape::tape()
72        0.0036  seti_boinc               powl
60        0.0030  seti_boinc               fraction_done(double, double)
57        0.0029  seti_boinc               data_description_t::data_description_t()
52        0.0026  seti_boinc               operator delete(void*)
50        0.0025  seti_boinc               result::result()
49        0.0025  seti_boinc               subband_description_t::subband_description_t()
48        0.0024  seti_boinc               recorder_config::recorder_config()
46        0.0023  seti_boinc               workunit_header::workunit_header()
44        0.0022  seti_boinc               PULSE_INFO::PULSE_INFO()
40        0.0020  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
35        0.0018  seti_boinc               PULSE_INFO::~PULSE_INFO()
35        0.0018  seti_boinc               __ieee754_log10
35        0.0018  seti_boinc               receiver_config::receiver_config()
34        0.0017  seti_boinc               fftwf_execute_dft
32        0.0016  seti_boinc               SPIKE_INFO::~SPIKE_INFO()
32        0.0016  seti_boinc               boinc_fraction_done
31        0.0016  seti_boinc               isnanl
27        0.0014  seti_boinc               floorf
24        0.0012  seti_boinc               invert_lcgf(float, float, float)
24        0.0012  seti_boinc               spike::spike()
21        0.0011  seti_boinc               fftwf_malloc
21        0.0011  seti_boinc               timer_handler()
20        0.0010  seti_boinc               T.9826
20        0.0010  seti_boinc               log10l
20        0.0010  seti_boinc               worker_signal_handler(int)
17       8.6e-04  seti_boinc               __ieee754_fmod
16       8.1e-04  seti_boinc               __libc_enable_asynccancel
15       7.6e-04  seti_boinc               T.9822
14       7.1e-04  seti_boinc               apply
14       7.1e-04  seti_boinc               fmodl
13       6.5e-04  seti_boinc               PulseProgressUnits(double, int)
13       6.5e-04  seti_boinc               calloc_a(unsigned int, unsigned int, unsigned int)
11       5.5e-04  seti_boinc               __aeabi_read_tp
11       5.5e-04  seti_boinc               nanosleep
10       5.0e-04  seti_boinc               fftwf_kernel_malloc
9        4.5e-04  seti_boinc               SPIKE_INFO::SPIKE_INFO()
9        4.5e-04  seti_boinc               finite
8        4.0e-04  seti_boinc               boinc_sleep(double)
7        3.5e-04  seti_boinc               GaussianProgressUnits()
7        3.5e-04  seti_boinc               T.9827
7        3.5e-04  seti_boinc               __default_sa_restorer_v2
7        3.5e-04  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> > x_setiathome_decode<unsigned char>(char const*, unsigned int)
7        3.5e-04  seti_boinc               usleep
6        3.0e-04  seti_boinc               TripletProgressUnits()
6        3.0e-04  seti_boinc               fftwf_free
5        2.5e-04  seti_boinc               T.9831
5        2.5e-04  seti_boinc               apply
5        2.5e-04  seti_boinc               dtime()
5        2.5e-04  seti_boinc               getrusage
4        2.0e-04  seti_boinc               fftwf_kernel_free
4        2.0e-04  seti_boinc               malloc_a(unsigned int, unsigned int)
4        2.0e-04  seti_boinc               timer_thread(void*)
3        1.5e-04  seti_boinc               apply_dit
3        1.5e-04  seti_boinc               free_a(void*)
3        1.5e-04  seti_boinc               gettimeofday
3        1.5e-04  seti_boinc               memmove
2        1.0e-04  seti_boinc               ChirpProgressUnits()
2        1.0e-04  seti_boinc               ____libc_enable_asynccancel_veneer
2        1.0e-04  seti_boinc               boinc_worker_thread_cpu_time
2        1.0e-04  seti_boinc               workunit_grp::operator=(workunit_grp const&)
1        5.0e-05  seti_boinc               SPIKE_INFO::operator=(SPIKE_INFO const&)
1        5.0e-05  seti_boinc               __libc_disable_asynccancel
1        5.0e-05  seti_boinc               apply
1        5.0e-05  seti_boinc               apply
1        5.0e-05  seti_boinc               strcpy
1        5.0e-05  seti_boinc               strlen
 
 
Tue Aug 30 04:17:29 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L2_ACCESS events (Any access to L2 cache) with a unit mask of 0x00 (No unit mask) count 10000
  L2_ACCESS:10000|
  samples|      %|
------------------
   177144 99.6411 seti_boinc
	  L2_ACCESS:10000|
	  samples|      %|
	------------------
	   177057 99.9509 seti_boinc
	       87  0.0491 [vectors] (tgid:4827 range:0xffff0000-0xffff1000)
      234  0.1316 libc-2.11.1.so
      179  0.1007 bash
      157  0.0883 ld-2.11.1.so
       14  0.0079 oprofiled
        9  0.0051 libapt-pkg-libc6.10-6.so.4.8.0
        8  0.0045 gawk
        8  0.0045 libavahi-common.so.3.5.1
        8  0.0045 libavahi-core.so.6.0.1
        3  0.0017 tr
        2  0.0011 libm-2.11.1.so
        2  0.0011 libpam.so.0.82.2
        2  0.0011 libpthread-2.11.1.so
        2  0.0011 apt-get
	  L2_ACCESS:10000|
	  samples|      %|
	------------------
	        1 50.0000 apt-get
	        1 50.0000 [vectors] (tgid:4505 range:0xffff0000-0xffff1000)
        1 5.6e-04 dash
        1 5.6e-04 grep
        1 5.6e-04 libcrypto.so.0.9.8
        1 5.6e-04 libnss_compat-2.11.1.so
        1 5.6e-04 ophelp
        1 5.6e-04 sudo
	  L2_ACCESS:10000|
	  samples|      %|
	------------------
	        1 100.000 [vectors] (tgid:6396 range:0xffff0000-0xffff1000)
        1 5.6e-04 LC_CTYPE
        1 5.6e-04 avahi-daemon
	  L2_ACCESS:10000|
	  samples|      %|
	------------------
	        1 100.000 [vectors] (tgid:3356 range:0xffff0000-0xffff1000)
        1 5.6e-04 ntpd
        1 5.6e-04 rsyslogd
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L2_ACCESS events (Any access to L2 cache) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        image name               symbol name
73672    41.5888  seti_boinc               top_sum2(float**, PoTPlan*)
39910    22.5297  seti_boinc               top_sum3(float**, PoTPlan*)
30442    17.1849  seti_boinc               top_sum4(float**, PoTPlan*)
24546    13.8565  seti_boinc               top_sum5(float**, PoTPlan*)
1973      1.1138  seti_boinc               sw_sum2_t31(float**, PoTPlan*)
1837      1.0370  seti_boinc               t_funct(int, int, int)
1557      0.8789  seti_boinc               find_pulse(float const*, int, float, int, int)
296       0.1671  seti_boinc               memset
249       0.1406  seti_boinc               analysis_config::analysis_config()
197       0.1112  seti_boinc               analyze_pot(float*, int, ChirpFftPair_t&)
181       0.1022  seti_boinc               malloc
149       0.0841  seti_boinc               _int_malloc
138       0.0779  seti_boinc               __ieee754_log
136       0.0768  seti_boinc               ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
121       0.0683  seti_boinc               workunit_grp::workunit_grp()
104       0.0587  seti_boinc               tape::tape()
103       0.0581  seti_boinc               GetFixedPoT(float*, int, int, float*, int, int)
98        0.0553  seti_boinc               splitter_config::splitter_config()
92        0.0519  seti_boinc               n1_16
87        0.0491  [vectors] (tgid:4827 range:0xffff0000-0xffff1000) [vectors] (tgid:4827 range:0xffff0000-0xffff1000)
87        0.0491  seti_boinc               malloc_consolidate
85        0.0480  seti_boinc               FindSpikes(float*, int, int, SETI_WU_INFO&)
85        0.0480  seti_boinc               time_to_ra_dec(double, double*, double*)
84        0.0474  seti_boinc               subband_description_t::subband_description_t()
74        0.0418  seti_boinc               pulse::pulse()
59        0.0333  seti_boinc               _int_free
59        0.0333  seti_boinc               operator new(unsigned int)
53        0.0299  seti_boinc               data_description_t::data_description_t()
50        0.0282  seti_boinc               __exp1
50        0.0282  seti_boinc               recorder_config::recorder_config()
44        0.0248  seti_boinc               result::result()
43        0.0243  seti_boinc               v_GetPowerSpectrum(float (*) [2], float*, int)
36        0.0203  seti_boinc               calc_detection_freq(double, double, double)
35        0.0198  seti_boinc               workunit_header::workunit_header()
33        0.0186  seti_boinc               cnvt_bin_hz(int, int)
30        0.0169  seti_boinc               __ieee754_pow
29        0.0164  seti_boinc               spike::spike()
25        0.0141  seti_boinc               PULSE_INFO::PULSE_INFO()
24        0.0135  seti_boinc               free
24        0.0135  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
23        0.0130  seti_boinc               receiver_config::receiver_config()
21        0.0119  seti_boinc               find_triplets(float const*, int, float, int, int)
17        0.0096  seti_boinc               floorf
17        0.0096  seti_boinc               log10l
16        0.0090  seti_boinc               T.9826
16        0.0090  seti_boinc               boinc_fraction_done
13        0.0073  seti_boinc               seti_analyze(ANALYSIS_STATE&)
11        0.0062  seti_boinc               calloc_a(unsigned int, unsigned int, unsigned int)
11        0.0062  seti_boinc               operator delete(void*)
10        0.0056  seti_boinc               __divsi3
10        0.0056  seti_boinc               logl
7         0.0040  seti_boinc               fftwf_execute_dft
6         0.0034  seti_boinc               SPIKE_INFO::SPIKE_INFO()
6         0.0034  seti_boinc               __aeabi_read_tp
5         0.0028  seti_boinc               PULSE_INFO::~PULSE_INFO()
5         0.0028  seti_boinc               T.9822
4         0.0023  seti_boinc               T.9827
4         0.0023  seti_boinc               memcpy
4         0.0023  seti_boinc               nanosleep
4         0.0023  seti_boinc               timer_handler()
3         0.0017  seti_boinc               SpikeProgressUnits(int)
3         0.0017  seti_boinc               T.9831
3         0.0017  seti_boinc               __default_sa_restorer_v2
3         0.0017  seti_boinc               __libc_disable_asynccancel
3         0.0017  seti_boinc               fraction_done(double, double)
3         0.0017  seti_boinc               powl
3         0.0017  seti_boinc               worker_signal_handler(int)
2         0.0011  seti_boinc               apply
2         0.0011  seti_boinc               fftwf_malloc
1        5.6e-04  seti_boinc               SPIKE_INFO::~SPIKE_INFO()
1        5.6e-04  seti_boinc               __ieee754_fmod
1        5.6e-04  seti_boinc               boinc_sleep(double)
1        5.6e-04  seti_boinc               fftwf_free
1        5.6e-04  seti_boinc               fftwf_kernel_malloc
1        5.6e-04  seti_boinc               fmodl
1        5.6e-04  seti_boinc               free_a(void*)
1        5.6e-04  seti_boinc               invert_lcgf(float, float, float)
1        5.6e-04  seti_boinc               isnanl
1        5.6e-04  seti_boinc               malloc_a(unsigned int, unsigned int)
1        5.6e-04  seti_boinc               std::ostream& std::ostream::_M_insert<long>(long)
1        5.6e-04  seti_boinc               usleep
 
 
Tue Aug 30 04:21:26 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L2_CACH_MISS events (Any cacheable miss in L2 cache) with a unit mask of 0x00 (No unit mask) count 10000
L2_CACH_MISS:1...|
  samples|      %|
------------------
     3298 73.2563 seti_boinc
	L2_CACH_MISS:1...|
	  samples|      %|
	------------------
	     3255 98.6962 seti_boinc
	       43  1.3038 [vectors] (tgid:4827 range:0xffff0000-0xffff1000)
      606 13.4607 libc-2.11.1.so
      148  3.2874 ld-2.11.1.so
      111  2.4656 python2.6
       85  1.8880 libz.so.1.2.3.3
       81  1.7992 dpkg-query
       72  1.5993 mandb
	L2_CACH_MISS:1...|
	  samples|      %|
	------------------
	       70 97.2222 mandb
	        2  2.7778 [vectors] (tgid:7728 range:0xffff0000-0xffff1000)
       36  0.7996 bash
       27  0.5997 updatedb.mlocate
       13  0.2888 libgdbm.so.3.0.0
        2  0.0444 dash
        2  0.0444 ld.so.cache
        2  0.0444 libnsl-2.11.1.so
        2  0.0444 libnss_nis-2.11.1.so
        2  0.0444 oprofiled
        2  0.0444 libavahi-core.so.6.0.1
        2  0.0444 ntpd
        1  0.0222 libgcc_s.so.1
        1  0.0222 libnss_compat-2.11.1.so
        1  0.0222 cmp
        1  0.0222 gawk
        1  0.0222 ISO8859-1.so
        1  0.0222 ISO8859-10.so
        1  0.0222 ISO8859-16.so
        1  0.0222 ISO8859-2.so
        1  0.0222 ISO8859-5.so
        1  0.0222 KOI8-R.so
        1  0.0222 libavahi-common.so.3.5.1
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L2_CACH_MISS events (Any cacheable miss in L2 cache) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        image name               symbol name
549      16.6465  seti_boinc               memset
502      15.2213  seti_boinc               analyze_pot(float*, int, ChirpFftPair_t&)
288       8.7326  seti_boinc               top_sum2(float**, PoTPlan*)
205       6.2159  seti_boinc               GetFixedPoT(float*, int, int, float*, int, int)
147       4.4572  seti_boinc               analysis_config::analysis_config()
139       4.2147  seti_boinc               top_sum3(float**, PoTPlan*)
111       3.3657  seti_boinc               splitter_config::splitter_config()
97        2.9412  seti_boinc               pulse::pulse()
94        2.8502  seti_boinc               top_sum4(float**, PoTPlan*)
89        2.6986  seti_boinc               workunit_grp::workunit_grp()
87        2.6380  seti_boinc               data_description_t::data_description_t()
86        2.6076  seti_boinc               subband_description_t::subband_description_t()
73        2.2135  seti_boinc               tape::tape()
73        2.2135  seti_boinc               top_sum5(float**, PoTPlan*)
71        2.1528  seti_boinc               result::result()
53        1.6070  seti_boinc               operator new(unsigned int)
47        1.4251  seti_boinc               workunit_header::workunit_header()
43        1.3038  [vectors] (tgid:4827 range:0xffff0000-0xffff1000) [vectors] (tgid:4827 range:0xffff0000-0xffff1000)
41        1.2432  seti_boinc               malloc
37        1.1219  seti_boinc               v_GetPowerSpectrum(float (*) [2], float*, int)
34        1.0309  seti_boinc               t_funct(int, int, int)
33        1.0006  seti_boinc               ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
30        0.9096  seti_boinc               _int_malloc
29        0.8793  seti_boinc               sw_sum2_t31(float**, PoTPlan*)
27        0.8187  seti_boinc               recorder_config::recorder_config()
24        0.7277  seti_boinc               find_pulse(float const*, int, float, int, int)
23        0.6974  seti_boinc               FindSpikes(float*, int, int, SETI_WU_INFO&)
19        0.5761  seti_boinc               receiver_config::receiver_config()
18        0.5458  seti_boinc               n1_64
17        0.5155  seti_boinc               find_triplets(float const*, int, float, int, int)
17        0.5155  seti_boinc               n1_32
16        0.4851  seti_boinc               T.9826
15        0.4548  seti_boinc               spike::spike()
12        0.3639  seti_boinc               T.9822
12        0.3639  seti_boinc               malloc_consolidate
12        0.3639  seti_boinc               n1_16
11        0.3335  seti_boinc               time_to_ra_dec(double, double*, double*)
10        0.3032  seti_boinc               _int_free
9         0.2729  seti_boinc               T.9827
9         0.2729  seti_boinc               __divsi3
9         0.2729  seti_boinc               __ieee754_log
9         0.2729  seti_boinc               cnvt_bin_hz(int, int)
5         0.1516  seti_boinc               SPIKE_INFO::SPIKE_INFO()
5         0.1516  seti_boinc               fftwf_kernel_malloc
5         0.1516  seti_boinc               floorf
4         0.1213  seti_boinc               PULSE_INFO::PULSE_INFO()
4         0.1213  seti_boinc               __ieee754_pow
3         0.0910  seti_boinc               PULSE_INFO::~PULSE_INFO()
3         0.0910  seti_boinc               T.9831
3         0.0910  seti_boinc               __aeabi_read_tp
3         0.0910  seti_boinc               __exp1
3         0.0910  seti_boinc               __libc_disable_asynccancel
3         0.0910  seti_boinc               free
3         0.0910  seti_boinc               nanosleep
3         0.0910  seti_boinc               operator delete(void*)
3         0.0910  seti_boinc               timer_handler()
2         0.0606  seti_boinc               __ieee754_fmod
2         0.0606  seti_boinc               calloc_a(unsigned int, unsigned int, unsigned int)
2         0.0606  seti_boinc               fftwf_malloc
2         0.0606  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
2         0.0606  seti_boinc               worker_signal_handler(int)
1         0.0303  seti_boinc               GaussFit(float*, int, int)
1         0.0303  seti_boinc               ____libc_disable_asynccancel_veneer
1         0.0303  seti_boinc               ____libc_enable_asynccancel_veneer
1         0.0303  seti_boinc               __default_sa_restorer_v2
1         0.0303  seti_boinc               boinc_fraction_done
1         0.0303  seti_boinc               calc_detection_freq(double, double, double)
1         0.0303  seti_boinc               fmodl
1         0.0303  seti_boinc               fraction_done(double, double)
1         0.0303  seti_boinc               memcpy
1         0.0303  seti_boinc               seti_analyze(ANALYSIS_STATE&)
1         0.0303  seti_boinc               timer_thread(void*)
 
 
Tue Aug 30 04:25:25 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L1_DATA_MISS events (L1 data cache miss as a result of the hashing algorithm) with a unit mask of 0x00 (No unit mask) count 10000
L1_DATA_MISS:1...|
  samples|      %|
------------------
    12859 99.0678 seti_boinc
       46  0.3544 libc-2.11.1.so
       41  0.3159 ld-2.11.1.so
       14  0.1079 mandb
        9  0.0693 libz.so.1.2.3.3
        6  0.0462 libnss_compat-2.11.1.so
        3  0.0231 bash
        2  0.0154 libgdbm.so.3.0.0
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L1_DATA_MISS events (L1 data cache miss as a result of the hashing algorithm) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
10621    82.5958  sinl
450       3.4995  sw_sum2_t31(float**, PoTPlan*)
393       3.0562  t_funct(int, int, int)
391       3.0407  cosl
272       2.1153  find_pulse(float const*, int, float, int, int)
230       1.7886  top_sum2(float**, PoTPlan*)
105       0.8165  top_sum3(float**, PoTPlan*)
38        0.2955  fftwf_cpy2d_pair
35        0.2722  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
32        0.2489  top_sum4(float**, PoTPlan*)
31        0.2411  t1_16
26        0.2022  analyze_pot(float*, int, ChirpFftPair_t&)
26        0.2022  v_GetPowerSpectrum(float (*) [2], float*, int)
24        0.1866  n1_32
21        0.1633  sw_sum4_t31(float**, PoTPlan*)
21        0.1633  top_sum5(float**, PoTPlan*)
20        0.1555  __ieee754_pow
14        0.1089  n1_64
13        0.1011  GetFixedPoT(float*, int, int, float*, int, int)
13        0.1011  sw_sum5_t31(float**, PoTPlan*)
11        0.0855  rotate_sqrtn_table
9         0.0700  _int_malloc
8         0.0622  cnvt_bin_hz(int, int)
7         0.0544  apply
7         0.0544  f_GetPeak(float*, int, int, float, float, float*)
7         0.0544  f_GetTrueMean(float*, int, float, int, int)
6         0.0467  time_to_ra_dec(double, double*, double*)
5         0.0389  FindSpikes(float*, int, int, SETI_WU_INFO&)
3         0.0233  csloww1
2         0.0156  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
2         0.0156  GAUSS_INFO::~GAUSS_INFO()
2         0.0156  boinc_fraction_done
2         0.0156  f_GetChiSq(float*, int, int, float, float, float*, float*)
2         0.0156  free
2         0.0156  t1_32
1         0.0078  PULSE_INFO::~PULSE_INFO()
1         0.0078  __divsi3
1         0.0078  __exp1
1         0.0078  __ieee754_log
1         0.0078  find_triplets(float const*, int, float, int, int)
1         0.0078  floor
1         0.0078  subband_description_t::subband_description_t()
1         0.0078  workunit_header::workunit_header()
 
 
Tue Aug 30 04:29:24 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L1_INST events (Any L1 instruction cache access, excluding CP15 cache accesses) with a unit mask of 0x00 (No unit mask) count 10000
    L1_INST:10000|
  samples|      %|
------------------
    85689 82.0517 seti_boinc
     7178  6.8733 libc-2.11.1.so
     3664  3.5085 mandb
	    L1_INST:10000|
	  samples|      %|
	------------------
	     3630 99.0721 mandb
	       34  0.9279 [vectors] (tgid:7728 range:0xffff0000-0xffff1000)
     1962  1.8787 ld-2.11.1.so
     1900  1.8193 libz.so.1.2.3.3
     1711  1.6384 bash
	    L1_INST:10000|
	  samples|      %|
	------------------
	     1710 99.9416 bash
	        1  0.0584 [vectors] (tgid:4728 range:0xffff0000-0xffff1000)
     1541  1.4756 oprofiled
	    L1_INST:10000|
	  samples|      %|
	------------------
	     1524 98.8968 oprofiled
	       17  1.1032 [vectors] (tgid:17625 range:0xffff0000-0xffff1000)
      338  0.3237 libavahi-common.so.3.5.1
      198  0.1896 libgdbm.so.3.0.0
       67  0.0642 libavahi-core.so.6.0.1
       59  0.0565 avahi-daemon
	    L1_INST:10000|
	  samples|      %|
	------------------
	       59 100.000 [vectors] (tgid:3356 range:0xffff0000-0xffff1000)
       19  0.0182 libpam.so.0.82.2
       18  0.0172 tr
       15  0.0144 dash
       10  0.0096 gawk
       10  0.0096 sudo
        9  0.0086 libnss_compat-2.11.1.so
        9  0.0086 rsyslogd
	    L1_INST:10000|
	  samples|      %|
	------------------
	        7 77.7778 rsyslogd
	        2 22.2222 [vectors] (tgid:3135 range:0xffff0000-0xffff1000)
        8  0.0077 grep
        7  0.0067 libpthread-2.11.1.so
        4  0.0038 libgcc_s.so.1
        4  0.0038 ntpd
        2  0.0019 libnsl-2.11.1.so
        1 9.6e-04 ls
        1 9.6e-04 mkdir
        1 9.6e-04 libcrypto.so.0.9.8
        1 9.6e-04 libdl-2.11.1.so
        1 9.6e-04 libncurses.so.5.7
        1 9.6e-04 libnss_files-2.11.1.so
        1 9.6e-04 libnss_nis-2.11.1.so
        1 9.6e-04 libselinux.so.1
        1 9.6e-04 pam_deny.so
        1 9.6e-04 gconv-modules.cache
        1 9.6e-04 LC_MEASUREMENT
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L1_INST events (Any L1 instruction cache access, excluding CP15 cache accesses) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
17363    20.2628  cosl
15775    18.4096  sinl
8922     10.4121  n1_32
7485      8.7351  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
5918      6.9064  rotate_sqrtn_table
5416      6.3205  n1_16
4571      5.3344  t1_16
3843      4.4848  q1_4
3050      3.5594  t1_4
2674      3.1206  FindSpikes(float*, int, int, SETI_WU_INFO&)
2646      3.0879  floor
2103      2.4542  fftwf_cpy2d_pair
2052      2.3947  apply
1392      1.6245  t1_8
1295      1.5113  v_GetPowerSpectrum(float (*) [2], float*, int)
531       0.6197  sincos
265       0.3093  csloww1
63        0.0735  __dubsin
62        0.0724  apply
60        0.0700  __dubcos
51        0.0595  apply
41        0.0478  apply_dit
25        0.0292  apply_dif
20        0.0233  apply
19        0.0222  csloww
14        0.0163  apply
6         0.0070  __ieee754_log
5         0.0058  fftwf_cpy2d_pair_co
3         0.0035  __docos
3         0.0035  malloc
2         0.0023  __ieee754_pow
2         0.0023  isnanl
2         0.0023  worker_signal_handler(int)
1         0.0012  _int_malloc
1         0.0012  boinc_sleep(double)
1         0.0012  dtime()
1         0.0012  fftwf_malloc_plain
1         0.0012  fmodl
1         0.0012  free
1         0.0012  gettimeofday
1         0.0012  nanosleep
1         0.0012  receiver_config::receiver_config()
1         0.0012  timer_handler()
 
 
Tue Aug 30 04:33:23 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L1_DATA_MISS events (L1 data cache miss as a result of the hashing algorithm) with a unit mask of 0x00 (No unit mask) count 10000
L1_DATA_MISS:1...|
  samples|      %|
------------------
    15281 99.1822 seti_boinc
       40  0.2596 ld-2.11.1.so
       39  0.2531 mandb
       34  0.2207 libc-2.11.1.so
        8  0.0519 libz.so.1.2.3.3
        3  0.0195 libgdbm.so.3.0.0
        2  0.0130 bash
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L1_DATA_MISS events (L1 data cache miss as a result of the hashing algorithm) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
14357    93.9533  sinl
518       3.3898  cosl
52        0.3403  fftwf_cpy2d_pair
47        0.3076  n1_32
38        0.2487  t1_16
36        0.2356  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
34        0.2225  n1_64
34        0.2225  v_GetPowerSpectrum(float (*) [2], float*, int)
25        0.1636  analyze_pot(float*, int, ChirpFftPair_t&)
18        0.1178  GetFixedPoT(float*, int, int, float*, int, int)
13        0.0851  apply
12        0.0785  time_to_ra_dec(double, double*, double*)
11        0.0720  __ieee754_pow
10        0.0654  FindSpikes(float*, int, int, SETI_WU_INFO&)
10        0.0654  f_GetTrueMean(float*, int, float, int, int)
9         0.0589  f_GetPeak(float*, int, int, float, float, float*)
9         0.0589  rotate_sqrtn_table
6         0.0393  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
6         0.0393  cnvt_bin_hz(int, int)
5         0.0327  __ieee754_log
4         0.0262  t1_64
3         0.0196  __dubsin
3         0.0196  _int_malloc
3         0.0196  f_GetChiSq(float*, int, int, float, float, float*, float*)
3         0.0196  floor
2         0.0131  apply_dit
2         0.0131  csloww1
2         0.0131  q1_4
2         0.0131  t1_8
1         0.0065  GAUSS_INFO::~GAUSS_INFO()
1         0.0065  SPIKE_INFO::~SPIKE_INFO()
1         0.0065  __exp1
1         0.0065  apply
1         0.0065  csloww
1         0.0065  find_pulse(float const*, int, float, int, int)
1         0.0065  free
 
 
Tue Aug 30 04:37:21 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted PC_BRANCH_FAILED events (Branch prediction misprediction) with a unit mask of 0x00 (No unit mask) count 10000
PC_BRANCH_FAIL...|
  samples|      %|
------------------
     4111 66.9871 seti_boinc
      901 14.6814 libz.so.1.2.3.3
      633 10.3145 ld-2.11.1.so
      310  5.0513 libc-2.11.1.so
      104  1.6946 mandb
       46  0.7496 bash
       20  0.3259 libgdbm.so.3.0.0
        5  0.0815 libavahi-common.so.3.5.1
        3  0.0489 gawk
        2  0.0326 ophelp
        1  0.0163 grep
        1  0.0163 libdbus-1.so.3.4.0
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted PC_BRANCH_FAILED events (Branch prediction misprediction) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
1556     37.8497  cosl
1211     29.4576  sinl
527      12.8193  f_GetTrueMean(float*, int, float, int, int)
132       3.2109  find_triplets(float const*, int, float, int, int)
85        2.0676  GaussFit(float*, int, int)
79        1.9217  __ieee754_log
78        1.8973  _int_malloc
68        1.6541  analyze_pot(float*, int, ChirpFftPair_t&)
46        1.1189  find_pulse(float const*, int, float, int, int)
37        0.9000  float_to_uchar(float*, unsigned char*, long, float)
37        0.9000  lcgf(double, double)
26        0.6324  apply
21        0.5108  sw_sum4_t31(float**, PoTPlan*)
20        0.4865  apply_dit
19        0.4622  GetFixedPoT(float*, int, int, float*, int, int)
17        0.4135  malloc_consolidate
15        0.3649  __divsi3
14        0.3405  sw_sum3_t31(float**, PoTPlan*)
10        0.2432  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
8         0.1946  __udivsi3
8         0.1946  _int_free
8         0.1946  apply_dif
8         0.1946  f_GetChiSq(float*, int, int, float, float, float*, float*)
8         0.1946  logl
8         0.1946  time_to_ra_dec(double, double*, double*)
6         0.1459  apply
5         0.1216  apply
5         0.1216  checkpoint(unsigned char)
5         0.1216  csloww1
4         0.0973  __dubsin
4         0.0973  apply
4         0.0973  apply
3         0.0730  FindSpikes(float*, int, int, SETI_WU_INFO&)
3         0.0730  fftwf_cpy2d_pair
3         0.0730  n1_32
3         0.0730  t1_4
2         0.0486  cnvt_bin_hz(int, int)
2         0.0486  malloc
2         0.0486  q1_4
2         0.0486  t1_16
1         0.0243  __dubcos
1         0.0243  __mul
1         0.0243  dtime()
1         0.0243  fftwf_cpy2d_pair_co
1         0.0243  fftwf_execute_dft
1         0.0243  floor
1         0.0243  free
1         0.0243  memcpy
1         0.0243  n1_16
1         0.0243  n1_64
1         0.0243  rotate_sqrtn_table
1         0.0243  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
 
 
Tue Aug 30 04:41:18 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted PC_BRANCH_TAKEN events (Any predicted branch that is taken) with a unit mask of 0x00 (No unit mask) count 10000
PC_BRANCH_TAKE...|
  samples|      %|
------------------
   184783 97.0382 seti_boinc
	PC_BRANCH_TAKE...|
	  samples|      %|
	------------------
	   184559 99.8788 seti_boinc
	      224  0.1212 [vectors] (tgid:4827 range:0xffff0000-0xffff1000)
     3760  1.9746 libc-2.11.1.so
      764  0.4012 bash
	PC_BRANCH_TAKE...|
	  samples|      %|
	------------------
	      696 91.0995 bash
	       67  8.7696 [vectors] (tgid:4221 range:0xffff0000-0xffff1000)
	        1  0.1309 [vectors] (tgid:4728 range:0xffff0000-0xffff1000)
      703  0.3692 oprofiled
      314  0.1649 ld-2.11.1.so
       19  0.0100 libavahi-common.so.3.5.1
       17  0.0089 gawk
       17  0.0089 tr
       14  0.0074 ophelp
        7  0.0037 libpam.so.0.82.2
        6  0.0032 ntpd
        3  0.0016 dash
        3  0.0016 grep
        3  0.0016 sudo
	PC_BRANCH_TAKE...|
	  samples|      %|
	------------------
	        2 66.6667 sudo
	        1 33.3333 [vectors] (tgid:4221 range:0xffff0000-0xffff1000)
        3  0.0016 libavahi-core.so.6.0.1
        2  0.0011 libdl-2.11.1.so
        2  0.0011 libm-2.11.1.so
        1 5.3e-04 libpthread-2.11.1.so
        1 5.3e-04 pam_limits.so
        1 5.3e-04 LC_COLLATE
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted PC_BRANCH_TAKEN events (Any predicted branch that is taken) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        image name               symbol name
27575    14.9229  seti_boinc               v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
26122    14.1366  seti_boinc               cosl
25055    13.5591  seti_boinc               sinl
12813     6.9341  seti_boinc               FindSpikes(float*, int, int, SETI_WU_INFO&)
9678      5.2375  seti_boinc               rotate_sqrtn_table
9637      5.2153  seti_boinc               f_GetTrueMean(float*, int, float, int, int)
8245      4.4620  seti_boinc               sincos
6442      3.4863  seti_boinc               v_GetPowerSpectrum(float (*) [2], float*, int)
4951      2.6794  seti_boinc               f_GetPeak(float*, int, int, float, float, float*)
4871      2.6361  seti_boinc               GaussFit(float*, int, int)
4266      2.3087  seti_boinc               fftwf_cpy2d_pair
4256      2.3032  seti_boinc               find_triplets(float const*, int, float, int, int)
3971      2.1490  seti_boinc               floor
3204      1.7339  seti_boinc               apply
2759      1.4931  seti_boinc               sw_sum2_t31(float**, PoTPlan*)
2568      1.3897  seti_boinc               analyze_pot(float*, int, ChirpFftPair_t&)
2559      1.3849  seti_boinc               find_pulse(float const*, int, float, int, int)
2281      1.2344  seti_boinc               __ieee754_log
2126      1.1505  seti_boinc               GetFixedPoT(float*, int, int, float*, int, int)
2028      1.0975  seti_boinc               sw_sum3_t31(float**, PoTPlan*)
1627      0.8805  seti_boinc               powl
1450      0.7847  seti_boinc               f_GetChiSq(float*, int, int, float, float, float*, float*)
1398      0.7566  seti_boinc               sw_sum4_t31(float**, PoTPlan*)
1298      0.7024  seti_boinc               float_to_uchar(float*, unsigned char*, long, float)
1280      0.6927  seti_boinc               lcgf(double, double)
1074      0.5812  seti_boinc               t1_4
1038      0.5617  seti_boinc               __ieee754_pow
964       0.5217  seti_boinc               sw_sum5_t31(float**, PoTPlan*)
951       0.5147  seti_boinc               _int_malloc
722       0.3907  seti_boinc               logl
487       0.2636  seti_boinc               __exp1
468       0.2533  seti_boinc               n1_16
449       0.2430  seti_boinc               _int_free
406       0.2197  seti_boinc               t1_16
363       0.1964  seti_boinc               malloc
332       0.1797  seti_boinc               fraction_done(double, double)
331       0.1791  seti_boinc               free
284       0.1537  seti_boinc               q1_4
244       0.1320  seti_boinc               time_to_ra_dec(double, double*, double*)
237       0.1283  seti_boinc               TripletProgressUnits()
231       0.1250  seti_boinc               csloww1
224       0.1212  [vectors] (tgid:4827 range:0xffff0000-0xffff1000) [vectors] (tgid:4827 range:0xffff0000-0xffff1000)
224       0.1212  seti_boinc               isnanl
203       0.1099  seti_boinc               __divsi3
202       0.1093  seti_boinc               checkpoint(unsigned char)
202       0.1093  seti_boinc               n1_32
196       0.1061  seti_boinc               ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
183       0.0990  seti_boinc               PulseProgressUnits(double, int)
150       0.0812  seti_boinc               apply
121       0.0655  seti_boinc               cnvt_bin_hz(int, int)
115       0.0622  seti_boinc               malloc_consolidate
113       0.0612  seti_boinc               apply_dit
104       0.0563  seti_boinc               __udivsi3
99        0.0536  seti_boinc               t1_8
96        0.0520  seti_boinc               GAUSS_INFO::~GAUSS_INFO()
96        0.0520  seti_boinc               operator new(unsigned int)
94        0.0509  seti_boinc               apply
94        0.0509  seti_boinc               receiver_config::receiver_config()
84        0.0455  seti_boinc               analysis_config::analysis_config()
83        0.0449  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
76        0.0411  seti_boinc               operator delete(void*)
69        0.0373  seti_boinc               memset
65        0.0352  seti_boinc               boinc_time_to_checkpoint
64        0.0346  seti_boinc               T.9826
64        0.0346  seti_boinc               boinc_fraction_done
53        0.0287  seti_boinc               gaussian::gaussian()
50        0.0271  seti_boinc               apply
48        0.0260  seti_boinc               apply_dif
45        0.0244  seti_boinc               data_description_t::data_description_t()
37        0.0200  seti_boinc               workunit_grp::workunit_grp()
32        0.0173  seti_boinc               __dubcos
30        0.0162  seti_boinc               n1_64
30        0.0162  seti_boinc               recorder_config::recorder_config()
29        0.0157  seti_boinc               GAUSS_INFO::GAUSS_INFO()
29        0.0157  seti_boinc               finite
28        0.0152  seti_boinc               GaussianProgressUnits()
27        0.0146  seti_boinc               result::result()
26        0.0141  seti_boinc               apply
22        0.0119  seti_boinc               MFILE::MFILE()
22        0.0119  seti_boinc               MFILE::~MFILE()
20        0.0108  seti_boinc               T.9831
20        0.0108  seti_boinc               __dubsin
19        0.0103  seti_boinc               subband_description_t::subband_description_t()
16        0.0087  seti_boinc               T.9827
15        0.0081  seti_boinc               calc_detection_freq(double, double, double)
14        0.0076  seti_boinc               T.9822
14        0.0076  seti_boinc               splitter_config::splitter_config()
13        0.0070  seti_boinc               t1_32
13        0.0070  seti_boinc               tape::tape()
11        0.0060  seti_boinc               csloww
11        0.0060  seti_boinc               memcpy
8         0.0043  seti_boinc               __mul
6         0.0032  seti_boinc               fftwf_cpy2d_pair_co
5         0.0027  seti_boinc               workunit_header::workunit_header()
4         0.0022  seti_boinc               __aeabi_read_tp
3         0.0016  seti_boinc               SpikeProgressUnits(int)
3         0.0016  seti_boinc               log10l
3         0.0016  seti_boinc               memmove
2         0.0011  seti_boinc               ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
2         0.0011  seti_boinc               seti_analyze(ANALYSIS_STATE&)
2         0.0011  seti_boinc               spike::spike()
2         0.0011  seti_boinc               t1_64
1        5.4e-04  seti_boinc               SPIKE_INFO::~SPIKE_INFO()
1        5.4e-04  seti_boinc               _IO_default_xsputn
1        5.4e-04  seti_boinc               __docos
1        5.4e-04  seti_boinc               _wordcopy_fwd_aligned
1        5.4e-04  seti_boinc               fmodl
1        5.4e-04  seti_boinc               gettimeofday
1        5.4e-04  seti_boinc               std::basic_ostream<char, std::char_traits<char> >& std::__ostream_insert<char, std::char_traits<char> >(std::basic_ostream<char, std::char_traits<char> >&, char const*, int)
 
 
Tue Aug 30 04:45:15 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L1_NEON_DATA events (NEON data access that hits L1 cache) with a unit mask of 0x00 (No unit mask) count 10000
L1_NEON_DATA:1...|
  samples|      %|
------------------
   716073 100.000 seti_boinc
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L1_NEON_DATA events (NEON data access that hits L1 cache) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
123063   17.1858  n1_32
100236   13.9980  t1_16
82183    11.4769  cosl
76583    10.6949  sinl
57151     7.9812  n1_64
40357     5.6359  n1_16
34366     4.7992  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
26250     3.6658  q1_4
20864     2.9137  rotate_sqrtn_table
15342     2.1425  t1_4
14452     2.0182  f_GetPeak(float*, int, int, float, float, float*)
12475     1.7421  FindSpikes(float*, int, int, SETI_WU_INFO&)
12467     1.7410  v_GetPowerSpectrum(float (*) [2], float*, int)
12324     1.7211  f_GetTrueMean(float*, int, float, int, int)
10043     1.4025  sincos
9884      1.3803  t1_64
8783      1.2266  fftwf_cpy2d_pair
8092      1.1301  GaussFit(float*, int, int)
7854      1.0968  t1_32
6586      0.9197  __ieee754_log
4348      0.6072  apply
4131      0.5769  __ieee754_pow
3548      0.4955  floor
2881      0.4023  find_triplets(float const*, int, float, int, int)
2881      0.4023  t1_8
2339      0.3266  __exp1
2101      0.2934  analyze_pot(float*, int, ChirpFftPair_t&)
1759      0.2456  f_GetChiSq(float*, int, int, float, float, float*, float*)
1735      0.2423  GetFixedPoT(float*, int, int, float*, int, int)
1372      0.1916  logl
1177      0.1644  sw_sum3_t31(float**, PoTPlan*)
1096      0.1531  lcgf(double, double)
976       0.1363  csloww1
840       0.1173  float_to_uchar(float*, unsigned char*, long, float)
787       0.1099  sw_sum5_t31(float**, PoTPlan*)
753       0.1052  sw_sum4_t31(float**, PoTPlan*)
681       0.0951  find_pulse(float const*, int, float, int, int)
528       0.0737  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
421       0.0588  isnanl
373       0.0521  powl
297       0.0415  TripletProgressUnits()
240       0.0335  fraction_done(double, double)
216       0.0302  time_to_ra_dec(double, double*, double*)
200       0.0279  apply
165       0.0230  apply
138       0.0193  PulseProgressUnits(double, int)
120       0.0168  cnvt_bin_hz(int, int)
79        0.0110  calc_detection_freq(double, double, double)
76        0.0106  csloww
74        0.0103  __dubcos
65        0.0091  __dubsin
49        0.0068  apply_dit
46        0.0064  GaussianProgressUnits()
36        0.0050  GAUSS_INFO::GAUSS_INFO()
34        0.0047  checkpoint(unsigned char)
19        0.0027  __docos
18        0.0025  apply_dif
15        0.0021  fftwf_cpy2d_pair_co
14        0.0020  apply
11        0.0015  gaussian::gaussian()
11        0.0015  splitter_config::splitter_config()
10        0.0014  __udivsi3
10        0.0014  tape::tape()
10        0.0014  workunit_header::workunit_header()
8         0.0011  recorder_config::recorder_config()
7        9.8e-04  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
6        8.4e-04  __divsi3
4        5.6e-04  seti_analyze(ANALYSIS_STATE&)
3        4.2e-04  dtime()
3        4.2e-04  workunit_grp::workunit_grp()
2        2.8e-04  __ieee754_log10
2        2.8e-04  subband_description_t::subband_description_t()
1        1.4e-04  SpikeProgressUnits(int)
1        1.4e-04  __mpn_extract_double
1        1.4e-04  log10l
```