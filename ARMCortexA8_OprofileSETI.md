# SETI on Cortex-A8 #
```
#!/bin/bash
# iMX53 - ARM Cortex A8 Oprofile Script
SleepSeconds=180 #on real run
./seti_boinc --standalone &
sudo rm -r /var/lib/oprofile
sudo rm -r /root/.oprofile/daemonrc

# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=CPU_CYCLES:200000:0x0:0:1 --event=INSTR_EXECUTED:200000:0x0:0:1 --event=L2_ACCESS:200000:0x0:0:1 --event=L2_CACH_MISS:200000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt

# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=PC_BRANCH_MIS_PRED:200000:0x0:0:1 --event=PC_BRANCH_MIS_USED:200000:0x0:0:1 --event=PC_IMM_BRANCH:200000:0x0:0:1 --event=PC_BRANCH_EXECUTED:200000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt

# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=ITLB_MISS:200000:0x0:0:1 --event=DTLB_REFILL:200000:0x0:0:1 --event=CYCLES_INST_STALL:200000:0x0:0:1 --event=CYCLES_NEON_DATA_STALL:200000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
```

## oprofile script - 180s ##
```
Tue Oct  4 02:43:57 CST 2011
CPU: ARM Cortex-A8, speed 1e+06 MHz (estimated)
Counted CPU_CYCLES events (Number of CPU cycles) with a unit mask of 0x00 (No unit mask) count 200000
Counted INSTR_EXECUTED events (All executed instructions) with a unit mask of 0x00 (No unit mask) count 200000
Counted L2_ACCESS events (Any access to L2 cache) with a unit mask of 0x00 (No unit mask) count 200000
Counted L2_CACH_MISS events (Any cacheable miss in L2 cache) with a unit mask of 0x00 (No unit mask) count 200000
CPU_CYCLES:200000|INSTR_EXECUTED...| L2_ACCESS:200000|L2_CACH_MISS:2...|
  samples|      %|  samples|      %|  samples|      %|  samples|      %|
------------------------------------------------------------------------
   855518 99.4112    204338 98.7546      8632 99.5962       116 92.8000 seti_boinc
	CPU_CYCLES:200000|INSTR_EXECUTED...| L2_ACCESS:200000|L2_CACH_MISS:2...|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	   855317 99.9765    204183 99.9241      8629 99.9652       113 97.4138 seti_boinc
	      201  0.0235       155  0.0759         3  0.0348         3  2.5862 [vectors] (tgid:12078 range:0xffff0000-0xffff1000)
     1794  0.2085      1227  0.5930         9  0.1038         3  2.4000 oprofiled
	CPU_CYCLES:200000|INSTR_EXECUTED...| L2_ACCESS:200000|L2_CACH_MISS:2...|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	     1793 99.9443      1226 99.9185         9 100.000         3 100.000 oprofiled
	        1  0.0557         1  0.0815         0       0         0       0 [vectors] (tgid:12707 range:0xffff0000-0xffff1000)
     1730  0.2010       971  0.4693         6  0.0692         3  2.4000 libc-2.11.1.so
      845  0.0982       184  0.0889        11  0.1269         3  2.4000 ld-2.11.1.so
      198  0.0230        60  0.0290         2  0.0231         0       0 dash
	CPU_CYCLES:200000|INSTR_EXECUTED...| L2_ACCESS:200000|L2_CACH_MISS:2...|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	      194 97.9798        59 98.3333         2 100.000         0       0 dash
	        4  2.0202         1  1.6667         0       0         0       0 [vectors] (tgid:12866 range:0xffff0000-0xffff1000)
      124  0.0144        18  0.0087         2  0.0231         0       0 gawk
       95  0.0110        51  0.0246         1  0.0115         0       0 libavahi-common.so.3.5.1
       67  0.0078        14  0.0068         2  0.0231         0       0 libavahi-core.so.6.0.1
       66  0.0077         3  0.0014         0       0         0       0 libapt-pkg-libc6.10-6.so.4.8.0
       57  0.0066        35  0.0169         0       0         0       0 ophelp
       10  0.0012         4  0.0019         0       0         0       0 avahi-daemon
	CPU_CYCLES:200000|INSTR_EXECUTED...| L2_ACCESS:200000|L2_CACH_MISS:2...|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	       10 100.000         4 100.000         0       0         0       0 [vectors] (tgid:3312 range:0xffff0000-0xffff1000)
       10  0.0012         0       0         0       0         0       0 ntpd
        9  0.0010         0       0         0       0         0       0 libpthread-2.11.1.so
        8 9.3e-04         2 9.7e-04         0       0         0       0 grep
        5 5.8e-04         1 4.8e-04         0       0         0       0 libm-2.11.1.so
        5 5.8e-04         0       0         0       0         0       0 libpopt.so.0.0.0
        4 4.6e-04         0       0         0       0         0       0 bash
        4 4.6e-04         1 4.8e-04         0       0         0       0 apt-get
	CPU_CYCLES:200000|INSTR_EXECUTED...| L2_ACCESS:200000|L2_CACH_MISS:2...|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	        2 50.0000         0       0         0       0         0       0 apt-get
	        2 50.0000         1 100.000         0       0         0       0 [vectors] (tgid:11952 range:0xffff0000-0xffff1000)
        4 4.6e-04         0       0         0       0         0       0 sudo
        4 4.6e-04         0       0         0       0         0       0 rsyslogd
        3 3.5e-04         0       0         0       0         0       0 ls
        3 3.5e-04         1 4.8e-04         0       0         0       0 libcrypto.so.0.9.8
        3 3.5e-04         0       0         0       0         0       0 libgcc_s.so.1
        3 3.5e-04         1 4.8e-04         0       0         0       0 libpam.so.0.82.2
        3 3.5e-04         1 4.8e-04         0       0         0       0 LC_CTYPE
        2 2.3e-04         0       0         0       0         0       0 seq
        2 2.3e-04         0       0         0       0         0       0 gconv-modules.cache
        1 1.2e-04         0       0         1  0.0115         0       0 cat
        1 1.2e-04         0       0         0       0         0       0 ld.so.cache
        1 1.2e-04         0       0         0       0         0       0 libdl-2.11.1.so
        1 1.2e-04         1 4.8e-04         0       0         0       0 libnss_compat-2.11.1.so
        1 1.2e-04         0       0         0       0         0       0 libselinux.so.1
        1 1.2e-04         0       0         0       0         0       0 pam_limits.so
        1 1.2e-04         0       0         0       0         0       0 tr
        1 1.2e-04         0       0         0       0         0       0 ftp
        1 1.2e-04         1 4.8e-04         0       0         0       0 imklog.so
        0       0         0       0         1  0.0115         0       0 librt-2.11.1.so
        0       0         1 4.8e-04         0       0         0       0 libstdc++.so.6.0.13
 
CPU: ARM Cortex-A8, speed 1e+06 MHz (estimated)
Counted CPU_CYCLES events (Number of CPU cycles) with a unit mask of 0x00 (No unit mask) count 200000
Counted INSTR_EXECUTED events (All executed instructions) with a unit mask of 0x00 (No unit mask) count 200000
Counted L2_ACCESS events (Any access to L2 cache) with a unit mask of 0x00 (No unit mask) count 200000
Counted L2_CACH_MISS events (Any cacheable miss in L2 cache) with a unit mask of 0x00 (No unit mask) count 200000
samples  %        samples  %        samples  %        samples  %        image name               symbol name
317032   37.0573  74761    36.5869  3455     40.0255  8         6.8966  seti_boinc               top_sum2(float**, PoTPlan*)
180654   21.1163  42192    20.6481  1912     22.1501  3         2.5862  seti_boinc               top_sum3(float**, PoTPlan*)
162413   18.9842  35900    17.5689  1478     17.1223  2         1.7241  seti_boinc               top_sum4(float**, PoTPlan*)
139173   16.2677  30676    15.0124  1231     14.2609  1         0.8621  seti_boinc               top_sum5(float**, PoTPlan*)
5692      0.6653  7450      3.6459  27        0.3128  2         1.7241  seti_boinc               strchr
4829      0.5645  1050      0.5139  63        0.7298  0              0  seti_boinc               sw_sum2_t31(float**, PoTPlan*)
4230      0.4944  889       0.4351  14        0.1622  0              0  seti_boinc               __ieee754_log
3264      0.3815  433       0.2119  26        0.3012  10        8.6207  seti_boinc               n1_64
2982      0.3486  826       0.4042  46        0.5329  0              0  seti_boinc               find_pulse(float const*, int, float, int, int)
2943      0.3440  409       0.2002  23        0.2665  0              0  seti_boinc               t1_32
2870      0.3355  2568      1.2567  24        0.2780  0              0  seti_boinc               Laligned
2740      0.3203  1141      0.5584  84        0.9731  2         1.7241  seti_boinc               t_funct(int, int, int)
1949      0.2278  292       0.1429  11        0.1274  0              0  seti_boinc               v_BaseLineSmooth(float (*) [2], int, int, int)
1666      0.1947  249       0.1219  6         0.0695  1         0.8621  seti_boinc               t1_16
1661      0.1942  307       0.1502  8         0.0927  0              0  seti_boinc               n1_32
1384      0.1618  254       0.1243  5         0.0579  0              0  seti_boinc               __ieee754_pow
1290      0.1508  193       0.0945  9         0.1043  0              0  seti_boinc               q1_8
1043      0.1219  118       0.0577  2         0.0232  0              0  seti_boinc               lcgf(double, double)
1009      0.1179  126       0.0617  7         0.0811  0              0  seti_boinc               __exp1
975       0.1140  135       0.0661  13        0.1506  1         0.8621  seti_boinc               t1_8
935       0.1093  127       0.0622  4         0.0463  2         1.7241  seti_boinc               q1_4
932       0.1089  102       0.0499  4         0.0463  1         0.8621  seti_boinc               t1_4
900       0.1052  130       0.0636  11        0.1274  4         3.4483  seti_boinc               v_GetPowerSpectrum(float (*) [2], float*, int)
853       0.0997  154       0.0754  8         0.0927  0              0  seti_boinc               n1_8
838       0.0980  236       0.1155  13        0.1506  1         0.8621  seti_boinc               FindSpikes(float*, int, int, SETI_WU_INFO&)
700       0.0818  43        0.0210  3         0.0348  2         1.7241  seti_boinc               GetFixedPoT(float*, int, int, float*, int, int)
683       0.0798  130       0.0636  6         0.0695  0              0  seti_boinc               ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
667       0.0780  40        0.0196  2         0.0232  0              0  seti_boinc               analyze_pot(float*, int, ChirpFftPair_t&)
631       0.0738  138       0.0675  6         0.0695  0              0  seti_boinc               time_to_ra_dec(double, double*, double*)
470       0.0549  32        0.0157  6         0.0695  8         6.8966  seti_boinc               memcpy
466       0.0545  239       0.1170  5         0.0579  0              0  seti_boinc               _int_malloc
453       0.0530  133       0.0651  3         0.0348  1         0.8621  seti_boinc               GenChirpFftPairs(ChirpFftPair_t**, double*)
451       0.0527  439       0.2148  2         0.0232  0              0  seti_boinc               __divsi3
399       0.0466  154       0.0754  10        0.1158  3         2.5862  seti_boinc               malloc
336       0.0393  90        0.0440  2         0.0232  0              0  seti_boinc               logl
286       0.0334  53        0.0259  16        0.1854  11        9.4828  seti_boinc               analysis_config::analysis_config()
270       0.0316  53        0.0259  1         0.0116  0              0  seti_boinc               SpikeProgressUnits(int)
263       0.0307  209       0.1023  1         0.0116  0              0  seti_boinc               _int_free
263       0.0307  24        0.0117  2         0.0232  0              0  seti_boinc               calc_detection_freq(double, double, double)
257       0.0300  149       0.0729  0              0  0              0  seti_boinc               free
252       0.0295  75        0.0367  0              0  0              0  seti_boinc               find_triplets(float const*, int, float, int, int)
242       0.0283  37        0.0181  0              0  0              0  seti_boinc               seti_analyze(ANALYSIS_STATE&)
201       0.0235  155       0.0759  3         0.0348  3         2.5862  [vectors] (tgid:12078 range:0xffff0000-0xffff1000) [vectors] (tgid:12078 range:0xffff0000-0xffff1000)
166       0.0194  53        0.0259  11        0.1274  11        9.4828  seti_boinc               memset
155       0.0181  58        0.0284  6         0.0695  4         3.4483  seti_boinc               workunit_grp::workunit_grp()
153       0.0179  32        0.0157  0              0  0              0  seti_boinc               malloc_consolidate
147       0.0172  39        0.0191  2         0.0232  0              0  seti_boinc               cnvt_bin_hz(int, int)
137       0.0160  26        0.0127  10        0.1158  4         3.4483  seti_boinc               splitter_config::splitter_config()
136       0.0159  137       0.0670  1         0.0116  0              0  seti_boinc               fftwf_md5putc
136       0.0159  57        0.0279  1         0.0116  0              0  seti_boinc               powl
117       0.0137  60        0.0294  2         0.0232  4         3.4483  seti_boinc               operator new(unsigned int)
115       0.0134  18        0.0088  0              0  0              0  seti_boinc               fraction_done(double, double)
114       0.0133  22        0.0108  7         0.0811  6         5.1724  seti_boinc               tape::tape()
113       0.0132  70        0.0343  4         0.0463  3         2.5862  seti_boinc               bits_to_floats(unsigned char*, float (*) [2], int)
103       0.0120  14        0.0069  0              0  0              0  seti_boinc               __ieee754_log10
93        0.0109  55        0.0269  1         0.0116  0              0  seti_boinc               search0
89        0.0104  13        0.0064  0              0  0              0  seti_boinc               GetPulsePoTLen(long, int*, int*)
87        0.0102  14        0.0069  5         0.0579  2         1.7241  seti_boinc               recorder_config::recorder_config()
86        0.0101  20        0.0098  0              0  0              0  seti_boinc               fftwf_execute_dft
83        0.0097  72        0.0352  0              0  0              0  seti_boinc               __udivsi3
81        0.0095  18        0.0088  1         0.0116  0              0  seti_boinc               log10l
78        0.0091  17        0.0083  0              0  0              0  seti_boinc               isnanl
77        0.0090  30        0.0147  2         0.0232  7         6.0345  seti_boinc               data_description_t::data_description_t()
76        0.0089  17        0.0083  0              0  0              0  seti_boinc               __aeabi_d2ulz
70        0.0082  39        0.0191  3         0.0348  1         0.8621  seti_boinc               spike::spike()
63        0.0074  2        9.8e-04  4         0.0463  0              0  seti_boinc               boinc_fraction_done
61        0.0071  27        0.0132  0              0  0              0  seti_boinc               receiver_config::receiver_config()
55        0.0064  9         0.0044  0              0  0              0  seti_boinc               cexp_generic
53        0.0062  11        0.0054  0              0  0              0  seti_boinc               std::_Rb_tree<long long, std::pair<long long const, ChirpFftPair_t>, std::_Select1st<std::pair<long long const, ChirpFftPair_t> >, std::less<long long>, std::allocator<std::pair<long long const, ChirpFftPair_t> > >::_M_erase(std::_Rb_tree_node<std::pair<long long const, ChirpFftPair_t> >*)
53        0.0062  19        0.0093  0              0  0              0  seti_boinc               std::_Rb_tree_insert_and_rebalance(bool, std::_Rb_tree_node_base*, std::_Rb_tree_node_base*, std::_Rb_tree_node_base&)
52        0.0061  17        0.0083  0              0  0              0  seti_boinc               operator delete(void*)
52        0.0061  3         0.0015  0              0  1         0.8621  seti_boinc               std::_Rb_tree_increment(std::_Rb_tree_node_base const*)
49        0.0057  8         0.0039  0              0  0              0  seti_boinc               GetProgressUnitSize(int, int)
47        0.0055  38        0.0186  0              0  0              0  seti_boinc               SPIKE_INFO::~SPIKE_INFO()
47        0.0055  29        0.0142  1         0.0116  0              0  seti_boinc               T.9826
47        0.0055  20        0.0098  1         0.0116  0              0  seti_boinc               workunit_header::workunit_header()
45        0.0053  10        0.0049  3         0.0348  0              0  seti_boinc               result::result()
41        0.0048  11        0.0054  2         0.0232  3         2.5862  seti_boinc               subband_description_t::subband_description_t()
39        0.0046  4         0.0020  0              0  0              0  seti_boinc               invert_lcgf(float, float, float)
39        0.0046  5         0.0024  4         0.0463  1         0.8621  seti_boinc               pulse::pulse()
27        0.0032  3         0.0015  1         0.0116  0              0  seti_boinc               ComputePoTInfo(int, int)
25        0.0029  1        4.9e-04  0              0  0              0  seti_boinc               PULSE_INFO::PULSE_INFO()
24        0.0028  8         0.0039  0              0  0              0  seti_boinc               fftwf_ct_applicable
23        0.0027  14        0.0069  0              0  0              0  seti_boinc               cexpl_sqrtn_table
21        0.0025  5         0.0024  0              0  0              0  seti_boinc               __fixdfdi
20        0.0023  16        0.0078  1         0.0116  0              0  seti_boinc               SPIKE_INFO::SPIKE_INFO()
19        0.0022  8         0.0039  0              0  0              0  seti_boinc               floor
19        0.0022  23        0.0113  0              0  0              0  seti_boinc               mkplan
18        0.0021  10        0.0049  0              0  0              0  seti_boinc               PULSE_INFO::~PULSE_INFO()
18        0.0021  9         0.0044  0              0  0              0  seti_boinc               std::_Rb_tree<long long, std::pair<long long const, ChirpFftPair_t>, std::_Select1st<std::pair<long long const, ChirpFftPair_t> >, std::less<long long>, std::allocator<std::pair<long long const, ChirpFftPair_t> > >::_M_insert_unique_(std::_Rb_tree_const_iterator<std::pair<long long const, ChirpFftPair_t> >, std::pair<long long const, ChirpFftPair_t> const&)
17        0.0020  2        9.8e-04  0              0  0              0  seti_boinc               __aeabi_read_tp
17        0.0020  14        0.0069  0              0  0              0  seti_boinc               fftwf_md5putb
17        0.0020  4         0.0020  0              0  0              0  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
17        0.0020  1        4.9e-04  0              0  0              0  seti_boinc               timer_handler()
16        0.0019  13        0.0064  1         0.0116  0              0  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> > x_setiathome_decode<unsigned char>(char const*, unsigned int)
15        0.0018  6         0.0029  0              0  0              0  seti_boinc               T.9827
15        0.0018  5         0.0024  1         0.0116  0              0  seti_boinc               mkplan
14        0.0016  11        0.0054  0              0  0              0  seti_boinc               fftwf_md5end
14        0.0016  4         0.0020  0              0  0              0  seti_boinc               htab_lookup
14        0.0016  9         0.0044  0              0  0              0  seti_boinc               std::_Rb_tree_decrement(std::_Rb_tree_node_base const*)
13        0.0015  5         0.0024  0              0  1         0.8621  seti_boinc               T.9822
13        0.0015  2        9.8e-04  0              0  0              0  seti_boinc               apply
13        0.0015  3         0.0015  0              0  0              0  seti_boinc               hgrow
13        0.0015  14        0.0069  0              0  0              0  seti_boinc               std::_Rb_tree<long long, std::pair<long long const, ChirpFftPair_t>, std::_Select1st<std::pair<long long const, ChirpFftPair_t> >, std::less<long long>, std::allocator<std::pair<long long const, ChirpFftPair_t> > >::_M_insert_(std::_Rb_tree_node_base const*, std::_Rb_tree_node_base const*, std::pair<long long const, ChirpFftPair_t> const&)
12        0.0014  2        9.8e-04  0              0  0              0  seti_boinc               finite
12        0.0014  0              0  1         0.0116  0              0  seti_boinc               nanosleep
9         0.0011  1        4.9e-04  0              0  0              0  seti_boinc               boinc_sleep(double)
9         0.0011  6         0.0029  0              0  0              0  seti_boinc               hinsert0
9         0.0011  0              0  0              0  0              0  seti_boinc               worker_signal_handler(int)
8        9.4e-04  3         0.0015  0              0  0              0  seti_boinc               fftwf_mktensor
8        9.4e-04  1        4.9e-04  0              0  0              0  seti_boinc               mkplan
7        8.2e-04  0              0  0              0  0              0  seti_boinc               apply
7        8.2e-04  1        4.9e-04  0              0  0              0  seti_boinc               cosl
7        8.2e-04  6         0.0029  0              0  0              0  seti_boinc               fftwf_choose_radix
7        8.2e-04  1        4.9e-04  0              0  0              0  seti_boinc               fftwf_kernel_free
7        8.2e-04  2        9.8e-04  0              0  0              0  seti_boinc               fftwf_malloc
7        8.2e-04  2        9.8e-04  2         0.0232  0              0  seti_boinc               mkplan
6        7.0e-04  1        4.9e-04  0              0  0              0  seti_boinc               __aeabi_uidivmod
6        7.0e-04  0              0  0              0  0              0  seti_boinc               __ieee754_fmod
6        7.0e-04  0              0  0              0  0              0  seti_boinc               __libc_disable_asynccancel
6        7.0e-04  1        4.9e-04  0              0  0              0  seti_boinc               fftwf_ifree
6        7.0e-04  6         0.0029  0              0  0              0  seti_boinc               fftwf_malloc_plain
6        7.0e-04  0              0  0              0  0              0  seti_boinc               fftwf_plan_destroy_internal
6        7.0e-04  6         0.0029  0              0  0              0  seti_boinc               fftwf_tensor_compress
6        7.0e-04  0              0  0              0  0              0  seti_boinc               fftwf_tensor_sz
6        7.0e-04  5         0.0024  0              0  0              0  seti_boinc               htab_insert
6        7.0e-04  8         0.0039  0              0  0              0  seti_boinc               mkplan
6        7.0e-04  8         0.0039  0              0  0              0  seti_boinc               msort_with_tmp
6        7.0e-04  1        4.9e-04  0              0  0              0  seti_boinc               sinl
5        5.8e-04  8         0.0039  0              0  0              0  seti_boinc               __aeabi_idivmod
5        5.8e-04  0              0  0              0  0              0  seti_boinc               apply
5        5.8e-04  0              0  0              0  0              0  seti_boinc               dtime()
5        5.8e-04  0              0  0              0  0              0  seti_boinc               fftwf_tensor_copy
4        4.7e-04  0              0  0              0  0              0  seti_boinc               PulseProgressUnits(double, int)
4        4.7e-04  2        9.8e-04  0              0  0              0  seti_boinc               ___printf_fp
4        4.7e-04  1        4.9e-04  0              0  0              0  seti_boinc               __libc_enable_asynccancel
4        4.7e-04  1        4.9e-04  1         0.0116  1         0.8621  seti_boinc               calloc_a(unsigned int, unsigned int, unsigned int)
4        4.7e-04  0              0  0              0  0              0  seti_boinc               evaluate_plan
4        4.7e-04  2        9.8e-04  0              0  0              0  seti_boinc               fftwf_kernel_malloc
4        4.7e-04  1        4.9e-04  0              0  0              0  seti_boinc               fftwf_md5INT
4        4.7e-04  1        4.9e-04  0              0  0              0  seti_boinc               fftwf_md5int
4        4.7e-04  2        9.8e-04  0              0  0              0  seti_boinc               fftwf_twiddle_awake
4        4.7e-04  3         0.0015  0              0  0              0  seti_boinc               fill_slot
4        4.7e-04  0              0  0              0  0              0  seti_boinc               mkcldw
4        4.7e-04  0              0  0              0  0              0  seti_boinc               real_cexp
3        3.5e-04  0              0  0              0  0              0  seti_boinc               ____libc_disable_asynccancel_veneer
3        3.5e-04  0              0  0              0  0              0  seti_boinc               __default_sa_restorer_v2
3        3.5e-04  6         0.0029  0              0  0              0  seti_boinc               fftwf_hc2hc_applicable
3        3.5e-04  2        9.8e-04  0              0  0              0  seti_boinc               fftwf_isqrt
3        3.5e-04  1        4.9e-04  0              0  0              0  seti_boinc               fftwf_mkplan
3        3.5e-04  1        4.9e-04  0              0  0              0  seti_boinc               fftwf_tensor_compress_contiguous
3        3.5e-04  1        4.9e-04  0              0  0              0  seti_boinc               floorf
3        3.5e-04  0              0  0              0  0              0  seti_boinc               fmodl
3        3.5e-04  1        4.9e-04  0              0  0              0  seti_boinc               getrusage
3        3.5e-04  2        9.8e-04  0              0  0              0  seti_boinc               hash
3        3.5e-04  0              0  0              0  0              0  seti_boinc               hlookup
3        3.5e-04  0              0  0              0  0              0  seti_boinc               isinfl
3        3.5e-04  1        4.9e-04  0              0  0              0  seti_boinc               mkplan
3        3.5e-04  2        9.8e-04  0              0  0              0  seti_boinc               mkplan
3        3.5e-04  0              0  0              0  0              0  seti_boinc               mkplan
3        3.5e-04  0              0  1         0.0116  0              0  seti_boinc               mkplan
3        3.5e-04  1        4.9e-04  0              0  0              0  seti_boinc               qsort_r
3        3.5e-04  1        4.9e-04  0              0  0              0  seti_boinc               sincos
3        3.5e-04  0              0  0              0  0              0  seti_boinc               timer_thread(void*)
2        2.3e-04  0              0  0              0  0              0  seti_boinc               GaussFit(float*, int, int)
2        2.3e-04  0              0  0              0  0              0  seti_boinc               T.9831
2        2.3e-04  3         0.0015  0              0  0              0  seti_boinc               TripletProgressUnits()
2        2.3e-04  1        4.9e-04  0              0  0              0  seti_boinc               applicable
2        2.3e-04  0              0  0              0  0              0  seti_boinc               fftwf_ct_uglyp
2        2.3e-04  1        4.9e-04  0              0  0              0  seti_boinc               fftwf_dimcmp
2        2.3e-04  1        4.9e-04  0              0  0              0  seti_boinc               fftwf_free
2        2.3e-04  0              0  0              0  0              0  seti_boinc               fftwf_md5puts
2        2.3e-04  0              0  0              0  0              0  seti_boinc               fftwf_mkproblem_dft
2        2.3e-04  0              0  0              0  0              0  seti_boinc               fftwf_mkproblem_dft_d
2        2.3e-04  1        4.9e-04  0              0  0              0  seti_boinc               fftwf_ops_zero
2        2.3e-04  2        9.8e-04  0              0  0              0  seti_boinc               fftwf_tensor_destroy2
2        2.3e-04  0              0  0              0  0              0  seti_boinc               gettimeofday
2        2.3e-04  1        4.9e-04  0              0  0              0  seti_boinc               mkplan
2        2.3e-04  2        9.8e-04  0              0  0              0  seti_boinc               mkplan
2        2.3e-04  0              0  0              0  0              0  seti_boinc               mkplan
2        2.3e-04  1        4.9e-04  0              0  0              0  seti_boinc               mkplan
2        2.3e-04  0              0  0              0  0              0  seti_boinc               qsort
2        2.3e-04  0              0  0              0  0              0  seti_boinc               really_pickdim
1        1.2e-04  1        4.9e-04  0              0  0              0  seti_boinc               GaussianProgressUnits()
1        1.2e-04  0              0  0              0  0              0  seti_boinc               ____libc_enable_asynccancel_veneer
1        1.2e-04  0              0  0              0  0              0  seti_boinc               __dubsin
1        1.2e-04  1        4.9e-04  0              0  0              0  seti_boinc               __mpn_divrem
1        1.2e-04  0              0  0              0  0              0  seti_boinc               applicable_ip_sq_tiled
1        1.2e-04  0              0  0              0  0              0  seti_boinc               applicable_memcpy
1        1.2e-04  0              0  0              0  0              0  seti_boinc               apply
1        1.2e-04  0              0  0              0  1         0.8621  seti_boinc               apply_dit
1        1.2e-04  0              0  0              0  0              0  seti_boinc               boinc_worker_thread_cpu_time
1        1.2e-04  0              0  0              0  0              0  seti_boinc               buffered_vfprintf
1        1.2e-04  0              0  0              0  0              0  seti_boinc               destroy
1        1.2e-04  0              0  0              0  0              0  seti_boinc               destroy
1        1.2e-04  0              0  0              0  0              0  seti_boinc               fclose
1        1.2e-04  0              0  0              0  0              0  seti_boinc               fftwf_alignment_of
1        1.2e-04  0              0  0              0  0              0  seti_boinc               fftwf_first_divisor
1        1.2e-04  1        4.9e-04  0              0  0              0  seti_boinc               fftwf_iabs
1        1.2e-04  0              0  0              0  0              0  seti_boinc               fftwf_imin
1        1.2e-04  0              0  0              0  0              0  seti_boinc               fftwf_mapflags
1        1.2e-04  0              0  0              0  0              0  seti_boinc               fftwf_md5unsigned
1        1.2e-04  0              0  0              0  0              0  seti_boinc               fftwf_mkapiplan
1        1.2e-04  0              0  0              0  0              0  seti_boinc               fftwf_mkplan_d
1        1.2e-04  1        4.9e-04  0              0  0              0  seti_boinc               fftwf_mkplan_dft
1        1.2e-04  0              0  0              0  0              0  seti_boinc               fftwf_mktensor_2d
1        1.2e-04  0              0  0              0  0              0  seti_boinc               fftwf_nbuf
1        1.2e-04  2        9.8e-04  0              0  0              0  seti_boinc               fftwf_ops_madd
1        1.2e-04  0              0  0              0  0              0  seti_boinc               fftwf_ops_madd2
1        1.2e-04  2        9.8e-04  0              0  0              0  seti_boinc               fftwf_pickdim
1        1.2e-04  0              0  0              0  0              0  seti_boinc               fftwf_solvtab_exec
1        1.2e-04  1        4.9e-04  0              0  0              0  seti_boinc               fftwf_tensor_destroy4
1        1.2e-04  0              0  0              0  0              0  seti_boinc               fftwf_tensor_equal
1        1.2e-04  0              0  0              0  0              0  seti_boinc               free_a(void*)
1        1.2e-04  0              0  0              0  0              0  seti_boinc               getchr_str
1        1.2e-04  0              0  0              0  0              0  seti_boinc               getlong
1        1.2e-04  0              0  0              0  0              0  seti_boinc               hack_digit.11765
1        1.2e-04  0              0  0              0  0              0  seti_boinc               malloc_a(unsigned int, unsigned int)
1        1.2e-04  2        9.8e-04  0              0  0              0  seti_boinc               memmove
1        1.2e-04  0              0  0              0  0              0  seti_boinc               mkcldw
1        1.2e-04  0              0  0              0  0              0  seti_boinc               mkplan
1        1.2e-04  0              0  0              0  0              0  seti_boinc               pthread_once
1        1.2e-04  0              0  0              0  0              0  seti_boinc               putchr_cnt
1        1.2e-04  0              0  0              0  0              0  seti_boinc               recorder_config::print_xml(int, int, int, char const*) const
1        1.2e-04  0              0  0              0  0              0  seti_boinc               register_solver
1        1.2e-04  0              0  0              0  0              0  seti_boinc               regone
1        1.2e-04  0              0  0              0  0              0  seti_boinc               result::operator=(result const&)
1        1.2e-04  0              0  0              0  0              0  seti_boinc               std::num_put<char, std::ostreambuf_iterator<char, std::char_traits<char> > >::do_put(std::ostreambuf_iterator<char, std::char_traits<char> >, std::ios_base&, char, long long) const
1        1.2e-04  0              0  0              0  0              0  seti_boinc               std::ostreambuf_iterator<char, std::char_traits<char> > std::num_put<char, std::ostreambuf_iterator<char, std::char_traits<char> > >::_M_insert_float<double>(std::ostreambuf_iterator<char, std::char_traits<char> >, std::ios_base&, char, char, double) const
1        1.2e-04  0              0  0              0  0              0  seti_boinc               std::string::assign(std::string const&)
1        1.2e-04  0              0  0              0  0              0  seti_boinc               strchrnul
1        1.2e-04  0              0  0              0  0              0  seti_boinc               usleep
1        1.2e-04  0              0  0              0  0              0  seti_boinc               vprint
0              0  1        4.9e-04  0              0  0              0  seti_boinc               Llastword
0              0  1        4.9e-04  0              0  0              0  seti_boinc               bool std::has_facet<std::num_get<char, std::istreambuf_iterator<char, std::char_traits<char> > > >(std::locale const&)
0              0  1        4.9e-04  0              0  0              0  seti_boinc               destroy
0              0  1        4.9e-04  0              0  0              0  seti_boinc               fftwf_mkproblem_rdft
0              0  2        9.8e-04  0              0  0              0  seti_boinc               fftwf_tensor_append
0              0  3         0.0015  0              0  0              0  seti_boinc               fftwf_tensor_destroy
0              0  1        4.9e-04  0              0  0              0  seti_boinc               fftwf_tensor_md5
0              0  1        4.9e-04  0              0  0              0  seti_boinc               fftwf_tensor_tornk1
0              0  1        4.9e-04  0              0  0              0  seti_boinc               mkcldw
0              0  1        4.9e-04  0              0  0              0  seti_boinc               mygetc
0              0  3         0.0015  0              0  0              0  seti_boinc               okp
0              0  1        4.9e-04  0              0  0              0  seti_boinc               putulong
0              0  1        4.9e-04  0              0  0              0  seti_boinc               std::string::_Rep::_S_create(unsigned int, unsigned int, std::allocator<char> const&)
 
 
Tue Oct  4 02:47:20 CST 2011
CPU: ARM Cortex-A8, speed 1e+06 MHz (estimated)
Counted PC_BRANCH_EXECUTED events (Any taken branch that is executed) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_BRANCH_MIS_PRED events (Branch mispredicted or not predicted. Counts pipeline flushes because of misprediction) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_BRANCH_MIS_USED events (Branch or change in program flow that could have been predicted) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_IMM_BRANCH events (Immediate branch instruction executed (taken or not)) with a unit mask of 0x00 (No unit mask) count 200000
PC_BRANCH_EXEC...|PC_BRANCH_MIS_...|PC_BRANCH_MIS_...|PC_IMM_BRANCH:...|
  samples|      %|  samples|      %|  samples|      %|  samples|      %|
------------------------------------------------------------------------
     1683 90.1929       120 80.0000      2129 84.5177      1984 85.0772 seti_boinc
	PC_BRANCH_EXEC...|PC_BRANCH_MIS_...|PC_BRANCH_MIS_...|PC_IMM_BRANCH:...|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	     1674 99.4652       119 99.1667      2112 99.2015      1965 99.0423 seti_boinc
	        9  0.5348         1  0.8333        17  0.7985        19  0.9577 [vectors] (tgid:12078 range:0xffff0000-0xffff1000)
      128  6.8596        15 10.0000       236  9.3688       221  9.4768 libc-2.11.1.so
       19  1.0182         2  1.3333        51  2.0246        45  1.9297 libavahi-common.so.3.5.1
       15  0.8039         5  3.3333        53  2.1040        44  1.8868 ld-2.11.1.so
        8  0.4287         5  3.3333        15  0.5955        13  0.5575 dash
	PC_BRANCH_EXEC...|PC_BRANCH_MIS_...|PC_BRANCH_MIS_...|PC_IMM_BRANCH:...|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	        8 100.000         5 100.000        14 93.3333        13 100.000 dash
	        0       0         0       0         1  6.6667         0       0 [vectors] (tgid:14338 range:0xffff0000-0xffff1000)
        4  0.2144         1  0.6667         9  0.3573         3  0.1286 gawk
        3  0.1608         1  0.6667         7  0.2779         8  0.3431 ophelp
        2  0.1072         1  0.6667         5  0.1985         2  0.0858 libavahi-core.so.6.0.1
        2  0.1072         0       0         0       0         1  0.0429 ntpd
        1  0.0536         0       0         0       0         1  0.0429 libpthread-2.11.1.so
        1  0.0536         0       0         0       0         0       0 LC_CTYPE
        0       0         0       0         1  0.0397         0       0 ls
        0       0         0       0         1  0.0397         0       0 libm-2.11.1.so
        0       0         0       0         0       0         1  0.0429 libpam.so.0.82.2
        0       0         0       0         0       0         1  0.0429 apt-get
	PC_BRANCH_EXEC...|PC_BRANCH_MIS_...|PC_BRANCH_MIS_...|PC_IMM_BRANCH:...|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	        0       0         0       0         0       0         1 100.000 [vectors] (tgid:11952 range:0xffff0000-0xffff1000)
        0       0         0       0         1  0.0397         0       0 sudo
        0       0         0       0         3  0.1191         3  0.1286 libapt-pkg-libc6.10-6.so.4.8.0
        0       0         0       0         7  0.2779         5  0.2144 avahi-daemon
	PC_BRANCH_EXEC...|PC_BRANCH_MIS_...|PC_BRANCH_MIS_...|PC_IMM_BRANCH:...|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	        0       0         0       0         1 14.2857         0       0 avahi-daemon
	        0       0         0       0         6 85.7143         5 100.000 [vectors] (tgid:3312 range:0xffff0000-0xffff1000)
        0       0         0       0         1  0.0397         0       0 sshd
 
CPU: ARM Cortex-A8, speed 1e+06 MHz (estimated)
Counted PC_BRANCH_EXECUTED events (Any taken branch that is executed) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_BRANCH_MIS_PRED events (Branch mispredicted or not predicted. Counts pipeline flushes because of misprediction) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_BRANCH_MIS_USED events (Branch or change in program flow that could have been predicted) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_IMM_BRANCH events (Immediate branch instruction executed (taken or not)) with a unit mask of 0x00 (No unit mask) count 200000
samples  %        samples  %        samples  %        samples  %        image name               symbol name
587      34.8782  43       35.8333  660      31.0005  631      31.8044  seti_boinc               top_sum2(float**, PoTPlan*)
213      12.6560  4         3.3333  198       9.3001  182       9.1734  seti_boinc               top_sum3(float**, PoTPlan*)
171      10.1604  3         2.5000  197       9.2532  181       9.1230  seti_boinc               top_sum4(float**, PoTPlan*)
144       8.5561  1         0.8333  160       7.5153  152       7.6613  seti_boinc               top_sum5(float**, PoTPlan*)
117       6.9519  12       10.0000  207       9.7229  153       7.7117  seti_boinc               find_pulse(float const*, int, float, int, int)
71        4.2187  18       15.0000  100       4.6970  86        4.3347  seti_boinc               sw_sum2_t31(float**, PoTPlan*)
69        4.0998  5         4.1667  125       5.8713  145       7.3085  seti_boinc               __divsi3
64        3.8027  1         0.8333  111       5.2137  119       5.9980  seti_boinc               t_funct(int, int, int)
30        1.7825  1         0.8333  26        1.2212  24        1.2097  seti_boinc               ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
22        1.3072  3         2.5000  27        1.2682  28        1.4113  seti_boinc               __ieee754_log
21        1.2478  3         2.5000  31        1.4561  15        0.7560  seti_boinc               FindSpikes(float*, int, int, SETI_WU_INFO&)
17        1.0101  4         3.3333  35        1.6440  33        1.6633  seti_boinc               _int_malloc
16        0.9507  3         2.5000  31        1.4561  25        1.2601  seti_boinc               _int_free
10        0.5942  0              0  13        0.6106  12        0.6048  seti_boinc               find_triplets(float const*, int, float, int, int)
9         0.5348  1         0.8333  17        0.7985  19        0.9577  [vectors] (tgid:12078 range:0xffff0000-0xffff1000) [vectors] (tgid:12078 range:0xffff0000-0xffff1000)
9         0.5348  1         0.8333  22        1.0333  14        0.7056  seti_boinc               malloc
8         0.4753  0              0  24        1.1273  16        0.8065  seti_boinc               free
8         0.4753  2         1.6667  13        0.6106  18        0.9073  seti_boinc               time_to_ra_dec(double, double*, double*)
6         0.3565  0              0  3         0.1409  3         0.1512  seti_boinc               analyze_pot(float*, int, ChirpFftPair_t&)
6         0.3565  1         0.8333  7         0.3288  5         0.2520  seti_boinc               logl
6         0.3565  0              0  7         0.3288  11        0.5544  seti_boinc               memset
5         0.2971  0              0  5         0.2349  5         0.2520  seti_boinc               GetFixedPoT(float*, int, int, float*, int, int)
5         0.2971  0              0  3         0.1409  2         0.1008  seti_boinc               analysis_config::analysis_config()
5         0.2971  0              0  7         0.3288  1         0.0504  seti_boinc               lcgf(double, double)
5         0.2971  0              0  11        0.5167  8         0.4032  seti_boinc               powl
4         0.2377  0              0  4         0.1879  0              0  seti_boinc               SpikeProgressUnits(int)
4         0.2377  0              0  2         0.0939  0              0  seti_boinc               subband_description_t::subband_description_t()
4         0.2377  1         0.8333  3         0.1409  5         0.2520  seti_boinc               v_GetPowerSpectrum(float (*) [2], float*, int)
4         0.2377  2         1.6667  5         0.2349  1         0.0504  seti_boinc               workunit_grp::workunit_grp()
3         0.1783  0              0  0              0  6         0.3024  seti_boinc               T.9827
3         0.1783  0              0  5         0.2349  4         0.2016  seti_boinc               __exp1
3         0.1783  1         0.8333  3         0.1409  9         0.4536  seti_boinc               malloc_consolidate
3         0.1783  3         2.5000  4         0.1879  7         0.3528  seti_boinc               operator delete(void*)
3         0.1783  1         0.8333  6         0.2818  7         0.3528  seti_boinc               receiver_config::receiver_config()
2         0.1188  0              0  4         0.1879  2         0.1008  seti_boinc               PULSE_INFO::~PULSE_INFO()
2         0.1188  0              0  5         0.2349  2         0.1008  seti_boinc               SPIKE_INFO::~SPIKE_INFO()
2         0.1188  0              0  3         0.1409  5         0.2520  seti_boinc               T.9826
2         0.1188  0              0  0              0  1         0.0504  seti_boinc               __ieee754_log10
2         0.1188  0              0  8         0.3758  8         0.4032  seti_boinc               __ieee754_pow
2         0.1188  0              0  1         0.0470  0              0  seti_boinc               invert_lcgf(float, float, float)
2         0.1188  0              0  0              0  0              0  seti_boinc               log10l
2         0.1188  0              0  3         0.1409  6         0.3024  seti_boinc               operator new(unsigned int)
2         0.1188  0              0  2         0.0939  0              0  seti_boinc               result::result()
2         0.1188  1         0.8333  1         0.0470  1         0.0504  seti_boinc               workunit_header::workunit_header()
1         0.0594  0              0  2         0.0939  2         0.1008  seti_boinc               T.9822
1         0.0594  0              0  0              0  0              0  seti_boinc               __mpn_extract_double
1         0.0594  3         2.5000  1         0.0470  7         0.3528  seti_boinc               cnvt_bin_hz(int, int)
1         0.0594  0              0  4         0.1879  1         0.0504  seti_boinc               isnanl
1         0.0594  0              0  1         0.0470  1         0.0504  seti_boinc               n1_16
1         0.0594  0              0  3         0.1409  1         0.0504  seti_boinc               recorder_config::recorder_config()
1         0.0594  0              0  4         0.1879  1         0.0504  seti_boinc               seti_analyze(ANALYSIS_STATE&)
1         0.0594  1         0.8333  0              0  1         0.0504  seti_boinc               splitter_config::splitter_config()
0              0  0              0  0              0  1         0.0504  seti_boinc               __aeabi_read_tp
0              0  0              0  0              0  1         0.0504  seti_boinc               __mpn_divrem
0              0  0              0  1         0.0470  0              0  seti_boinc               apply
0              0  0              0  2         0.0939  0              0  seti_boinc               boinc_fraction_done
0              0  0              0  1         0.0470  3         0.1512  seti_boinc               calc_detection_freq(double, double, double)
0              0  0              0  1         0.0470  2         0.1008  seti_boinc               data_description_t::data_description_t()
0              0  0              0  3         0.1409  1         0.0504  seti_boinc               fftwf_execute_dft
0              0  0              0  1         0.0470  1         0.0504  seti_boinc               fftwf_free
0              0  1         0.8333  0              0  1         0.0504  seti_boinc               fftwf_kernel_malloc
0              0  0              0  1         0.0470  1         0.0504  seti_boinc               fraction_done(double, double)
0              0  0              0  1         0.0470  0              0  seti_boinc               free_a(void*)
0              0  0              0  1         0.0470  0              0  seti_boinc               isinfl
0              0  0              0  0              0  1         0.0504  seti_boinc               malloc_a(unsigned int, unsigned int)
0              0  0              0  1         0.0470  0              0  seti_boinc               pulse::pulse()
0              0  0              0  0              0  1         0.0504  seti_boinc               spike::spike()
0              0  0              0  2         0.0939  2         0.1008  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
0              0  0              0  0              0  3         0.1512  seti_boinc               tape::tape()
 
 
Tue Oct  4 02:50:43 CST 2011
CPU: ARM Cortex-A8, speed 1e+06 MHz (estimated)
Counted CYCLES_INST_STALL events (Cycles where no instruction available) with a unit mask of 0x00 (No unit mask) count 200000
Counted CYCLES_NEON_DATA_STALL events (Number of cycles the processor waits on MRC data from NEON) with a unit mask of 0x00 (No unit mask) count 200000
Counted DTLB_REFILL events (Data R/W that causes a TLB refill) with a unit mask of 0x00 (No unit mask) count 200000
Counted ITLB_MISS events (Instruction fetch misses from TLB) with a unit mask of 0x00 (No unit mask) count 200000
CYCLES_INST_ST...|CYCLES_NEON_DA...|DTLB_REFILL:20...| ITLB_MISS:200000|
  samples|      %|  samples|      %|  samples|      %|  samples|      %|
------------------------------------------------------------------------
     4126 66.7422    514388 100.000        98 77.7778         3 100.000 seti_boinc
	CYCLES_INST_ST...|CYCLES_NEON_DA...|DTLB_REFILL:20...| ITLB_MISS:200000|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	     4103 99.4426    514388 100.000        97 98.9796         3 100.000 seti_boinc
	       23  0.5574         0       0         1  1.0204         0       0 [vectors] (tgid:12078 range:0xffff0000-0xffff1000)
      974 15.7554         0       0         6  4.7619         0       0 libc-2.11.1.so
      315  5.0954         0       0         1  0.7937         0       0 ld-2.11.1.so
      246  3.9793         0       0         2  1.5873         0       0 updatedb.mlocate
	CYCLES_INST_ST...|CYCLES_NEON_DA...|DTLB_REFILL:20...| ITLB_MISS:200000|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	      229 93.0894         0       0         2 100.000         0       0 updatedb.mlocate
	       17  6.9106         0       0         0       0         0       0 [vectors] (tgid:15924 range:0xffff0000-0xffff1000)
       82  1.3264         0       0         0       0         0       0 dash
       80  1.2941         0       0        15 11.9048         0       0 gzip
       70  1.1323         0       0         1  0.7937         0       0 dpkg-query
       49  0.7926         0       0         0       0         0       0 gawk
       28  0.4529         0       0         0       0         0       0 oprofiled
	CYCLES_INST_ST...|CYCLES_NEON_DA...|DTLB_REFILL:20...| ITLB_MISS:200000|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	       27 96.4286         0       0         0       0         0       0 oprofiled
	        1  3.5714         0       0         0       0         0       0 [vectors] (tgid:15651 range:0xffff0000-0xffff1000)
       24  0.3882         0       0         1  0.7937         0       0 libavahi-core.so.6.0.1
       18  0.2912         0       0         0       0         0       0 libapt-pkg-libc6.10-6.so.4.8.0
       18  0.2912         0       0         0       0         0       0 libgdbm.so.3.0.0
       17  0.2750         0       0         0       0         0       0 libavahi-common.so.3.5.1
       14  0.2265         0       0         1  0.7937         0       0 mandb
	CYCLES_INST_ST...|CYCLES_NEON_DA...|DTLB_REFILL:20...| ITLB_MISS:200000|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	       12 85.7143         0       0         1 100.000         0       0 mandb
	        2 14.2857         0       0         0       0         0       0 [vectors] (tgid:15901 range:0xffff0000-0xffff1000)
       12  0.1941         0       0         0       0         0       0 libstdc++.so.6.0.13
       11  0.1779         0       0         0       0         0       0 ophelp
        9  0.1456         0       0         0       0         0       0 bash
        6  0.0971         0       0         0       0         0       0 grep
        6  0.0971         0       0         0       0         0       0 libdbus-1.so.3.4.0
        6  0.0971         0       0         0       0         0       0 logrotate
        5  0.0809         0       0         0       0         0       0 find
        5  0.0809         0       0         0       0         0       0 ntpd
        5  0.0809         0       0         0       0         0       0 rsyslogd
        4  0.0647         0       0         0       0         0       0 libgcc_s.so.1
        4  0.0647         0       0         0       0         0       0 cupsd
        3  0.0485         0       0         0       0         0       0 chown
        3  0.0485         0       0         0       0         0       0 date
        3  0.0485         0       0         0       0         0       0 libnih.so.1.0.0
        3  0.0485         0       0         0       0         0       0 libpopt.so.0.0.0
        3  0.0485         0       0         0       0         0       0 libpthread-2.11.1.so
        3  0.0485         0       0         0       0         0       0 sudo
        3  0.0485         0       0         0       0         0       0 avahi-daemon
        2  0.0324         0       0         0       0         0       0 ls
        2  0.0324         0       0         0       0         0       0 libdl-2.11.1.so
        2  0.0324         0       0         0       0         0       0 libm-2.11.1.so
        2  0.0324         0       0         0       0         0       0 libselinux.so.1
        2  0.0324         0       0         0       0         0       0 init
	CYCLES_INST_ST...|CYCLES_NEON_DA...|DTLB_REFILL:20...| ITLB_MISS:200000|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	        1 50.0000         0       0         0       0         0       0 init
	        1 50.0000         0       0         0       0         0       0 [vectors] (tgid:1 range:0xffff0000-0xffff1000)
        2  0.0324         0       0         0       0         0       0 libcups.so.2
        2  0.0324         0       0         0       0         0       0 LC_CTYPE
        1  0.0162         0       0         0       0         0       0 cat
        1  0.0162         0       0         0       0         0       0 mv
        1  0.0162         0       0         0       0         0       0 ld.so.cache
        1  0.0162         0       0         0       0         0       0 libcrypto.so.0.9.8
        1  0.0162         0       0         0       0         0       0 pam_limits.so
        1  0.0162         0       0         0       0         0       0 pam_unix.so
        1  0.0162         0       0         0       0         0       0 basename
        1  0.0162         0       0         0       0         0       0 dirname
        1  0.0162         0       0         0       0         0       0 dpkg
        1  0.0162         0       0         1  0.7937         0       0 seq
        1  0.0162         0       0         0       0         0       0 gconv-modules.cache
        1  0.0162         0       0         0       0         0       0 libcupsmime.so.1
        1  0.0162         0       0         0       0         0       0 LC_COLLATE
 
CPU: ARM Cortex-A8, speed 1e+06 MHz (estimated)
Counted CYCLES_INST_STALL events (Cycles where no instruction available) with a unit mask of 0x00 (No unit mask) count 200000
Counted CYCLES_NEON_DATA_STALL events (Number of cycles the processor waits on MRC data from NEON) with a unit mask of 0x00 (No unit mask) count 200000
Counted DTLB_REFILL events (Data R/W that causes a TLB refill) with a unit mask of 0x00 (No unit mask) count 200000
Counted ITLB_MISS events (Instruction fetch misses from TLB) with a unit mask of 0x00 (No unit mask) count 200000
samples  %        samples  %        samples  %        samples  %        image name               symbol name
1219     29.5444  249945   48.5908  18       18.3673  0              0  seti_boinc               top_sum2(float**, PoTPlan*)
473      11.4639  106684   20.7400  16       16.3265  0              0  seti_boinc               top_sum3(float**, PoTPlan*)
339       8.2162  9030      1.7555  1         1.0204  0              0  seti_boinc               sw_sum2_t31(float**, PoTPlan*)
333       8.0708  81698    15.8826  21       21.4286  0              0  seti_boinc               top_sum4(float**, PoTPlan*)
315       7.6345  1983      0.3855  2         2.0408  1        33.3333  seti_boinc               find_pulse(float const*, int, float, int, int)
257       6.2288  60231    11.7093  9         9.1837  0              0  seti_boinc               top_sum5(float**, PoTPlan*)
182       4.4111  0              0  0              0  0              0  seti_boinc               __divsi3
111       2.6903  143       0.0278  14       14.2857  0              0  seti_boinc               t_funct(int, int, int)
110       2.6660  0              0  1         1.0204  0              0  seti_boinc               _int_malloc
78        1.8905  1187      0.2308  1         1.0204  1        33.3333  seti_boinc               ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
66        1.5996  0              0  0              0  0              0  seti_boinc               _int_free
35        0.8483  0              0  0              0  0              0  seti_boinc               free
34        0.8240  0              0  3         3.0612  0              0  seti_boinc               malloc
31        0.7513  176       0.0342  0              0  0              0  seti_boinc               time_to_ra_dec(double, double*, double*)
27        0.6544  310       0.0603  0              0  0              0  seti_boinc               find_triplets(float const*, int, float, int, int)
24        0.5817  0              0  2         2.0408  0              0  seti_boinc               malloc_consolidate
23        0.5574  0              0  1         1.0204  0              0  [vectors] (tgid:12078 range:0xffff0000-0xffff1000) [vectors] (tgid:12078 range:0xffff0000-0xffff1000)
22        0.5332  620       0.1205  2         2.0408  0              0  seti_boinc               __ieee754_log
21        0.5090  0              0  0              0  0              0  seti_boinc               memset
21        0.5090  0              0  1         1.0204  0              0  seti_boinc               workunit_grp::workunit_grp()
20        0.4847  1        1.9e-04  0              0  0              0  seti_boinc               PULSE_INFO::PULSE_INFO()
19        0.4605  204       0.0397  1         1.0204  0              0  seti_boinc               FindSpikes(float*, int, int, SETI_WU_INFO&)
17        0.4120  580       0.1128  0              0  0              0  seti_boinc               analyze_pot(float*, int, ChirpFftPair_t&)
16        0.3878  0              0  0              0  0              0  seti_boinc               PULSE_INFO::~PULSE_INFO()
16        0.3878  0              0  0              0  0              0  seti_boinc               memcpy
15        0.3635  6         0.0012  1         1.0204  0              0  seti_boinc               floorf
15        0.3635  0              0  1         1.0204  0              0  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
14        0.3393  215       0.0418  0              0  0              0  seti_boinc               n1_32
14        0.3393  4        7.8e-04  0              0  0              0  seti_boinc               operator delete(void*)
14        0.3393  0              0  0              0  0              0  seti_boinc               pulse::pulse()
13        0.3151  27        0.0052  0              0  0              0  seti_boinc               cnvt_bin_hz(int, int)
12        0.2908  0              0  0              0  0              0  seti_boinc               receiver_config::receiver_config()
12        0.2908  0              0  1         1.0204  0              0  seti_boinc               splitter_config::splitter_config()
11        0.2666  0              0  0              0  0              0  seti_boinc               operator new(unsigned int)
9         0.2181  0              0  0              0  0              0  seti_boinc               __libc_disable_asynccancel
9         0.2181  50        0.0097  1         1.0204  0              0  seti_boinc               calc_detection_freq(double, double, double)
9         0.2181  0              0  0              0  0              0  seti_boinc               result::result()
8         0.1939  36        0.0070  0              0  0              0  seti_boinc               SpikeProgressUnits(int)
8         0.1939  0              0  0              0  0              0  seti_boinc               T.9826
8         0.1939  0              0  0              0  0              0  seti_boinc               subband_description_t::subband_description_t()
7         0.1697  138       0.0268  0              0  0              0  seti_boinc               __ieee754_pow
7         0.1697  0              0  0              0  1        33.3333  seti_boinc               fftwf_kernel_malloc
7         0.1697  0              0  0              0  0              0  seti_boinc               recorder_config::recorder_config()
7         0.1697  0              0  0              0  0              0  seti_boinc               workunit_header::workunit_header()
6         0.1454  0              0  0              0  0              0  seti_boinc               T.9822
6         0.1454  0              0  0              0  0              0  seti_boinc               __aeabi_read_tp
6         0.1454  0              0  0              0  0              0  seti_boinc               data_description_t::data_description_t()
5         0.1212  0              0  0              0  0              0  seti_boinc               analysis_config::analysis_config()
5         0.1212  0              0  0              0  0              0  seti_boinc               calloc_a(unsigned int, unsigned int, unsigned int)
5         0.1212  0              0  0              0  0              0  seti_boinc               getrusage
5         0.1212  0              0  0              0  0              0  seti_boinc               nanosleep
5         0.1212  0              0  0              0  0              0  seti_boinc               timer_handler()
5         0.1212  306       0.0595  0              0  0              0  seti_boinc               v_GetPowerSpectrum(float (*) [2], float*, int)
4         0.0969  254       0.0494  0              0  0              0  seti_boinc               GetFixedPoT(float*, int, int, float*, int, int)
4         0.0969  0              0  0              0  0              0  seti_boinc               __ieee754_fmod
4         0.0969  0              0  0              0  0              0  seti_boinc               fftwf_malloc
4         0.0969  0              0  0              0  0              0  seti_boinc               fmodl
4         0.0969  0              0  0              0  0              0  seti_boinc               tape::tape()
3         0.0727  0              0  0              0  0              0  seti_boinc               T.9827
3         0.0727  169       0.0329  0              0  0              0  seti_boinc               __exp1
3         0.0727  0              0  0              0  0              0  seti_boinc               boinc_sleep(double)
3         0.0727  0              0  0              0  0              0  seti_boinc               gettimeofday
3         0.0727  0              0  0              0  0              0  seti_boinc               isnanl
3         0.0727  37        0.0072  0              0  0              0  seti_boinc               logl
3         0.0727  39        0.0076  0              0  0              0  seti_boinc               seti_analyze(ANALYSIS_STATE&)
3         0.0727  0              0  0              0  0              0  seti_boinc               worker_signal_handler(int)
2         0.0485  0              0  0              0  0              0  seti_boinc               __default_sa_restorer_v2
2         0.0485  0              0  0              0  0              0  seti_boinc               __libc_enable_asynccancel
2         0.0485  2        3.9e-04  0              0  0              0  seti_boinc               apply
2         0.0485  0              0  0              0  0              0  seti_boinc               boinc_fraction_done
2         0.0485  0              0  0              0  0              0  seti_boinc               fftwf_kernel_free
2         0.0485  17        0.0033  0              0  0              0  seti_boinc               fraction_done(double, double)
2         0.0485  0              0  0              0  0              0  seti_boinc               free_a(void*)
2         0.0485  0              0  0              0  0              0  seti_boinc               malloc_a(unsigned int, unsigned int)
2         0.0485  0              0  0              0  0              0  seti_boinc               memmove
2         0.0485  0              0  0              0  0              0  seti_boinc               usleep
1         0.0242  0              0  0              0  0              0  seti_boinc               SPIKE_INFO::SPIKE_INFO()
1         0.0242  0              0  0              0  0              0  seti_boinc               T.9831
1         0.0242  0              0  0              0  0              0  seti_boinc               ____libc_disable_asynccancel_veneer
1         0.0242  0              0  0              0  0              0  seti_boinc               ____libc_enable_asynccancel_veneer
1         0.0242  0              0  0              0  0              0  seti_boinc               dtime()
1         0.0242  13        0.0025  0              0  0              0  seti_boinc               powl
0              0  0              0  1         1.0204  0              0  seti_boinc               SPIKE_INFO::~SPIKE_INFO()
0              0  19        0.0037  0              0  0              0  seti_boinc               __ieee754_log10
0              0  2        3.9e-04  0              0  0              0  seti_boinc               fftwf_execute_dft
0              0  4        7.8e-04  0              0  0              0  seti_boinc               finite
0              0  9         0.0017  0              0  0              0  seti_boinc               invert_lcgf(float, float, float)
0              0  242       0.0470  0              0  0              0  seti_boinc               lcgf(double, double)
0              0  7         0.0014  0              0  0              0  seti_boinc               log10l
 
 
```
## ARM Cortex-A8 Events ##
using oprofile v0.9.7
```
lucid@lucid-desktop:~/oprofile-0.9.7$ sudo opcontrol --list-events
oprofile: available events for CPU type "ARM Cortex-A8"

See Cortex-A8 Technical Reference Manual
Cortex A8 DDI (ARM DDI 0344B, revision r1p1)
For architectures using unit masks, you may be able to specify
unit masks by name.  See 'opcontrol' man page for more details.

PMNC_SW_INCR: (counter: 1, 2, 3, 4, 5, 6)
	Software increment of PMNC registers (min count: 500)
IFETCH_MISS: (counter: 1, 2, 3, 4, 5, 6)
	Instruction fetch misses from cache or normal cacheable memory (min count: 500)
ITLB_MISS: (counter: 1, 2, 3, 4, 5, 6)
	Instruction fetch misses from TLB (min count: 500)
DCACHE_REFILL: (counter: 1, 2, 3, 4, 5, 6)
	Data R/W operation that causes a refill from cache or normal cacheable memory (min count: 
        500)
DCACHE_ACCESS: (counter: 1, 2, 3, 4, 5, 6)
	Data R/W from cache (min count: 500)
DTLB_REFILL: (counter: 1, 2, 3, 4, 5, 6)
	Data R/W that causes a TLB refill (min count: 500)
DREAD: (counter: 1, 2, 3, 4, 5, 6)
	Data read architecturally executed (note: architecturally executed = for instructions that 
        are unconditional or that pass the condition code) (min count: 500)
DWRITE: (counter: 1, 2, 3, 4, 5, 6)
	Data write architecturally executed (min count: 500)
INSTR_EXECUTED: (counter: 1, 2, 3, 4, 5, 6)
	All executed instructions (min count: 500)
EXC_TAKEN: (counter: 1, 2, 3, 4, 5, 6)
	Exception taken (min count: 500)
EXC_EXECUTED: (counter: 1, 2, 3, 4, 5, 6)
	Exception return architecturally executed (min count: 500)
CID_WRITE: (counter: 1, 2, 3, 4, 5, 6)
	Instruction that writes to the Context ID Register architecturally executed (min count: 
        500)
PC_WRITE: (counter: 1, 2, 3, 4, 5, 6)
	SW change of PC, architecturally executed (not by exceptions) (min count: 500)
PC_IMM_BRANCH: (counter: 1, 2, 3, 4, 5, 6)
	Immediate branch instruction executed (taken or not) (min count: 500)
PC_PROC_RETURN: (counter: 1, 2, 3, 4, 5, 6)
	Procedure return architecturally executed (not by exceptions) (min count: 500)
UNALIGNED_ACCESS: (counter: 1, 2, 3, 4, 5, 6)
	Unaligned access architecturally executed (min count: 500)
PC_BRANCH_MIS_PRED: (counter: 1, 2, 3, 4, 5, 6)
	Branch mispredicted or not predicted. Counts pipeline flushes because of misprediction 
        (min count: 500)
PC_BRANCH_MIS_USED: (counter: 1, 2, 3, 4, 5, 6)
	Branch or change in program flow that could have been predicted (min count: 500)
CPU_CYCLES: (counter: 0)
	Number of CPU cycles (min count: 500)
WRITE_BUFFER_FULL: (counter: 1, 2, 3, 4)
	Any write buffer full cycle (min count: 500)
L2_STORE_MERGED: (counter: 1, 2, 3, 4)
	Any store that is merged in L2 cache (min count: 500)
L2_STORE_BUFF: (counter: 1, 2, 3, 4)
	Any bufferable store from load/store to L2 cache (min count: 500)
L2_ACCESS: (counter: 1, 2, 3, 4)
	Any access to L2 cache (min count: 500)
L2_CACH_MISS: (counter: 1, 2, 3, 4)
	Any cacheable miss in L2 cache (min count: 500)
AXI_READ_CYCLES: (counter: 1, 2, 3, 4)
	Number of cycles for an active AXI read (min count: 500)
AXI_WRITE_CYCLES: (counter: 1, 2, 3, 4)
	Number of cycles for an active AXI write (min count: 500)
MEMORY_REPLAY: (counter: 1, 2, 3, 4)
	Any replay event in the memory subsystem (min count: 500)
UNALIGNED_ACCESS_REPLAY: (counter: 1, 2, 3, 4)
	Unaligned access that causes a replay (min count: 500)
L1_DATA_MISS: (counter: 1, 2, 3, 4)
	L1 data cache miss as a result of the hashing algorithm (min count: 500)
L1_INST_MISS: (counter: 1, 2, 3, 4)
	L1 instruction cache miss as a result of the hashing algorithm (min count: 500)
L1_DATA_COLORING: (counter: 1, 2, 3, 4)
	L1 data access in which a page coloring alias occurs (min count: 500)
L1_NEON_DATA: (counter: 1, 2, 3, 4)
	NEON data access that hits L1 cache (min count: 500)
L1_NEON_CACH_DATA: (counter: 1, 2, 3, 4)
	NEON cacheable data access that hits L1 cache (min count: 500)
L2_NEON: (counter: 1, 2, 3, 4)
	L2 access as a result of NEON memory access (min count: 500)
L2_NEON_HIT: (counter: 1, 2, 3, 4)
	Any NEON hit in L2 cache (min count: 500)
L1_INST: (counter: 1, 2, 3, 4)
	Any L1 instruction cache access, excluding CP15 cache accesses (min count: 500)
PC_RETURN_MIS_PRED: (counter: 1, 2, 3, 4)
	Return stack misprediction at return stack pop (incorrect target address) (min count: 500)
PC_BRANCH_FAILED: (counter: 1, 2, 3, 4)
	Branch prediction misprediction (min count: 500)
PC_BRANCH_TAKEN: (counter: 1, 2, 3, 4)
	Any predicted branch that is taken (min count: 500)
PC_BRANCH_EXECUTED: (counter: 1, 2, 3, 4)
	Any taken branch that is executed (min count: 500)
OP_EXECUTED: (counter: 1, 2, 3, 4)
	Number of operations executed (in instruction or mutli-cycle instruction) (min count: 500)
CYCLES_INST_STALL: (counter: 1, 2, 3, 4)
	Cycles where no instruction available (min count: 500)
CYCLES_INST: (counter: 1, 2, 3, 4)
	Number of instructions issued in a cycle (min count: 500)
CYCLES_NEON_DATA_STALL: (counter: 1, 2, 3, 4)
	Number of cycles the processor waits on MRC data from NEON (min count: 500)
CYCLES_NEON_INST_STALL: (counter: 1, 2, 3, 4)
	Number of cycles the processor waits on NEON instruction queue or NEON load queue (min 
        count: 500)
NEON_CYCLES: (counter: 1, 2, 3, 4)
	Number of cycles NEON and integer processors are not idle (min count: 500)
PMU0_EVENTS: (counter: 1, 2, 3, 4)
	Number of events from external input source PMUEXTIN[0] (min count: 500)
PMU1_EVENTS: (counter: 1, 2, 3, 4)
	Number of events from external input source PMUEXTIN[1] (min count: 500)
PMU_EVENTS: (counter: 1, 2, 3, 4)
	Number of events from both external input sources PMUEXTIN[0] and PMUEXTIN[1] (min count: 
        500)
lucid@lucid-desktop:~/oprofile-0.9.7$ 
```
## profile script 360s ##
```
Tue Oct  4 03:12:31 CST 2011
CPU: ARM Cortex-A8, speed 1e+06 MHz (estimated)
Counted CPU_CYCLES events (Number of CPU cycles) with a unit mask of 0x00 (No unit mask) count 200000
Counted INSTR_EXECUTED events (All executed instructions) with a unit mask of 0x00 (No unit mask) count 200000
Counted L2_ACCESS events (Any access to L2 cache) with a unit mask of 0x00 (No unit mask) count 200000
Counted L2_CACH_MISS events (Any cacheable miss in L2 cache) with a unit mask of 0x00 (No unit mask) count 200000
CPU_CYCLES:200000|INSTR_EXECUTED...| L2_ACCESS:200000|L2_CACH_MISS:2...|
  samples|      %|  samples|      %|  samples|      %|  samples|      %|
------------------------------------------------------------------------
  1588124 98.1837    253523 96.3698      7565 94.6927      2059 94.2334 seti_boinc
	CPU_CYCLES:200000|INSTR_EXECUTED...| L2_ACCESS:200000|L2_CACH_MISS:2...|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	  1587793 99.9792    253299 99.9116      7563 99.9736      2058 99.9514 seti_boinc
	      331  0.0208       224  0.0884         2  0.0264         1  0.0486 [vectors] (tgid:12078 range:0xffff0000-0xffff1000)
     6677  0.4128      3052  1.1601       107  1.3393        66  3.0206 libc-2.11.1.so
     6045  0.3737      1444  0.5489        58  0.7260         8  0.3661 libxapian.so.15.6.9
     5854  0.3619       775  0.2946       145  1.8150        20  0.9153 python2.6
	CPU_CYCLES:200000|INSTR_EXECUTED...| L2_ACCESS:200000|L2_CACH_MISS:2...|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	     5516 94.2262       564 72.7742       141 97.2414        20 100.000 python2.6
	      338  5.7738       211 27.2258         4  2.7586         0       0 [vectors] (tgid:16290 range:0xffff0000-0xffff1000)
     4423  0.2734      2099  0.7979        39  0.4882         1  0.0458 oprofiled
	CPU_CYCLES:200000|INSTR_EXECUTED...| L2_ACCESS:200000|L2_CACH_MISS:2...|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	     4421 99.9548      2098 99.9524        39 100.000         1 100.000 oprofiled
	        2  0.0452         1  0.0476         0       0         0       0 [vectors] (tgid:17000 range:0xffff0000-0xffff1000)
     2236  0.1382       880  0.3345        26  0.3254         3  0.1373 libstdc++.so.6.0.13
     1226  0.0758       505  0.1920        15  0.1878        18  0.8238 libz.so.1.2.3.3
      755  0.0467       189  0.0718         8  0.1001         2  0.0915 ld-2.11.1.so
      659  0.0407       186  0.0707        10  0.1252         3  0.1373 libapt-pkg-libc6.10-6.so.4.8.0
      333  0.0206        37  0.0141         3  0.0376         1  0.0458 _xapian.so
      243  0.0150       202  0.0768         3  0.0376         0       0 libavahi-common.so.3.5.1
      219  0.0135        10  0.0038         3  0.0376         1  0.0458 apt_pkg.so
      179  0.0111        68  0.0258         1  0.0125         0       0 dash
	CPU_CYCLES:200000|INSTR_EXECUTED...| L2_ACCESS:200000|L2_CACH_MISS:2...|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	      176 98.3240        66 97.0588         1 100.000         0       0 dash
	        3  1.6760         2  2.9412         0       0         0       0 [vectors] (tgid:17159 range:0xffff0000-0xffff1000)
      151  0.0093        20  0.0076         2  0.0250         0       0 libavahi-core.so.6.0.1
      106  0.0066        14  0.0053         1  0.0125         1  0.0458 gawk
       99  0.0061         1 3.8e-04         2  0.0250         0       0 libpthread-2.11.1.so
       47  0.0029         3  0.0011         0       0         1  0.0458 ntpd
       37  0.0023        33  0.0125         0       0         0       0 ophelp
       28  0.0017        20  0.0076         0       0         0       0 avahi-daemon
	CPU_CYCLES:200000|INSTR_EXECUTED...| L2_ACCESS:200000|L2_CACH_MISS:2...|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	       23 82.1429        20 100.000         0       0         0       0 [vectors] (tgid:3312 range:0xffff0000-0xffff1000)
	        5 17.8571         0       0         0       0         0       0 avahi-daemon
       12 7.4e-04         1 3.8e-04         0       0         0       0 libgcc_s.so.1
        8 4.9e-04         1 3.8e-04         0       0         0       0 rsyslogd
        6 3.7e-04         1 3.8e-04         0       0         0       0 libpopt.so.0.0.0
        6 3.7e-04         1 3.8e-04         0       0         0       0 sudo
        5 3.1e-04         0       0         0       0         0       0 bash
        5 3.1e-04         3  0.0011         0       0         0       0 grep
        5 3.1e-04         2 7.6e-04         0       0         0       0 libdl-2.11.1.so
        3 1.9e-04         2 7.6e-04         1  0.0125         0       0 libm-2.11.1.so
        2 1.2e-04         1 3.8e-04         0       0         0       0 ls
        2 1.2e-04         0       0         0       0         1  0.0458 libcrypto.so.0.9.8
        1 6.2e-05         0       0         0       0         0       0 cat
        1 6.2e-05         0       0         0       0         0       0 mkdir
        1 6.2e-05         0       0         0       0         0       0 libnss_compat-2.11.1.so
        1 6.2e-05         0       0         0       0         0       0 pam_unix.so
        1 6.2e-05         0       0         0       0         0       0 seq
        1 6.2e-05         0       0         0       0         0       0 LC_CTYPE
        1 6.2e-05         0       0         0       0         0       0 cron
 
CPU: ARM Cortex-A8, speed 1e+06 MHz (estimated)
Counted CPU_CYCLES events (Number of CPU cycles) with a unit mask of 0x00 (No unit mask) count 200000
Counted INSTR_EXECUTED events (All executed instructions) with a unit mask of 0x00 (No unit mask) count 200000
Counted L2_ACCESS events (Any access to L2 cache) with a unit mask of 0x00 (No unit mask) count 200000
Counted L2_CACH_MISS events (Any cacheable miss in L2 cache) with a unit mask of 0x00 (No unit mask) count 200000
samples  %        samples  %        samples  %        samples  %        image name               symbol name
246430   15.5171  21904     8.6398  1904     25.1685  829      40.2623  seti_boinc               n1_32
219878   13.8451  31278    12.3373  1495     19.7621  6         0.2914  seti_boinc               sinl
195336   12.2998  28244    11.1406  63        0.8328  8         0.3885  seti_boinc               cosl
150774    9.4938  23572     9.2978  597       7.8916  89        4.3225  seti_boinc               t1_16
79191     4.9864  14048     5.5411  208       2.7495  183       8.8878  seti_boinc               v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
60342     3.7996  11148     4.3972  15        0.1983  2         0.0971  seti_boinc               n1_16
53332     3.3582  9779      3.8572  494       6.5301  125       6.0709  seti_boinc               n1_64
48399     3.0476  7636      3.0120  35        0.4627  1         0.0486  seti_boinc               q1_4
47439     2.9871  13721     5.4121  120       1.5863  4         0.1943  seti_boinc               rotate_sqrtn_table
42327     2.6652  5054      1.9935  234       3.0932  182       8.8392  seti_boinc               v_GetPowerSpectrum(float (*) [2], float*, int)
42116     2.6519  6035      2.3805  23        0.3040  0              0  seti_boinc               t1_4
40145     2.5278  5138      2.0266  320       4.2300  152       7.3822  seti_boinc               apply
37454     2.3584  1973      0.7782  467       6.1732  136       6.6051  seti_boinc               GetFixedPoT(float*, int, int, float*, int, int)
31280     1.9696  7818      3.0837  103       1.3615  43        2.0884  seti_boinc               FindSpikes(float*, int, int, SETI_WU_INFO&)
29164     1.8364  1557      0.6141  398       5.2611  90        4.3711  seti_boinc               analyze_pot(float*, int, ChirpFftPair_t&)
22350     1.4073  5484      2.1631  35        0.4627  0              0  seti_boinc               GaussFit(float*, int, int)
22221     1.3992  2974      1.1731  10        0.1322  0              0  seti_boinc               lcgf(double, double)
21437     1.3498  2841      1.1206  5         0.0661  0              0  seti_boinc               f_GetChiSq(float*, int, int, float, float, float*, float*)
19925     1.2546  5956      2.3493  4         0.0529  0              0  seti_boinc               floor
19183     1.2079  6101      2.4065  11        0.1454  0              0  seti_boinc               f_GetPeak(float*, int, int, float, float, float*)
18559     1.1686  2476      0.9766  3         0.0397  0              0  seti_boinc               sincos
15287     0.9626  6586      2.5978  14        0.1851  0              0  seti_boinc               f_GetTrueMean(float*, int, float, int, int)
14730     0.9275  3450      1.3608  34        0.4494  0              0  seti_boinc               __ieee754_log
14047     0.8845  2043      0.8058  84        1.1104  15        0.7285  seti_boinc               t1_32
13746     0.8655  1548      0.6106  41        0.5420  13        0.6314  seti_boinc               t1_8
11657     0.7340  2481      0.9786  39        0.5155  1         0.0486  seti_boinc               __ieee754_pow
8056      0.5073  4826      1.9036  376       4.9703  127       6.1680  seti_boinc               fftwf_cpy2d_pair
7428      0.4677  1227      0.4840  32        0.4230  0              0  seti_boinc               __exp1
6454      0.4064  2255      0.8895  40        0.5288  1         0.0486  seti_boinc               find_triplets(float const*, int, float, int, int)
5447      0.3430  1249      0.4927  13        0.1718  3         0.1457  seti_boinc               sw_sum3_t31(float**, PoTPlan*)
4829      0.3041  1091      0.4303  5         0.0661  0              0  seti_boinc               float_to_uchar(float*, unsigned char*, long, float)
4253      0.2678  1117      0.4406  2         0.0264  0              0  seti_boinc               sw_sum2_t31(float**, PoTPlan*)
3841      0.2419  844       0.3329  3         0.0397  0              0  seti_boinc               sw_sum4_t31(float**, PoTPlan*)
3331      0.2097  1654      0.6524  35        0.4627  2         0.0971  seti_boinc               t1_64
3249      0.2046  785       0.3096  2         0.0264  0              0  seti_boinc               sw_sum5_t31(float**, PoTPlan*)
3207      0.2019  832       0.3282  8         0.1058  0              0  seti_boinc               find_pulse(float const*, int, float, int, int)
3178      0.2001  349       0.1377  2         0.0264  0              0  seti_boinc               csloww1
1389      0.0875  994       0.3921  30        0.3966  1         0.0486  seti_boinc               _int_malloc
1358      0.0855  422       0.1665  7         0.0925  1         0.0486  seti_boinc               logl
1245      0.0784  623       0.2457  4         0.0529  1         0.0486  seti_boinc               powl
1033      0.0650  232       0.0915  1         0.0132  0              0  seti_boinc               fraction_done(double, double)
1022      0.0644  251       0.0990  16        0.2115  1         0.0486  seti_boinc               ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
833       0.0525  307       0.1211  26        0.3437  2         0.0971  seti_boinc               malloc
674       0.0424  149       0.0588  5         0.0661  0              0  seti_boinc               time_to_ra_dec(double, double*, double*)
658       0.0414  521       0.2055  18        0.2379  0              0  seti_boinc               _int_free
654       0.0412  62        0.0245  2         0.0264  1         0.0486  seti_boinc               __dubsin
620       0.0390  53        0.0209  3         0.0397  1         0.0486  seti_boinc               __dubcos
513       0.0323  108       0.0426  7         0.0925  0              0  seti_boinc               TripletProgressUnits()
503       0.0317  16        0.0063  10        0.1322  0              0  seti_boinc               boinc_fraction_done
502       0.0316  90        0.0355  1         0.0132  0              0  seti_boinc               PulseProgressUnits(double, int)
444       0.0280  265       0.1045  6         0.0793  0              0  seti_boinc               free
410       0.0258  133       0.0525  7         0.0925  0              0  seti_boinc               checkpoint(unsigned char)
331       0.0208  224       0.0884  2         0.0264  1         0.0486  [vectors] (tgid:12078 range:0xffff0000-0xffff1000) [vectors] (tgid:12078 range:0xffff0000-0xffff1000)
326       0.0205  78        0.0308  7         0.0925  1         0.0486  seti_boinc               apply
318       0.0200  123       0.0485  0              0  0              0  seti_boinc               isnanl
313       0.0197  50        0.0197  7         0.0925  1         0.0486  seti_boinc               apply_dit
288       0.0181  28        0.0110  1         0.0132  0              0  seti_boinc               csloww
286       0.0180  50        0.0197  2         0.0264  0              0  seti_boinc               calc_detection_freq(double, double, double)
257       0.0162  86        0.0339  19        0.2512  6         0.2914  seti_boinc               analysis_config::analysis_config()
234       0.0147  178       0.0702  0              0  0              0  seti_boinc               __divsi3
204       0.0128  71        0.0280  2         0.0264  0              0  seti_boinc               cnvt_bin_hz(int, int)
198       0.0125  82        0.0323  0              0  0              0  seti_boinc               apply
198       0.0125  39        0.0154  6         0.0793  1         0.0486  seti_boinc               apply
189       0.0119  96        0.0379  9         0.1190  0              0  seti_boinc               malloc_consolidate
179       0.0113  36        0.0142  7         0.0925  0              0  seti_boinc               GaussianProgressUnits()
179       0.0113  33        0.0130  7         0.0925  9         0.4371  seti_boinc               splitter_config::splitter_config()
149       0.0094  85        0.0335  7         0.0925  4         0.1943  seti_boinc               workunit_grp::workunit_grp()
144       0.0091  67        0.0264  5         0.0661  0              0  seti_boinc               gaussian::gaussian()
144       0.0091  105       0.0414  9         0.1190  2         0.0971  seti_boinc               operator new(unsigned int)
127       0.0080  61        0.0241  1         0.0132  0              0  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
117       0.0074  87        0.0343  1         0.0132  0              0  seti_boinc               GAUSS_INFO::~GAUSS_INFO()
113       0.0071  35        0.0138  4         0.0529  2         0.0971  seti_boinc               data_description_t::data_description_t()
112       0.0071  99        0.0390  2         0.0264  0              0  seti_boinc               __udivsi3
106       0.0067  26        0.0103  10        0.1322  5         0.2428  seti_boinc               tape::tape()
105       0.0066  22        0.0087  0              0  0              0  seti_boinc               finite
93        0.0059  19        0.0075  5         0.0661  1         0.0486  seti_boinc               result::result()
91        0.0057  35        0.0138  1         0.0132  0              0  seti_boinc               operator delete(void*)
76        0.0048  21        0.0083  3         0.0397  0              0  seti_boinc               recorder_config::recorder_config()
73        0.0046  0              0  0              0  0              0  seti_boinc               timer_handler()
68        0.0043  19        0.0075  4         0.0529  0              0  seti_boinc               workunit_header::workunit_header()
67        0.0042  31        0.0122  1         0.0132  0              0  seti_boinc               memset
67        0.0042  29        0.0114  0              0  0              0  seti_boinc               receiver_config::receiver_config()
62        0.0039  16        0.0063  1         0.0132  0              0  seti_boinc               apply_dif
61        0.0038  0              0  2         0.0264  0              0  seti_boinc               seti_analyze(ANALYSIS_STATE&)
59        0.0037  19        0.0075  3         0.0397  0              0  seti_boinc               boinc_time_to_checkpoint
56        0.0035  2        7.9e-04  0              0  0              0  seti_boinc               __libc_disable_asynccancel
55        0.0035  14        0.0055  3         0.0397  0              0  seti_boinc               apply
54        0.0034  26        0.0103  6         0.0793  2         0.0971  seti_boinc               subband_description_t::subband_description_t()
53        0.0033  2        7.9e-04  0              0  1         0.0486  seti_boinc               nanosleep
52        0.0033  23        0.0091  1         0.0132  0              0  seti_boinc               MFILE::MFILE()
50        0.0031  20        0.0079  4         0.0529  2         0.0971  seti_boinc               T.9822
48        0.0030  7         0.0028  0              0  0              0  seti_boinc               __docos
38        0.0024  37        0.0146  1         0.0132  0              0  seti_boinc               T.9826
33        0.0021  1        3.9e-04  0              0  0              0  seti_boinc               boinc_sleep(double)
32        0.0020  23        0.0091  0              0  0              0  seti_boinc               GAUSS_INFO::GAUSS_INFO()
31        0.0020  19        0.0075  1         0.0132  0              0  seti_boinc               MFILE::~MFILE()
30        0.0019  38        0.0150  0              0  0              0  seti_boinc               memcpy
28        0.0018  1        3.9e-04  2         0.0264  0              0  seti_boinc               __aeabi_read_tp
27        0.0017  2        7.9e-04  0              0  0              0  seti_boinc               log10l
26        0.0016  2        7.9e-04  0              0  0              0  seti_boinc               fmodl
26        0.0016  1        3.9e-04  0              0  0              0  seti_boinc               worker_signal_handler(int)
25        0.0016  1        3.9e-04  1         0.0132  0              0  seti_boinc               fftwf_execute_dft
23        0.0014  0              0  0              0  0              0  seti_boinc               SpikeProgressUnits(int)
23        0.0014  1        3.9e-04  0              0  0              0  seti_boinc               gettimeofday
21        0.0013  1        3.9e-04  0              0  0              0  seti_boinc               __ieee754_fmod
16        0.0010  1        3.9e-04  0              0  0              0  seti_boinc               SPIKE_INFO::~SPIKE_INFO()
16        0.0010  12        0.0047  0              0  0              0  seti_boinc               T.9827
16        0.0010  2        7.9e-04  0              0  0              0  seti_boinc               ____libc_disable_asynccancel_veneer
14       8.8e-04  0              0  0              0  0              0  seti_boinc               dtime()
14       8.8e-04  15        0.0059  0              0  0              0  seti_boinc               fftwf_cpy2d_pair_co
10       6.3e-04  0              0  0              0  0              0  seti_boinc               timer_thread(void*)
9        5.7e-04  0              0  0              0  0              0  seti_boinc               ____libc_enable_asynccancel_veneer
9        5.7e-04  0              0  0              0  0              0  seti_boinc               __libc_enable_asynccancel
9        5.7e-04  0              0  0              0  0              0  seti_boinc               getrusage
9        5.7e-04  8         0.0032  0              0  0              0  seti_boinc               memmove
9        5.7e-04  0              0  0              0  0              0  seti_boinc               usleep
8        5.0e-04  1        3.9e-04  0              0  0              0  seti_boinc               __default_sa_restorer_v2
8        5.0e-04  1        3.9e-04  1         0.0132  1         0.0486  seti_boinc               spike::spike()
7        4.4e-04  1        3.9e-04  0              0  0              0  seti_boinc               __ieee754_log10
5        3.1e-04  9         0.0035  0              0  0              0  seti_boinc               T.9831
3        1.9e-04  0              0  0              0  0              0  seti_boinc               boinc_worker_thread_cpu_time
3        1.9e-04  0              0  0              0  0              0  seti_boinc               fftwf_ifree
2        1.3e-04  0              0  0              0  0              0  seti_boinc               GetPulsePoTLen(long, int*, int*)
2        1.3e-04  0              0  0              0  0              0  seti_boinc               SPIKE_INFO::SPIKE_INFO()
2        1.3e-04  0              0  0              0  0              0  seti_boinc               fftwf_kernel_free
2        1.3e-04  0              0  0              0  0              0  seti_boinc               isinfl
1        6.3e-05  0              0  0              0  0              0  seti_boinc               PULSE_INFO::~PULSE_INFO()
1        6.3e-05  0              0  0              0  0              0  seti_boinc               ____strtoul_l_internal
1        6.3e-05  0              0  0              0  0              0  seti_boinc               boinc_ops_cumulative
1        6.3e-05  0              0  0              0  0              0  seti_boinc               calloc_a(unsigned int, unsigned int, unsigned int)
1        6.3e-05  0              0  0              0  0              0  seti_boinc               fftwf_malloc_plain
1        6.3e-05  0              0  0              0  0              0  seti_boinc               invert_lcgf(float, float, float)
0              0  1        3.9e-04  0              0  0              0  seti_boinc               hack_digit.11765
0              0  1        3.9e-04  0              0  0              0  seti_boinc               strncpy
 
 
Tue Oct  4 03:18:54 CST 2011
CPU: ARM Cortex-A8, speed 1e+06 MHz (estimated)
Counted PC_BRANCH_EXECUTED events (Any taken branch that is executed) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_BRANCH_MIS_PRED events (Branch mispredicted or not predicted. Counts pipeline flushes because of misprediction) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_BRANCH_MIS_USED events (Branch or change in program flow that could have been predicted) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_IMM_BRANCH events (Immediate branch instruction executed (taken or not)) with a unit mask of 0x00 (No unit mask) count 200000
PC_BRANCH_EXEC...|PC_BRANCH_MIS_...|PC_BRANCH_MIS_...|PC_IMM_BRANCH:...|
  samples|      %|  samples|      %|  samples|      %|  samples|      %|
------------------------------------------------------------------------
    15052 93.2301       607 74.4785     22213 92.6198     19672 93.1748 seti_boinc
	PC_BRANCH_EXEC...|PC_BRANCH_MIS_...|PC_BRANCH_MIS_...|PC_IMM_BRANCH:...|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	    15030 99.8538       606 99.8353     22181 99.8559     19644 99.8577 seti_boinc
	       22  0.1462         1  0.1647        32  0.1441        28  0.1423 [vectors] (tgid:12078 range:0xffff0000-0xffff1000)
      438  2.7129        49  6.0123       698  2.9104       615  2.9129 libc-2.11.1.so
      255  1.5794        63  7.7301       374  1.5594       276  1.3073 libxapian.so.15.6.9
      147  0.9105        28  3.4356       234  0.9757       150  0.7105 libstdc++.so.6.0.13
      114  0.7061        36  4.4172       188  0.7839       166  0.7862 python2.6
	PC_BRANCH_EXEC...|PC_BRANCH_MIS_...|PC_BRANCH_MIS_...|PC_IMM_BRANCH:...|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	       89 78.0702        33 91.6667       124 65.9574       116 69.8795 python2.6
	       25 21.9298         3  8.3333        64 34.0426        50 30.1205 [vectors] (tgid:16290 range:0xffff0000-0xffff1000)
       38  0.2354         8  0.9816        85  0.3544        92  0.4358 libz.so.1.2.3.3
       38  0.2354         8  0.9816        67  0.2794        40  0.1895 libapt-pkg-libc6.10-6.so.4.8.0
       23  0.1425         8  0.9816        54  0.2252        39  0.1847 ld-2.11.1.so
       13  0.0805         1  0.1227        22  0.0917        19  0.0900 oprofiled
        7  0.0434         1  0.1227        13  0.0542        12  0.0568 dash
	PC_BRANCH_EXEC...|PC_BRANCH_MIS_...|PC_BRANCH_MIS_...|PC_IMM_BRANCH:...|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	        6 85.7143         1 100.000        13 100.000        11 91.6667 dash
	        1 14.2857         0       0         0       0         1  8.3333 [vectors] (tgid:18635 range:0xffff0000-0xffff1000)
        5  0.0310         0       0        10  0.0417         8  0.0379 libavahi-common.so.3.5.1
        5  0.0310         1  0.1227         6  0.0250         7  0.0332 _xapian.so
        3  0.0186         0       0         7  0.0292         2  0.0095 ophelp
        2  0.0124         0       0         2  0.0083         5  0.0237 gawk
        2  0.0124         3  0.3681         0       0         1  0.0047 apt_pkg.so
        2  0.0124         0       0         1  0.0042         0       0 ntpd
        1  0.0062         1  0.1227         4  0.0167         2  0.0095 libavahi-core.so.6.0.1
        0       0         0       0         1  0.0042         2  0.0095 libgcc_s.so.1
        0       0         0       0         1  0.0042         1  0.0047 libpam.so.0.82.2
        0       0         1  0.1227         1  0.0042         1  0.0047 libpthread-2.11.1.so
        0       0         0       0         1  0.0042         1  0.0047 sudo
        0       0         0       0         0       0         1  0.0047 LC_COLLATE
        0       0         0       0         0       0         1  0.0047 avahi-daemon
	PC_BRANCH_EXEC...|PC_BRANCH_MIS_...|PC_BRANCH_MIS_...|PC_IMM_BRANCH:...|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	        0       0         0       0         0       0         1 100.000 [vectors] (tgid:3312 range:0xffff0000-0xffff1000)
        0       0         0       0         1  0.0042         0       0 rsyslogd
 
CPU: ARM Cortex-A8, speed 1e+06 MHz (estimated)
Counted PC_BRANCH_EXECUTED events (Any taken branch that is executed) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_BRANCH_MIS_PRED events (Branch mispredicted or not predicted. Counts pipeline flushes because of misprediction) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_BRANCH_MIS_USED events (Branch or change in program flow that could have been predicted) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_IMM_BRANCH events (Immediate branch instruction executed (taken or not)) with a unit mask of 0x00 (No unit mask) count 200000
samples  %        samples  %        samples  %        samples  %        image name               symbol name
2277     15.1276  5         0.8237  2678     12.0560  1767      8.9823  seti_boinc               v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
2205     14.6492  166      27.3476  3671     16.5264  3433     17.4512  seti_boinc               cosl
2108     14.0048  126      20.7578  3828     17.2332  3746     19.0423  seti_boinc               sinl
1068      7.0954  1         0.1647  1608      7.2390  1611      8.1893  seti_boinc               FindSpikes(float*, int, int, SETI_WU_INFO&)
843       5.6006  1         0.1647  830       3.7366  234       1.1895  seti_boinc               rotate_sqrtn_table
811       5.3880  44        7.2488  867       3.9031  941       4.7834  seti_boinc               f_GetTrueMean(float*, int, float, int, int)
663       4.4047  3         0.4942  990       4.4568  972       4.9410  seti_boinc               sincos
521       3.4613  0              0  541       2.4355  548       2.7857  seti_boinc               v_GetPowerSpectrum(float (*) [2], float*, int)
441       2.9298  13        2.1417  503       2.2644  358       1.8198  seti_boinc               GaussFit(float*, int, int)
415       2.7571  0              0  551       2.4805  533       2.7094  seti_boinc               f_GetPeak(float*, int, int, float, float, float*)
353       2.3452  4         0.6590  566       2.5481  529       2.6891  seti_boinc               fftwf_cpy2d_pair
345       2.2921  1         0.1647  1268      5.7084  1307      6.6440  seti_boinc               floor
276       1.8336  12        1.9769  303       1.3641  313       1.5911  seti_boinc               find_triplets(float const*, int, float, int, int)
268       1.7805  1         0.1647  433       1.9493  332       1.6877  seti_boinc               apply
196       1.3022  13        2.1417  271       1.2200  289       1.4691  seti_boinc               __ieee754_log
180       1.1959  13        2.1417  197       0.8869  126       0.6405  seti_boinc               powl
177       1.1759  11        1.8122  209       0.9409  197       1.0014  seti_boinc               analyze_pot(float*, int, ChirpFftPair_t&)
174       1.1560  7         1.1532  250       1.1255  263       1.3369  seti_boinc               GetFixedPoT(float*, int, int, float*, int, int)
131       0.8703  1         0.1647  116       0.5222  129       0.6558  seti_boinc               f_GetChiSq(float*, int, int, float, float, float*, float*)
110       0.7308  1         0.1647  125       0.5627  117       0.5948  seti_boinc               float_to_uchar(float*, unsigned char*, long, float)
102       0.6777  7         1.1532  209       0.9409  154       0.7828  seti_boinc               lcgf(double, double)
101       0.6710  7         1.1532  127       0.5717  88        0.4473  seti_boinc               find_pulse(float const*, int, float, int, int)
99        0.6577  9         1.4827  232       1.0444  233       1.1844  seti_boinc               __ieee754_pow
87        0.5780  22        3.6244  196       0.8824  204       1.0370  seti_boinc               _int_malloc
82        0.5448  1         0.1647  95        0.4277  107       0.5439  seti_boinc               t1_4
78        0.5182  11        1.8122  108       0.4862  77        0.3914  seti_boinc               sw_sum3_t31(float**, PoTPlan*)
51        0.3388  0              0  72        0.3241  43        0.2186  seti_boinc               logl
50        0.3322  8         1.3180  55        0.2476  46        0.2338  seti_boinc               sw_sum5_t31(float**, PoTPlan*)
49        0.3255  3         0.4942  164       0.7383  109       0.5541  seti_boinc               _int_free
45        0.2990  1         0.1647  71        0.3196  66        0.3355  seti_boinc               __exp1
45        0.2990  17        2.8007  96        0.4322  62        0.3152  seti_boinc               sw_sum4_t31(float**, PoTPlan*)
44        0.2923  0              0  41        0.1846  37        0.1881  seti_boinc               n1_16
42        0.2790  15        2.4712  59        0.2656  37        0.1881  seti_boinc               sw_sum2_t31(float**, PoTPlan*)
36        0.2392  1         0.1647  41        0.1846  31        0.1576  seti_boinc               t1_16
34        0.2259  7         1.1532  72        0.3241  83        0.4219  seti_boinc               free
33        0.2192  0              0  31        0.1396  23        0.1169  seti_boinc               q1_4
31        0.2060  0              0  27        0.1216  19        0.0966  seti_boinc               fraction_done(double, double)
31        0.2060  0              0  27        0.1216  3         0.0153  seti_boinc               isnanl
30        0.1993  10        1.6474  53        0.2386  54        0.2745  seti_boinc               __divsi3
29        0.1927  0              0  30        0.1351  24        0.1220  seti_boinc               TripletProgressUnits()
28        0.1860  0              0  66        0.2971  50        0.2542  seti_boinc               malloc
24        0.1594  1         0.1647  32        0.1441  25        0.1271  seti_boinc               time_to_ra_dec(double, double*, double*)
23        0.1528  5         0.8237  39        0.1756  32        0.1627  seti_boinc               checkpoint(unsigned char)
23        0.1528  1         0.1647  18        0.0810  13        0.0661  seti_boinc               n1_32
22        0.1462  1         0.1647  32        0.1441  28        0.1423  [vectors] (tgid:12078 range:0xffff0000-0xffff1000) [vectors] (tgid:12078 range:0xffff0000-0xffff1000)
19        0.1262  3         0.4942  22        0.0990  24        0.1220  seti_boinc               csloww1
16        0.1063  1         0.1647  18        0.0810  13        0.0661  seti_boinc               PulseProgressUnits(double, int)
15        0.0997  9         1.4827  23        0.1035  10        0.0508  seti_boinc               ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
13        0.0864  6         0.9885  29        0.1306  20        0.1017  seti_boinc               malloc_consolidate
13        0.0864  0              0  11        0.0495  6         0.0305  seti_boinc               receiver_config::receiver_config()
11        0.0731  2         0.3295  29        0.1306  29        0.1474  seti_boinc               __udivsi3
10        0.0664  0              0  20        0.0900  6         0.0305  seti_boinc               GAUSS_INFO::~GAUSS_INFO()
10        0.0664  0              0  14        0.0630  3         0.0153  seti_boinc               apply
10        0.0664  1         0.1647  13        0.0585  3         0.0153  seti_boinc               apply_dit
10        0.0664  1         0.1647  7         0.0315  8         0.0407  seti_boinc               boinc_time_to_checkpoint
10        0.0664  2         0.3295  11        0.0495  10        0.0508  seti_boinc               cnvt_bin_hz(int, int)
9         0.0598  0              0  5         0.0225  4         0.0203  seti_boinc               boinc_fraction_done
8         0.0531  1         0.1647  18        0.0810  4         0.0203  seti_boinc               apply
8         0.0531  0              0  17        0.0765  9         0.0458  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
7         0.0465  0              0  10        0.0450  6         0.0305  seti_boinc               t1_8
6         0.0399  0              0  3         0.0135  2         0.0102  seti_boinc               GAUSS_INFO::GAUSS_INFO()
6         0.0399  2         0.3295  1         0.0045  3         0.0153  seti_boinc               __dubcos
6         0.0399  1         0.1647  6         0.0270  3         0.0153  seti_boinc               gaussian::gaussian()
6         0.0399  2         0.3295  13        0.0585  11        0.0559  seti_boinc               memset
6         0.0399  0              0  2         0.0090  1         0.0051  seti_boinc               n1_64
6         0.0399  1         0.1647  8         0.0360  5         0.0254  seti_boinc               workunit_grp::workunit_grp()
5         0.0332  0              0  12        0.0540  7         0.0356  seti_boinc               T.9826
5         0.0332  0              0  5         0.0225  5         0.0254  seti_boinc               analysis_config::analysis_config()
5         0.0332  2         0.3295  24        0.1080  10        0.0508  seti_boinc               operator delete(void*)
4         0.0266  0              0  3         0.0135  5         0.0254  seti_boinc               csloww
4         0.0266  0              0  19        0.0855  11        0.0559  seti_boinc               operator new(unsigned int)
3         0.0199  2         0.3295  9         0.0405  3         0.0153  seti_boinc               GaussianProgressUnits()
3         0.0199  0              0  1         0.0045  1         0.0051  seti_boinc               MFILE::~MFILE()
3         0.0199  4         0.6590  9         0.0405  5         0.0254  seti_boinc               apply
3         0.0199  0              0  2         0.0090  1         0.0051  seti_boinc               calc_detection_freq(double, double, double)
3         0.0199  0              0  3         0.0135  0              0  seti_boinc               recorder_config::recorder_config()
3         0.0199  0              0  0              0  0              0  seti_boinc               workunit_header::workunit_header()
2         0.0133  1         0.1647  5         0.0225  2         0.0102  seti_boinc               MFILE::MFILE()
2         0.0133  1         0.1647  4         0.0180  0              0  seti_boinc               apply_dif
2         0.0133  0              0  2         0.0090  8         0.0407  seti_boinc               data_description_t::data_description_t()
2         0.0133  1         0.1647  0              0  2         0.0102  seti_boinc               memmove
2         0.0133  1         0.1647  3         0.0135  1         0.0051  seti_boinc               result::result()
2         0.0133  4         0.6590  2         0.0090  1         0.0051  seti_boinc               splitter_config::splitter_config()
2         0.0133  1         0.1647  2         0.0090  1         0.0051  seti_boinc               subband_description_t::subband_description_t()
1         0.0066  0              0  0              0  1         0.0051  seti_boinc               SPIKE_INFO::~SPIKE_INFO()
1         0.0066  0              0  3         0.0135  8         0.0407  seti_boinc               T.9822
1         0.0066  0              0  1         0.0045  1         0.0051  seti_boinc               __docos
1         0.0066  4         0.6590  4         0.0180  6         0.0305  seti_boinc               __dubsin
1         0.0066  0              0  0              0  0              0  seti_boinc               __mpn_mul_1
1         0.0066  0              0  0              0  0              0  seti_boinc               dtime()
1         0.0066  0              0  1         0.0045  1         0.0051  seti_boinc               fftwf_cpy2d_pair_co
1         0.0066  0              0  2         0.0090  2         0.0102  seti_boinc               finite
1         0.0066  1         0.1647  2         0.0090  4         0.0203  seti_boinc               memcpy
1         0.0066  0              0  0              0  3         0.0153  seti_boinc               t1_32
1         0.0066  0              0  0              0  1         0.0051  seti_boinc               t1_64
0              0  0              0  4         0.0180  4         0.0203  seti_boinc               T.9827
0              0  0              0  6         0.0270  2         0.0102  seti_boinc               T.9831
0              0  0              0  1         0.0045  0              0  seti_boinc               __aeabi_read_tp
0              0  1         0.1647  0              0  0              0  seti_boinc               __default_sa_restorer_v2
0              0  1         0.1647  3         0.0135  1         0.0051  seti_boinc               apply
0              0  0              0  1         0.0045  0              0  seti_boinc               fftwf_kernel_malloc
0              0  0              0  0              0  1         0.0051  seti_boinc               gettimeofday
0              0  0              0  1         0.0045  0              0  seti_boinc               log10l
0              0  0              0  0              0  1         0.0051  seti_boinc               memchr
0              0  0              0  1         0.0045  0              0  seti_boinc               seti_analyze(ANALYSIS_STATE&)
0              0  1         0.1647  0              0  0              0  seti_boinc               timer_handler()
 
 
Tue Oct  4 03:25:16 CST 2011
CPU: ARM Cortex-A8, speed 1e+06 MHz (estimated)
Counted CYCLES_INST_STALL events (Cycles where no instruction available) with a unit mask of 0x00 (No unit mask) count 200000
Counted CYCLES_NEON_DATA_STALL events (Number of cycles the processor waits on MRC data from NEON) with a unit mask of 0x00 (No unit mask) count 200000
Counted DTLB_REFILL events (Data R/W that causes a TLB refill) with a unit mask of 0x00 (No unit mask) count 200000
Counted ITLB_MISS events (Instruction fetch misses from TLB) with a unit mask of 0x00 (No unit mask) count 200000
CYCLES_INST_ST...|CYCLES_NEON_DA...|DTLB_REFILL:20...| ITLB_MISS:200000|
  samples|      %|  samples|      %|  samples|      %|  samples|      %|
------------------------------------------------------------------------
    13082 69.5666    771699 99.9997      1222 93.5681        12 52.1739 seti_boinc
	CYCLES_INST_ST...|CYCLES_NEON_DA...|DTLB_REFILL:20...| ITLB_MISS:200000|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	    13025 99.5643    771699 100.000      1222 100.000        12 100.000 seti_boinc
	       57  0.4357         0       0         0       0         0       0 [vectors] (tgid:12078 range:0xffff0000-0xffff1000)
     1903 10.1196         0       0        24  1.8377         4 17.3913 python2.6
	CYCLES_INST_ST...|CYCLES_NEON_DA...|DTLB_REFILL:20...| ITLB_MISS:200000|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	     1864 97.9506         0       0        24 100.000         4 100.000 python2.6
	       39  2.0494         0       0         0       0         0       0 [vectors] (tgid:16290 range:0xffff0000-0xffff1000)
     1161  6.1739         0       0        18  1.3783         3 13.0435 libc-2.11.1.so
      911  4.8445         1 1.3e-04        29  2.2205         2  8.6957 libxapian.so.15.6.9
      417  2.2175         0       0         5  0.3828         0       0 libstdc++.so.6.0.13
      280  1.4890         0       0         3  0.2297         0       0 libapt-pkg-libc6.10-6.so.4.8.0
      240  1.2763         0       0         2  0.1531         0       0 libz.so.1.2.3.3
      208  1.1061         1 1.3e-04         0       0         2  8.6957 _xapian.so
      168  0.8934         0       0         1  0.0766         0       0 ld-2.11.1.so
      125  0.6647         0       0         1  0.0766         0       0 apt_pkg.so
       66  0.3510         0       0         0       0         0       0 dash
       62  0.3297         0       0         1  0.0766         0       0 libpthread-2.11.1.so
       45  0.2393         0       0         0       0         0       0 gawk
       30  0.1595         0       0         0       0         0       0 oprofiled
	CYCLES_INST_ST...|CYCLES_NEON_DA...|DTLB_REFILL:20...| ITLB_MISS:200000|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	       29 96.6667         0       0         0       0         0       0 oprofiled
	        1  3.3333         0       0         0       0         0       0 [vectors] (tgid:19948 range:0xffff0000-0xffff1000)
       18  0.0957         0       0         0       0         0       0 libavahi-common.so.3.5.1
       17  0.0904         0       0         0       0         0       0 ntpd
       15  0.0798         0       0         0       0         0       0 libgcc_s.so.1
       11  0.0585         0       0         0       0         0       0 libavahi-core.so.6.0.1
        9  0.0479         0       0         0       0         0       0 libm-2.11.1.so
        6  0.0319         0       0         0       0         0       0 grep
        6  0.0319         0       0         0       0         0       0 ophelp
        5  0.0266         0       0         0       0         0       0 libdl-2.11.1.so
        3  0.0160         0       0         0       0         0       0 sudo
	CYCLES_INST_ST...|CYCLES_NEON_DA...|DTLB_REFILL:20...| ITLB_MISS:200000|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	        2 66.6667         0       0         0       0         0       0 sudo
	        1 33.3333         0       0         0       0         0       0 [vectors] (tgid:20107 range:0xffff0000-0xffff1000)
        2  0.0106         0       0         0       0         0       0 libpopt.so.0.0.0
        2  0.0106         0       0         0       0         0       0 libselinux.so.1
        2  0.0106         0       0         0       0         0       0 seq
        2  0.0106         0       0         0       0         0       0 rsyslogd
	CYCLES_INST_ST...|CYCLES_NEON_DA...|DTLB_REFILL:20...| ITLB_MISS:200000|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	        1 50.0000         0       0         0       0         0       0 rsyslogd
	        1 50.0000         0       0         0       0         0       0 [vectors] (tgid:3136 range:0xffff0000-0xffff1000)
        2  0.0106         0       0         0       0         0       0 sshd
        1  0.0053         0       0         0       0         0       0 bash
        1  0.0053         0       0         0       0         0       0 ls
        1  0.0053         0       0         0       0         0       0 mkdir
        1  0.0053         0       0         0       0         0       0 libcrypto.so.0.9.8
        1  0.0053         0       0         0       0         0       0 libnss_nis-2.11.1.so
        1  0.0053         0       0         0       0         0       0 libpam.so.0.82.2
        1  0.0053         0       0         0       0         0       0 avahi-daemon
	CYCLES_INST_ST...|CYCLES_NEON_DA...|DTLB_REFILL:20...| ITLB_MISS:200000|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	        1 100.000         0       0         0       0         0       0 [vectors] (tgid:3312 range:0xffff0000-0xffff1000)
 
CPU: ARM Cortex-A8, speed 1e+06 MHz (estimated)
Counted CYCLES_INST_STALL events (Cycles where no instruction available) with a unit mask of 0x00 (No unit mask) count 200000
Counted CYCLES_NEON_DATA_STALL events (Number of cycles the processor waits on MRC data from NEON) with a unit mask of 0x00 (No unit mask) count 200000
Counted DTLB_REFILL events (Data R/W that causes a TLB refill) with a unit mask of 0x00 (No unit mask) count 200000
Counted ITLB_MISS events (Instruction fetch misses from TLB) with a unit mask of 0x00 (No unit mask) count 200000
samples  %        samples  %        samples  %        samples  %        image name               symbol name
1750     13.3772  159039   20.6089  5         0.4092  0              0  seti_boinc               cosl
1517     11.5961  144520   18.7275  3         0.2455  0              0  seti_boinc               sinl
1059      8.0951  6133      0.7947  63        5.1555  0              0  seti_boinc               n1_64
722       5.5190  24672     3.1971  6         0.4910  0              0  seti_boinc               t1_16
668       5.1063  16628     2.1547  355      29.0507  0              0  seti_boinc               n1_32
464       3.5469  16090     2.0850  3         0.2455  0              0  seti_boinc               sw_sum2_t31(float**, PoTPlan*)
312       2.3850  24308     3.1499  4         0.3273  0              0  seti_boinc               f_GetChiSq(float*, int, int, float, float, float*, float*)
293       2.2397  13706     1.7761  28        2.2913  1         8.3333  seti_boinc               __ieee754_log
290       2.2168  8322      1.0784  4         0.3273  0              0  seti_boinc               f_GetTrueMean(float*, int, float, int, int)
280       2.1403  37645     4.8782  5         0.4092  0              0  seti_boinc               q1_4
249       1.9034  3071      0.3980  0              0  0              0  seti_boinc               t1_64
241       1.8422  53749     6.9650  0              0  0              0  seti_boinc               v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
224       1.7123  8349      1.0819  1         0.0818  0              0  seti_boinc               sw_sum4_t31(float**, PoTPlan*)
218       1.6664  0              0  15        1.2275  1         8.3333  seti_boinc               _int_malloc
206       1.5747  17575     2.2774  1         0.0818  0              0  seti_boinc               n1_16
193       1.4753  19546     2.5329  16        1.3093  0              0  seti_boinc               GaussFit(float*, int, int)
179       1.3683  9214      1.1940  145      11.8658  0              0  seti_boinc               analyze_pot(float*, int, ChirpFftPair_t&)
169       1.2919  31325     4.0592  0              0  0              0  seti_boinc               v_GetPowerSpectrum(float (*) [2], float*, int)
166       1.2689  15358     1.9902  1         0.0818  1         8.3333  seti_boinc               FindSpikes(float*, int, int, SETI_WU_INFO&)
165       1.2613  6872      0.8905  25        2.0458  1         8.3333  seti_boinc               __ieee754_pow
157       1.2001  24313     3.1506  2         0.1637  0              0  seti_boinc               lcgf(double, double)
151       1.1543  0              0  15        1.2275  0              0  seti_boinc               malloc
149       1.1390  33193     4.3013  2         0.1637  0              0  seti_boinc               t1_4
133       1.0167  1405      0.1821  23        1.8822  0              0  seti_boinc               t1_32
131       1.0014  4926      0.6383  24        1.9640  0              0  seti_boinc               find_triplets(float const*, int, float, int, int)
128       0.9784  6729      0.8720  13        1.0638  0              0  seti_boinc               sw_sum3_t31(float**, PoTPlan*)
127       0.9708  233       0.0302  0              0  0              0  seti_boinc               __dubcos
127       0.9708  7201      0.9331  2         0.1637  0              0  seti_boinc               sw_sum5_t31(float**, PoTPlan*)
104       0.7950  0              0  4         0.3273  0              0  seti_boinc               _int_free
96        0.7338  8759      1.1350  148      12.1113  1         8.3333  seti_boinc               GetFixedPoT(float*, int, int, float*, int, int)
95        0.7262  2        2.6e-04  3         0.2455  0              0  seti_boinc               free
93        0.7109  0              0  2         0.1637  0              0  seti_boinc               checkpoint(unsigned char)
91        0.6956  630       0.0816  0              0  0              0  seti_boinc               powl
87        0.6650  4272      0.5536  8         0.6547  0              0  seti_boinc               find_pulse(float const*, int, float, int, int)
82        0.6268  0              0  0              0  0              0  seti_boinc               __divsi3
81        0.6192  269       0.0349  0              0  0              0  seti_boinc               __dubsin
77        0.5886  6743      0.8738  21        1.7185  0              0  seti_boinc               __exp1
74        0.5657  587       0.0761  6         0.4910  1         8.3333  seti_boinc               ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
72        0.5504  4513      0.5848  2         0.1637  0              0  seti_boinc               t1_8
67        0.5122  1984      0.2571  1         0.0818  0              0  seti_boinc               csloww1
67        0.5122  5423      0.7027  0              0  0              0  seti_boinc               top_sum3(float**, PoTPlan*)
57        0.4357  0              0  0              0  0              0  [vectors] (tgid:12078 range:0xffff0000-0xffff1000) [vectors] (tgid:12078 range:0xffff0000-0xffff1000)
56        0.4281  15        0.0019  0              0  0              0  seti_boinc               apply
56        0.4281  0              0  2         0.1637  1         8.3333  seti_boinc               workunit_grp::workunit_grp()
54        0.4128  8443      1.0941  2         0.1637  0              0  seti_boinc               f_GetPeak(float*, int, int, float, float, float*)
50        0.3822  0              0  0              0  0              0  seti_boinc               apply_dit
50        0.3822  14149     1.8335  4         0.3273  0              0  seti_boinc               floor
49        0.3746  11510     1.4915  0              0  0              0  seti_boinc               sincos
46        0.3516  4        5.2e-04  2         0.1637  0              0  seti_boinc               apply
42        0.3211  534       0.0692  4         0.3273  0              0  seti_boinc               time_to_ra_dec(double, double*, double*)
37        0.2828  905       0.1173  6         0.4910  0              0  seti_boinc               logl
36        0.2752  188       0.0244  0              0  0              0  seti_boinc               csloww
32        0.2446  0              0  80        6.5466  0              0  seti_boinc               apply
32        0.2446  100       0.0130  2         0.1637  0              0  seti_boinc               cnvt_bin_hz(int, int)
32        0.2446  0              0  3         0.2455  1         8.3333  seti_boinc               malloc_consolidate
30        0.2293  5058      0.6554  2         0.1637  0              0  seti_boinc               float_to_uchar(float*, unsigned char*, long, float)
28        0.2140  909       0.1178  0              0  0              0  seti_boinc               fraction_done(double, double)
28        0.2140  5        6.5e-04  0              0  0              0  seti_boinc               operator delete(void*)
26        0.1987  30        0.0039  4         0.3273  0              0  seti_boinc               GaussianProgressUnits()
26        0.1987  0              0  0              0  0              0  seti_boinc               __ieee754_fmod
26        0.1987  0              0  1         0.0818  0              0  seti_boinc               __udivsi3
24        0.1835  9         0.0012  0              0  0              0  seti_boinc               __docos
24        0.1835  0              0  0              0  2        16.6667  seti_boinc               gaussian::gaussian()
24        0.1835  10        0.0013  0              0  0              0  seti_boinc               seti_analyze(ANALYSIS_STATE&)
23        0.1758  0              0  0              0  0              0  seti_boinc               memset
23        0.1758  0              0  1         0.0818  0              0  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
22        0.1682  0              0  0              0  0              0  seti_boinc               __libc_disable_asynccancel
21        0.1605  0              0  2         0.1637  0              0  seti_boinc               recorder_config::recorder_config()
21        0.1605  0              0  1         0.0818  0              0  seti_boinc               result::result()
21        0.1605  1347      0.1745  0              0  0              0  seti_boinc               top_sum4(float**, PoTPlan*)
19        0.1452  1        1.3e-04  0              0  0              0  seti_boinc               boinc_sleep(double)
19        0.1452  41        0.0053  0              0  0              0  seti_boinc               isnanl
19        0.1452  0              0  0              0  2        16.6667  seti_boinc               operator new(unsigned int)
18        0.1376  563       0.0730  0              0  0              0  seti_boinc               PulseProgressUnits(double, int)
18        0.1376  0              0  0              0  0              0  seti_boinc               boinc_time_to_checkpoint
18        0.1376  0              0  21        1.7185  0              0  seti_boinc               rotate_sqrtn_table
18        0.1376  0              0  0              0  0              0  seti_boinc               splitter_config::splitter_config()
16        0.1223  0              0  0              0  0              0  seti_boinc               memcpy
16        0.1223  0              0  1         0.0818  0              0  seti_boinc               timer_handler()
15        0.1147  91        0.0118  10        0.8183  0              0  seti_boinc               TripletProgressUnits()
15        0.1147  42        0.0054  0              0  0              0  seti_boinc               apply
15        0.1147  0              0  2         0.1637  0              0  seti_boinc               tape::tape()
14        0.1070  0              0  0              0  0              0  seti_boinc               apply
13        0.0994  0              0  0              0  0              0  seti_boinc               MFILE::MFILE()
13        0.0994  0              0  0              0  0              0  seti_boinc               __aeabi_read_tp
13        0.0994  2        2.6e-04  0              0  0              0  seti_boinc               __ieee754_log10
13        0.0994  0              0  1         0.0818  0              0  seti_boinc               apply_dif
13        0.0994  0              0  0              0  0              0  seti_boinc               data_description_t::data_description_t()
13        0.0994  0              0  0              0  0              0  seti_boinc               workunit_header::workunit_header()
12        0.0917  0              0  0              0  0              0  seti_boinc               receiver_config::receiver_config()
11        0.0841  4        5.2e-04  0              0  0              0  seti_boinc               log10l
10        0.0764  132       0.0171  1         0.0818  0              0  seti_boinc               calc_detection_freq(double, double, double)
10        0.0764  0              0  98        8.0196  0              0  seti_boinc               fftwf_cpy2d_pair
10        0.0764  0              0  0              0  0              0  seti_boinc               getrusage
9         0.0688  10        0.0013  0              0  0              0  seti_boinc               SpikeProgressUnits(int)
9         0.0688  0              0  0              0  0              0  seti_boinc               subband_description_t::subband_description_t()
9         0.0688  0              0  0              0  0              0  seti_boinc               timer_thread(void*)
8         0.0612  0              0  0              0  0              0  seti_boinc               T.9822
8         0.0612  0              0  0              0  0              0  seti_boinc               __libc_enable_asynccancel
8         0.0612  140       0.0181  15        1.2275  0              0  seti_boinc               boinc_fraction_done
8         0.0612  0              0  0              0  0              0  seti_boinc               spike::spike()
7         0.0535  10        0.0013  1         0.0818  0              0  seti_boinc               GAUSS_INFO::~GAUSS_INFO()
7         0.0535  0              0  0              0  0              0  seti_boinc               fftwf_cpy2d_pair_co
7         0.0535  0              0  0              0  0              0  seti_boinc               fftwf_execute_dft
7         0.0535  0              0  0              0  0              0  seti_boinc               usleep
7         0.0535  0              0  0              0  0              0  seti_boinc               worker_signal_handler(int)
6         0.0459  0              0  0              0  0              0  seti_boinc               GAUSS_INFO::GAUSS_INFO()
6         0.0459  0              0  0              0  0              0  seti_boinc               T.9826
6         0.0459  0              0  0              0  0              0  seti_boinc               T.9827
6         0.0459  0              0  0              0  0              0  seti_boinc               fmodl
6         0.0459  0              0  0              0  0              0  seti_boinc               gettimeofday
6         0.0459  0              0  0              0  0              0  seti_boinc               nanosleep
5         0.0382  0              0  0              0  0              0  seti_boinc               SPIKE_INFO::SPIKE_INFO()
5         0.0382  1        1.3e-04  0              0  0              0  seti_boinc               SPIKE_INFO::~SPIKE_INFO()
5         0.0382  0              0  0              0  0              0  seti_boinc               ____libc_disable_asynccancel_veneer
5         0.0382  0              0  0              0  0              0  seti_boinc               analysis_config::analysis_config()
5         0.0382  6        7.8e-04  0              0  0              0  seti_boinc               dtime()
4         0.0306  0              0  0              0  0              0  seti_boinc               isinfl
3         0.0229  0              0  0              0  0              0  seti_boinc               MFILE::~MFILE()
3         0.0229  0              0  0              0  0              0  seti_boinc               __default_sa_restorer_v2
2         0.0153  6        7.8e-04  0              0  0              0  seti_boinc               ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
2         0.0153  0              0  0              0  0              0  seti_boinc               fftwf_malloc
2         0.0153  129       0.0167  0              0  0              0  seti_boinc               finite
2         0.0153  0              0  0              0  0              0  seti_boinc               memmove
1         0.0076  0              0  0              0  0              0  seti_boinc               PULSE_INFO::PULSE_INFO()
1         0.0076  0              0  0              0  0              0  seti_boinc               PULSE_INFO::~PULSE_INFO()
1         0.0076  0              0  0              0  0              0  seti_boinc               _IO_new_file_xsputn
1         0.0076  0              0  0              0  0              0  seti_boinc               ____libc_enable_asynccancel_veneer
1         0.0076  0              0  0              0  0              0  seti_boinc               __aeabi_uidivmod
1         0.0076  0              0  0              0  0              0  seti_boinc               fftwf_ifree
1         0.0076  0              0  0              0  0              0  seti_boinc               fftwf_kernel_malloc
1         0.0076  0              0  0              0  0              0  seti_boinc               fftwf_malloc_plain
0              0  1        1.3e-04  0              0  0              0  seti_boinc               boinc_worker_thread_cpu_time
 
 
```