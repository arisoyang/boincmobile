# SETI on Cortex-A9 #

```
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted CPU_CYCLES events (Number of CPU cycles) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_BRANCH_MIS_PRED events (Branch mispredicted or not predicted. Counts pipeline flushes because of misprediction) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_BRANCH_MIS_USED events (Branch or change in program flow that could have been predicted) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_IMM_BRANCH events (Immediate branch instruction executed (taken or not)) with a unit mask of 0x00 (No unit mask) count 200000
CPU_CYCLES:200000|PC_BRANCH_MIS_...|PC_BRANCH_MIS_...|PC_IMM_BRANCH:...|
  samples|      %|  samples|      %|  samples|      %|  samples|      %|
------------------------------------------------------------------------
  2620605 96.1471      4741 81.2371    136854 94.4518    124715 94.9472 seti_boinc
    75897  2.7846       779 13.3482      4415  3.0471      3473  2.6440 no-vmlinux
     9453  0.3468       115  1.9705      1366  0.9428      1214  0.9242 libc-2.13.so
     4921  0.1805        20  0.3427       835  0.5763       713  0.5428 oprofiled
     4535  0.1664        61  1.0452       543  0.3748       444  0.3380 python2.7
     2710  0.0994        30  0.5141       200  0.1380       208  0.1584 ld-2.13.so
     1923  0.0706        27  0.4626       165  0.1139       149  0.1134 bash
     1329  0.0488         0       0        24  0.0166        20  0.0152 libcrypt-2.13.so
      644  0.0236        11  0.1885       118  0.0814       101  0.0769 dpkg-query
      548  0.0201         7  0.1199        53  0.0366        46  0.0350 libcrypto.so.0.9.8
      300  0.0110         2  0.0343        19  0.0131        19  0.0145 libglib-2.0.so.0.2800.6
      261  0.0096         0       0        23  0.0159        21  0.0160 libpthread-2.13.so
      188  0.0069         9  0.1542        29  0.0200        15  0.0114 libstdc++.so.6.0.14
      164  0.0060         6  0.1028        18  0.0124        15  0.0114 dbus-daemon
      151  0.0055         0       0        15  0.0104        10  0.0076 gpgv
      148  0.0054         1  0.0171        24  0.0166        25  0.0190 libapt-pkg.so.4.10.1
      136  0.0050         1  0.0171        16  0.0110         6  0.0046 libgobject-2.0.so.0.2800.6
      118  0.0043         1  0.0171        11  0.0076         7  0.0053 libpixman-1.so.0.20.2
      117  0.0043         0       0         3  0.0021         5  0.0038 thttpd
      112  0.0041         4  0.0685        16  0.0110        11  0.0084 libgdbm.so.3.0.0
      100  0.0037         4  0.0685         5  0.0035         6  0.0046 Xorg
       75  0.0028         1  0.0171         2  0.0014         6  0.0046 mawk
       74  0.0027         3  0.0514        10  0.0069         9  0.0069 libdbus-1.so.3.5.4
       73  0.0027         0       0        11  0.0076        12  0.0091 ophelp
       73  0.0027         1  0.0171         6  0.0041         4  0.0030 libcairo.so.2.11000.2
       73  0.0027         0       0         7  0.0048         8  0.0061 libman-2.5.9.so
       71  0.0026         0       0        14  0.0097        10  0.0076 libpangoft2-1.0.so.0.2800.4
       66  0.0024         0       0         2  0.0014         3  0.0023 ntpd
	CPU_CYCLES:200000|PC_BRANCH_MIS_...|PC_BRANCH_MIS_...|PC_IMM_BRANCH:...|
	  samples|      %|  samples|      %|  samples|      %|  samples|      %|
	------------------------------------------------------------------------
	       65 98.4848         0       0         2 100.000         3 100.000 ntpd
	        1  1.5152         0       0         0       0         0       0 [vectors] (tgid:3192 range:0xffff0000-0xffff1000)
       54  0.0020         2  0.0343         5  0.0035         3  0.0023 dash
       53  0.0019         0       0        10  0.0069        13  0.0099 tr
       52  0.0019         0       0         5  0.0035         5  0.0038 libX11.so.6.3.0
       50  0.0018         2  0.0343        10  0.0069         7  0.0053 locale-archive
       46  0.0017         1  0.0171        13  0.0090        11  0.0084 libncurses.so.5.7
       39  0.0014         0       0         3  0.0021         2  0.0015 libmandb-2.5.9.so
       35  0.0013         0       0         4  0.0028         2  0.0015 libgtk-x11-2.0.so.0.2400.4
       32  0.0012         1  0.0171         2  0.0014         2  0.0015 sshd
       31  0.0011         0       0         1 6.9e-04         3  0.0023 libgdk-x11-2.0.so.0.2400.4
       24 8.8e-04         1  0.0171         2  0.0014         3  0.0023 libgio-2.0.so.0.2800.6
       19 7.0e-04         1  0.0171         0       0         2  0.0015 rm
       19 7.0e-04         0       0         4  0.0028         5  0.0038 dpkg
       17 6.2e-04         1  0.0171         1 6.9e-04         0       0 libpango-1.0.so.0.2800.4
       16 5.9e-04         0       0         1 6.9e-04         0       0 libdbus-glib-1.so.2.1.0
       15 5.5e-04         0       0         1 6.9e-04         0       0 librt-2.13.so
       15 5.5e-04         1  0.0171         4  0.0028         1 7.6e-04 http
       13 4.8e-04         0       0         1 6.9e-04         4  0.0030 ls
       13 4.8e-04         0       0         1 6.9e-04         1 7.6e-04 libm-2.13.so
       12 4.4e-04         0       0         0       0         0       0 libgthread-2.0.so.0.2800.6
       11 4.0e-04         0       0         0       0         2  0.0015 grep
       11 4.0e-04         0       0         0       0         0       0 libdl-2.13.so
       11 4.0e-04         0       0         1 6.9e-04         0       0 sudo
       11 4.0e-04         0       0         0       0         1 7.6e-04 libORBit-2.so.0.1.0
       11 4.0e-04         0       0         0       0         0       0 rsyslogd
       10 3.7e-04         0       0         2  0.0014         1 7.6e-04 _gobject.so
        9 3.3e-04         0       0         0       0         0       0 libproc-3.2.8.so
        9 3.3e-04         0       0         3  0.0021         2  0.0015 cmp
        9 3.3e-04         1  0.0171         0       0         0       0 libxcb.so.1.1.0
        7 2.6e-04         0       0         1 6.9e-04         0       0 libpopt.so.0.0.0
        7 2.6e-04         0       0         1 6.9e-04         2  0.0015 libfb.so
        6 2.2e-04         0       0         3  0.0021         2  0.0015 dpkg-statoverride
        6 2.2e-04         0       0         1 6.9e-04         0       0 find
        6 2.2e-04         0       0         1 6.9e-04         0       0 mandb
        5 1.8e-04         0       0         2  0.0014         0       0 libgcc_s.so.1
        5 1.8e-04         0       0         0       0         0       0 libpangocairo-1.0.so.0.2800.4
        5 1.8e-04         0       0         0       0         0       0 libsqlite3.so.0.8.6
        4 1.5e-04         0       0         0       0         2  0.0015 libnss_compat-2.13.so
        4 1.5e-04         0       0         0       0         0       0 metacity
        3 1.1e-04         0       0         0       0         0       0 top
        3 1.1e-04         0       0         0       0         0       0 libXext.so.6.4.0
        3 1.1e-04         0       0         0       0         0       0 _gtk.so
        2 7.3e-05         0       0         0       0         0       0 date
        2 7.3e-05         0       0         0       0         0       0 sed
        2 7.3e-05         0       0         1 6.9e-04         0       0 init
        2 7.3e-05         0       0         0       0         0       0 killall5
        2 7.3e-05         0       0         0       0         0       0 libgconf-2.so.4.1.5
        2 7.3e-05         0       0         0       0         0       0 libgvfscommon.so.0.0.0
        2 7.3e-05         0       0         0       0         0       0 packagekitd
        2 7.3e-05         0       0         0       0         0       0 _xapian.so
        2 7.3e-05         0       0         1 6.9e-04         0       0 libshadow.so
        1 3.7e-05         0       0         0       0         0       0 cat
        1 3.7e-05         0       0         0       0         0       0 df
        1 3.7e-05         0       0         0       0         0       0 touch
        1 3.7e-05         0       0         0       0         0       0 libattr.so.1.1.0
        1 3.7e-05         0       0         0       0         0       0 libexpat.so.1.5.2
        1 3.7e-05         0       0         1 6.9e-04         1 7.6e-04 libpam.so.0.82.3
        1 3.7e-05         0       0         0       0         0       0 libselinux.so.1
        1 3.7e-05         0       0         0       0         0       0 libudev.so.0.11.1
        1 3.7e-05         0       0         0       0         0       0 libutil-2.13.so
        1 3.7e-05         0       0         0       0         0       0 pam_unix.so
        1 3.7e-05         0       0         0       0         0       0 libnih.so.1.0.0
        1 3.7e-05         0       0         0       0         0       0 apt-get
        1 3.7e-05         0       0         0       0         0       0 dircolors
        1 3.7e-05         0       0         0       0         0       0 gnome-power-manager
        1 3.7e-05         0       0         0       0         0       0 seq
        1 3.7e-05         0       0         0       0         0       0 wget
        1 3.7e-05         0       0         0       0         0       0 xargs
        1 3.7e-05         0       0         0       0         0       0 libXrender.so.1.3.0
        1 3.7e-05         0       0         0       0         0       0 libatk-1.0.so.0.9.1
        1 3.7e-05         0       0         0       0         0       0 gconfd-2
        1 3.7e-05         0       0         0       0         0       0 module-console-kit.so
        1 3.7e-05         0       0         0       0         0       0 rtkit-daemon
        1 3.7e-05         0       0         0       0         0       0 libextmod.so
        1 3.7e-05         0       0         0       0         0       0 NetworkManager
        1 3.7e-05         0       0         0       0         0       0 cron
        1 3.7e-05         0       0         0       0         0       0 logrotate
        0       0         1  0.0171         1 6.9e-04         0       0 chown
        0       0         0       0         1 6.9e-04         0       0 du
        0       0         0       0         1 6.9e-04         0       0 _speedups.so
 
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted CPU_CYCLES events (Number of CPU cycles) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_BRANCH_MIS_PRED events (Branch mispredicted or not predicted. Counts pipeline flushes because of misprediction) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_BRANCH_MIS_USED events (Branch or change in program flow that could have been predicted) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_IMM_BRANCH events (Immediate branch instruction executed (taken or not)) with a unit mask of 0x00 (No unit mask) count 200000
samples  %        samples  %        samples  %        samples  %        symbol name
411607   15.7066  54        1.1390  2403      1.7559  2299      1.8434  cftmdl(int, int, float*, float*)
385536   14.7117  1060     22.3582  27523    20.1112  25226    20.2269  cosl
342200   13.0581  1402     29.5718  33463    24.4516  31365    25.1493  sinl
162324    6.1941  21        0.4429  666       0.4867  629       0.5043  cft1st(int, float*, float*)
160375    6.1198  25        0.5273  1020      0.7453  939       0.7529  bitrv2(int, int*, float*)
159969    6.1043  347       7.3191  8451      6.1752  6180      4.9553  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
108735    4.1492  64        1.3499  7093      5.1829  5221      4.1863  floor
98384     3.7542  13        0.2742  3910      2.8571  3842      3.0806  v_GetPowerSpectrum(float (*) [2], float*, int)
72441     2.7643  60        1.2656  7983      5.8332  7835      6.2823  sincos
71089     2.7127  11        0.2320  9512      6.9505  9521      7.6342  FindSpikes(float*, int, int, SETI_WU_INFO&)
68409     2.6104  5         0.1055  1151      0.8410  1192      0.9558  cftfsub(int, float*, float*)
56338     2.1498  20        0.4219  624       0.4560  559       0.4482  f_GetChiSq(float*, int, int, float, float, float*, float*)
53108     2.0266  41        0.8648  1690      1.2349  1750      1.4032  GetFixedPoT(float*, int, int, float*, int, int)
49720     1.8973  76        1.6030  3109      2.2718  2613      2.0952  GaussFit(float*, int, int)
46645     1.7799  51        1.0757  1416      1.0347  1257      1.0079  lcgf(double, double)
45024     1.7181  11        0.2320  1045      0.7636  977       0.7834  memcpy
43845     1.6731  94        1.9827  1822      1.3313  1624      1.3022  analyze_pot(float*, int, ChirpFftPair_t&)
42639     1.6271  107       2.2569  5130      3.7485  5102      4.0909  f_GetTrueMean(float*, int, float, int, int)
34584     1.3197  25        0.5273  3512      2.5662  3147      2.5234  f_GetPeak(float*, int, int, float, float, float*)
31118     1.1874  112       2.3624  1675      1.2239  1626      1.3038  __ieee754_log
18960     0.7235  18        0.3797  1697      1.2400  1694      1.3583  find_triplets(float const*, int, float, int, int)
15916     0.6073  229       4.8302  1359      0.9930  880       0.7056  sw_sum2_t31(float**, PoTPlan*)
13221     0.5045  15        0.3164  908       0.6635  890       0.7136  float_to_uchar(float*, unsigned char*, long, float)
12238     0.4670  70        1.4765  687       0.5020  540       0.4330  find_pulse(float const*, int, float, int, int)
9329      0.3560  74        1.5609  640       0.4677  395       0.3167  sw_sum3_t31(float**, PoTPlan*)
9156      0.3494  23        0.4851  730       0.5334  668       0.5356  malloc
8505      0.3245  90        1.8983  496       0.3624  337       0.2702  sw_sum4_t31(float**, PoTPlan*)
7749      0.2957  60        1.2656  1209      0.8834  1072      0.8596  free
7730      0.2950  8         0.1687  428       0.3127  428       0.3432  strchr
7642      0.2916  59        1.2445  466       0.3405  324       0.2598  sw_sum5_t31(float**, PoTPlan*)
6959      0.2655  102       2.1514  1174      0.8578  1096      0.8788  _int_malloc
5455      0.2082  63        1.3288  127       0.0928  135       0.1082  csloww1
5341      0.2038  0              0  427       0.3120  420       0.3368  Laligned
5329      0.2033  18        0.3797  297       0.2170  254       0.2037  logl
5122      0.1955  17        0.3586  115       0.0840  116       0.0930  top_sum3(float**, PoTPlan*)
3516      0.1342  13        0.2742  62        0.0453  60        0.0481  top_sum4(float**, PoTPlan*)
2953      0.1127  3         0.0633  49        0.0358  38        0.0305  isnanl
2913      0.1112  11        0.2320  624       0.4560  646       0.5180  _int_free
2693      0.1028  4         0.0844  39        0.0285  25        0.0200  top_sum5(float**, PoTPlan*)
2371      0.0905  35        0.7382  338       0.2470  185       0.1483  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
1880      0.0717  12        0.2531  250       0.1827  252       0.2021  time_to_ra_dec(double, double*, double*)
1769      0.0675  9         0.1898  76        0.0555  60        0.0481  top_sum2(float**, PoTPlan*)
1514      0.0578  25        0.5273  110       0.0804  65        0.0521  checkpoint(unsigned char)
1355      0.0517  0              0  107       0.0782  98        0.0786  fraction_done(double, double)
1315      0.0502  8         0.1687  35        0.0256  33        0.0265  __dubsin
1269      0.0484  17        0.3586  37        0.0270  29        0.0233  __dubcos
1065      0.0406  23        0.4851  133       0.0972  159       0.1275  malloc_consolidate
719       0.0274  0              0  24        0.0175  25        0.0200  v_BaseLineSmooth(float (*) [2], int, int, int)
694       0.0265  9         0.1898  79        0.0577  42        0.0337  workunit_grp::workunit_grp()
627       0.0239  0              0  6         0.0044  6         0.0048  calc_detection_freq(double, double, double)
612       0.0234  5         0.1055  25        0.0183  14        0.0112  gaussian::gaussian()
589       0.0225  0              0  32        0.0234  32        0.0257  TripletProgressUnits()
584       0.0223  2         0.0422  76        0.0555  46        0.0369  PulseProgressUnits(double, int)
565       0.0216  6         0.1266  42        0.0307  62        0.0497  operator new(unsigned int)
540       0.0206  12        0.2531  10        0.0073  17        0.0136  csloww
506       0.0193  8         0.1687  69        0.0504  71        0.0569  .divsi3_skip_div0_test
480       0.0183  0              0  66        0.0482  38        0.0305  analysis_config::analysis_config()
471       0.0180  5         0.1055  60        0.0438  62        0.0497  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
421       0.0161  1         0.0211  19        0.0139  26        0.0208  GAUSS_INFO::~GAUSS_INFO()
373       0.0142  2         0.0422  46        0.0336  39        0.0313  receiver_config::receiver_config()
337       0.0129  5         0.1055  21        0.0153  13        0.0104  result::result()
309       0.0118  2         0.0422  24        0.0175  25        0.0200  operator delete(void*)
297       0.0113  11        0.2320  64        0.0468  73        0.0585  memset
284       0.0108  0              0  3         0.0022  2         0.0016  boinc_fraction_done
263       0.0100  1         0.0211  19        0.0139  12        0.0096  data_description_t::data_description_t()
260       0.0099  1         0.0211  10        0.0073  8         0.0064  GenChirpFftPairs(ChirpFftPair_t**, double*)
258       0.0098  2         0.0422  20        0.0146  20        0.0160  tape::tape()
249       0.0095  5         0.1055  58        0.0424  54        0.0433  boinc_time_to_checkpoint
224       0.0085  2         0.0422  19        0.0139  24        0.0192  _ZN7sqlblobIfEC2EPKfj16tag_xml_encoding.clone.337
224       0.0085  1         0.0211  8         0.0058  13        0.0104  __udivsi3
211       0.0081  2         0.0422  28        0.0205  24        0.0192  __divsi3
206       0.0079  0              0  1        7.3e-04  1        8.0e-04  bitrv2conj(int, int*, float*)
203       0.0077  4         0.0844  6         0.0044  3         0.0024  workunit_header::workunit_header()
200       0.0076  0              0  22        0.0161  14        0.0112  splitter_config::splitter_config()
188       0.0072  2         0.0422  4         0.0029  7         0.0056  cnvt_bin_hz(int, int)
165       0.0063  12        0.2531  22        0.0161  20        0.0160  GaussianProgressUnits()
150       0.0057  0              0  1        7.3e-04  0              0  cftbsub(int, float*, float*)
145       0.0055  2         0.0422  16        0.0117  18        0.0144  MFILE::MFILE()
136       0.0052  1         0.0211  7         0.0051  4         0.0032  seti_analyze(ANALYSIS_STATE&)
128       0.0049  6         0.1266  9         0.0066  3         0.0024  recorder_config::recorder_config()
124       0.0047  1         0.0211  36        0.0263  31        0.0249  GAUSS_INFO::GAUSS_INFO()
121       0.0046  5         0.1055  6         0.0044  0              0  subband_description_t::subband_description_t()
112       0.0043  4         0.0844  11        0.0080  5         0.0040  MFILE::~MFILE()
94        0.0036  4         0.0844  18        0.0132  7         0.0056  _ZN7sqlblobI12coordinate_tEC2EPKS0_j16tag_xml_encoding.clone.343
80        0.0031  2         0.0422  1        7.3e-04  1        8.0e-04  __docos
68        0.0026  1         0.0211  4         0.0029  1        8.0e-04  _ZN7sqlblobI17chirp_parameter_tEC2EPKS0_j16tag_xml_encoding.clone.342
63        0.0024  1         0.0211  0              0  3         0.0024  _ZN7sqlblobIhEC2EPKhj16tag_xml_encoding.clone.336
55        0.0021  0              0  0              0  1        8.0e-04  spike::spike()
54        0.0021  0              0  1        7.3e-04  1        8.0e-04  timer_handler()
48        0.0018  0              0  1        7.3e-04  0              0  __ieee754_log10
45        0.0017  0              0  1        7.3e-04  0              0  bits_to_floats(unsigned char*, float (*) [2], int)
44        0.0017  0              0  6         0.0044  6         0.0048  std::_Rb_tree_insert_and_rebalance(bool, std::_Rb_tree_node_base*, std::_Rb_tree_node_base*, std::_Rb_tree_node_base&)
38        0.0015  0              0  1        7.3e-04  5         0.0040  ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
35        0.0013  0              0  4         0.0029  0              0  SPIKE_INFO::~SPIKE_INFO()
34        0.0013  0              0  0              0  0              0  SPIKE_INFO::SPIKE_INFO()
34        0.0013  0              0  0              0  0              0  cdft(int, int, float (*) [2], int*, float*)
33        0.0013  1         0.0211  0              0  3         0.0024  GetProgressUnitSize(int, int)
28        0.0011  1         0.0211  0              0  0              0  std::_Rb_tree<long long, std::pair<long long const, ChirpFftPair_t>, std::_Select1st<std::pair<long long const, ChirpFftPair_t> >, std::less<long long>, std::allocator<std::pair<long long const, ChirpFftPair_t> > >::_M_erase(std::_Rb_tree_node<std::pair<long long const, ChirpFftPair_t> >*)
28        0.0011  0              0  3         0.0022  1        8.0e-04  std::_Rb_tree_increment(std::_Rb_tree_node_base*)
27        0.0010  0              0  1        7.3e-04  4         0.0032  GetPulsePoTLen(long, int*, int*)
25       9.5e-04  0              0  2         0.0015  2         0.0016  SpikeProgressUnits(int)
22       8.4e-04  0              0  0              0  0              0  dtime()
22       8.4e-04  0              0  0              0  0              0  nanosleep
20       7.6e-04  0              0  0              0  0              0  __default_sa_restorer_v2
20       7.6e-04  0              0  1        7.3e-04  1        8.0e-04  std::vector<unsigned char, std::allocator<unsigned char> > x_setiathome_decode<unsigned char>(char const*, unsigned int)
19       7.3e-04  0              0  0              0  1        8.0e-04  log10l
18       6.9e-04  0              0  0              0  0              0  boinc_sleep(double)
17       6.5e-04  0              0  0              0  1        8.0e-04  ComputePoTInfo(int, int)
17       6.5e-04  0              0  3         0.0022  3         0.0024  std::_Rb_tree<long long, std::pair<long long const, ChirpFftPair_t>, std::_Select1st<std::pair<long long const, ChirpFftPair_t> >, std::less<long long>, std::allocator<std::pair<long long const, ChirpFftPair_t> > >::_M_insert_unique_(std::_Rb_tree_const_iterator<std::pair<long long const, ChirpFftPair_t> >, std::pair<long long const, ChirpFftPair_t> const&)
17       6.5e-04  2         0.0422  3         0.0022  3         0.0024  std::_Rb_tree_decrement(std::_Rb_tree_node_base*)
16       6.1e-04  0              0  1        7.3e-04  0              0  __kernel_cosf
16       6.1e-04  0              0  0              0  1        8.0e-04  worker_signal_handler(int)
14       5.3e-04  0              0  0              0  0              0  __ieee754_fmod
13       5.0e-04  0              0  0              0  0              0  ____libc_disable_asynccancel_veneer
13       5.0e-04  0              0  1        7.3e-04  1        8.0e-04  __fixdfdi
13       5.0e-04  0              0  0              0  0              0  gettimeofday
13       5.0e-04  0              0  2         0.0015  0              0  usleep
12       4.6e-04  0              0  0              0  0              0  __libc_enable_asynccancel
12       4.6e-04  0              0  1        7.3e-04  1        8.0e-04  getrusage
11       4.2e-04  0              0  0              0  1        8.0e-04  timer_thread(void*)
10       3.8e-04  1         0.0211  3         0.0022  3         0.0024  __aeabi_d2ulz
9        3.4e-04  0              0  0              0  0              0  __libc_disable_asynccancel
9        3.4e-04  1         0.0211  1        7.3e-04  0              0  fmodl
9        3.4e-04  0              0  0              0  1        8.0e-04  makewt(int, int*, float*)
8        3.1e-04  0              0  0              0  0              0  ____libc_enable_asynccancel_veneer
8        3.1e-04  1         0.0211  2         0.0015  0              0  __kernel_sinf
8        3.1e-04  0              0  0              0  0              0  sincosf
6        2.3e-04  0              0  1        7.3e-04  0              0  isinfl
6        2.3e-04  0              0  0              0  0              0  pulse::pulse()
6        2.3e-04  0              0  2         0.0015  0              0  strstr
5        1.9e-04  0              0  0              0  0              0  invert_lcgf(float, float, float)
5        1.9e-04  0              0  1        7.3e-04  0              0  memalign
4        1.5e-04  1         0.0211  0              0  0              0  PULSE_INFO::PULSE_INFO()
3        1.1e-04  0              0  0              0  0              0  ChirpProgressUnits()
3        1.1e-04  0              0  0              0  0              0  __mul
3        1.1e-04  0              0  2         0.0015  0              0  _int_memalign
3        1.1e-04  0              0  0              0  0              0  std::local_Rb_tree_rotate_left(std::_Rb_tree_node_base*, std::_Rb_tree_node_base*&)
2        7.6e-05  0              0  0              0  0              0  PULSE_INFO::~PULSE_INFO()
2        7.6e-05  0              0  0              0  0              0  anonymous symbol from section .text
2        7.6e-05  0              0  0              0  1        8.0e-04  memchr
2        7.6e-05  0              0  0              0  0              0  std::_Rb_tree_decrement(std::_Rb_tree_node_base const*)
2        7.6e-05  0              0  0              0  0              0  std::local_Rb_tree_rotate_right(std::_Rb_tree_node_base*, std::_Rb_tree_node_base*&)
1        3.8e-05  0              0  0              0  0              0  Llastword
1        3.8e-05  0              0  0              0  0              0  _ZNSt19basic_istringstreamIcSt11char_traitsIcESaIcEEC1ERKSsSt13_Ios_Openmode.clone.328
1        3.8e-05  0              0  0              0  0              0  __aeabi_uidivmod
1        3.8e-05  0              0  0              0  0              0  __cpy
1        3.8e-05  0              0  0              0  0              0  __cxxabiv1::__vmi_class_type_info::__do_dyncast(int, __cxxabiv1::__class_type_info::__sub_kind, __cxxabiv1::__class_type_info const*, void const*, __cxxabiv1::__class_type_info const*, void const*, __cxxabiv1::__class_type_info::__dyncast_result&) const
1        3.8e-05  0              0  0              0  0              0  __mpn_divrem
1        3.8e-05  0              0  0              0  0              0  __mpn_mul_1
1        3.8e-05  0              0  0              0  0              0  boinc_info
1        3.8e-05  0              0  0              0  0              0  boinc_ops_cumulative
1        3.8e-05  0              0  0              0  1        8.0e-04  bool std::has_facet<std::num_put<char, std::ostreambuf_iterator<char, std::char_traits<char> > > >(std::locale const&)
1        3.8e-05  0              0  0              0  0              0  fgets
1        3.8e-05  0              0  0              0  0              0  free_a(void*)
1        3.8e-05  0              0  0              0  0              0  int std::__int_to_char<char, unsigned long>(char*, unsigned long, char const*, std::_Ios_Fmtflags, bool)
1        3.8e-05  0              0  0              0  0              0  memcmp
1        3.8e-05  0              0  0              0  0              0  plan_PulsePoT(PoTPlan*, int, float*, int*)
1        3.8e-05  0              0  0              0  0              0  std::basic_ostream<char, std::char_traits<char> >& std::__ostream_insert<char, std::char_traits<char> >(std::basic_ostream<char, std::char_traits<char> >&, char const*, int)
1        3.8e-05  0              0  0              0  0              0  std::basic_ostream<char, std::char_traits<char> >& std::operator<< <std::char_traits<char> >(std::basic_ostream<char, std::char_traits<char> >&, char const*)
1        3.8e-05  0              0  0              0  0              0  std::istreambuf_iterator<char, std::char_traits<char> >::_M_get() const
1        3.8e-05  0              0  0              0  0              0  std::type_info::operator==(std::type_info const&) const
1        3.8e-05  0              0  0              0  0              0  t_funct(int, int, int)
1        3.8e-05  0              0  0              0  0              0  vfprintf
1        3.8e-05  0              0  0              0  0              0  xml_match_tag(char const*, char const*)
0              0  0              0  0              0  1        8.0e-04  ____strtol_l_internal
0              0  0              0  0              0  1        8.0e-04  add_magnitudes
0              0  0              0  0              0  1        8.0e-04  std::ostream& std::ostream::_M_insert<unsigned long>(unsigned long)
0              0  0              0  0              0  1        8.0e-04  std::string::find(char const*, unsigned int, unsigned int) const
0              0  1         0.0211  0              0  0              0  strcmp
 
 
Mon Oct  3 08:31:37 PDT 2011
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted CO_LF_HIT events (Number of coherent linefill requests which hit in another CPU, meaning that the linefill data is fetched directly from the relevant cache) with a unit mask of 0x00 (No unit mask) count 200000
Counted CO_LF_MISS events (Number of coherent linefill requests which miss in all other CPUs, meaning that the request is sent to external memory) with a unit mask of 0x00 (No unit mask) count 200000
 CO_LF_HIT:200000|CO_LF_MISS:200000|
  samples|      %|  samples|      %|
------------------------------------
      112 82.3529       108  0.4290 no-vmlinux
       24 17.6471     25046 99.4797 seti_boinc
        0       0         2  0.0079 bash
        0       0         1  0.0040 grep
        0       0         5  0.0199 ld-2.13.so
        0       0         7  0.0278 libc-2.13.so
        0       0         2  0.0079 libglib-2.0.so.0.2800.6
        0       0         1  0.0040 libgio-2.0.so.0.2800.6
        0       0         1  0.0040 libpango-1.0.so.0.2800.4
        0       0         1  0.0040 libpixman-1.so.0.20.2
        0       0         3  0.0119 thttpd
 
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted CO_LF_HIT events (Number of coherent linefill requests which hit in another CPU, meaning that the linefill data is fetched directly from the relevant cache) with a unit mask of 0x00 (No unit mask) count 200000
Counted CO_LF_MISS events (Number of coherent linefill requests which miss in all other CPUs, meaning that the request is sent to external memory) with a unit mask of 0x00 (No unit mask) count 200000
samples  %        samples  %        symbol name
6        25.0000  8010     31.9812  cftmdl(int, int, float*, float*)
3        12.5000  1523      6.0808  memcpy
2         8.3333  1447      5.7774  FindSpikes(float*, int, int, SETI_WU_INFO&)
2         8.3333  1753      6.9991  cft1st(int, float*, float*)
2         8.3333  1372      5.4779  cftfsub(int, float*, float*)
1         4.1667  17        0.0679  GaussFit(float*, int, int)
1         4.1667  0              0  MFILE::MFILE()
1         4.1667  0              0  __default_sa_restorer_v2
1         4.1667  0              0  __ieee754_log10
1         4.1667  11        0.0439  _int_malloc
1         4.1667  3645     14.5532  bitrv2(int, int*, float*)
1         4.1667  832       3.3219  floor
1         4.1667  0              0  isnanl
1         4.1667  1762      7.0351  v_GetPowerSpectrum(float (*) [2], float*, int)
0              0  2         0.0080  .divsi3_skip_div0_test
0              0  1         0.0040  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
0              0  1         0.0040  GAUSS_INFO::~GAUSS_INFO()
0              0  1739      6.9432  GetFixedPoT(float*, int, int, float*, int, int)
0              0  2         0.0080  SPIKE_INFO::SPIKE_INFO()
0              0  1         0.0040  SPIKE_INFO::~SPIKE_INFO()
0              0  1         0.0040  _ZN7sqlblobI17chirp_parameter_tEC2EPKS0_j16tag_xml_encoding.clone.342
0              0  1         0.0040  _ZN7sqlblobIfEC2EPKfj16tag_xml_encoding.clone.337
0              0  1         0.0040  _ZN7sqlblobIhEC2EPKhj16tag_xml_encoding.clone.336
0              0  9         0.0359  __dubcos
0              0  4         0.0160  __dubsin
0              0  28        0.1118  __ieee754_log
0              0  2         0.0080  _int_free
0              0  11        0.0439  analysis_config::analysis_config()
0              0  1610      6.4282  analyze_pot(float*, int, ChirpFftPair_t&)
0              0  1         0.0040  calc_detection_freq(double, double, double)
0              0  2         0.0080  checkpoint(unsigned char)
0              0  2         0.0080  cnvt_bin_hz(int, int)
0              0  60        0.2396  cosl
0              0  2         0.0080  csloww
0              0  10        0.0399  csloww1
0              0  1         0.0040  data_description_t::data_description_t()
0              0  10        0.0399  f_GetChiSq(float*, int, int, float, float, float*, float*)
0              0  5         0.0200  f_GetPeak(float*, int, int, float, float, float*)
0              0  7         0.0279  f_GetTrueMean(float*, int, float, int, int)
0              0  6         0.0240  find_pulse(float const*, int, float, int, int)
0              0  23        0.0918  find_triplets(float const*, int, float, int, int)
0              0  2         0.0080  float_to_uchar(float*, unsigned char*, long, float)
0              0  2         0.0080  fraction_done(double, double)
0              0  2         0.0080  free
0              0  3         0.0120  gaussian::gaussian()
0              0  10        0.0399  malloc
0              0  6         0.0240  malloc_consolidate
0              0  1         0.0040  operator delete(void*)
0              0  4         0.0160  operator new(unsigned int)
0              0  5         0.0200  result::result()
0              0  5         0.0200  seti_analyze(ANALYSIS_STATE&)
0              0  6         0.0240  sincos
0              0  216       0.8624  sinl
0              0  4         0.0160  splitter_config::splitter_config()
0              0  1         0.0040  subband_description_t::subband_description_t()
0              0  7         0.0279  sw_sum2_t31(float**, PoTPlan*)
0              0  2         0.0080  sw_sum3_t31(float**, PoTPlan*)
0              0  2         0.0080  sw_sum4_t31(float**, PoTPlan*)
0              0  1         0.0040  sw_sum5_t31(float**, PoTPlan*)
0              0  14        0.0559  tape::tape()
0              0  9         0.0359  time_to_ra_dec(double, double*, double*)
0              0  1         0.0040  timer_handler()
0              0  1         0.0040  top_sum2(float**, PoTPlan*)
0              0  2         0.0080  top_sum3(float**, PoTPlan*)
0              0  1         0.0040  top_sum4(float**, PoTPlan*)
0              0  821       3.2780  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
0              0  2         0.0080  workunit_grp::workunit_grp()
0              0  2         0.0080  workunit_header::workunit_header()
 
 
Mon Oct  3 08:49:23 PDT 2011
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted DTLB_REFILL events (Data R/W that causes a TLB refill) with a unit mask of 0x00 (No unit mask) count 200000
Counted ITLB_MISS events (Instruction fetch misses from TLB) with a unit mask of 0x00 (No unit mask) count 200000
DTLB_REFILL:20...| ITLB_MISS:200000|
  samples|      %|  samples|      %|
------------------------------------
     2803 98.2819         8 44.4444 seti_boinc
       43  1.5077         8 44.4444 no-vmlinux
        3  0.1052         1  5.5556 libc-2.13.so
        1  0.0351         1  5.5556 ld-2.13.so
        1  0.0351         0       0 libgtk-x11-2.0.so.0.2400.4
        1  0.0351         0       0 console-kit-daemon
 
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted DTLB_REFILL events (Data R/W that causes a TLB refill) with a unit mask of 0x00 (No unit mask) count 200000
Counted ITLB_MISS events (Instruction fetch misses from TLB) with a unit mask of 0x00 (No unit mask) count 200000
samples  %        samples  %        symbol name
730      26.0435  0              0  bitrv2(int, int*, float*)
602      21.4770  0              0  find_triplets(float const*, int, float, int, int)
562      20.0499  0              0  GetFixedPoT(float*, int, int, float*, int, int)
437      15.5904  1        12.5000  analyze_pot(float*, int, ChirpFftPair_t&)
85        3.0325  0              0  malloc
51        1.8195  1        12.5000  __ieee754_log
44        1.5697  0              0  _int_malloc
40        1.4270  0              0  GaussFit(float*, int, int)
23        0.8205  0              0  find_pulse(float const*, int, float, int, int)
23        0.8205  0              0  sw_sum3_t31(float**, PoTPlan*)
19        0.6778  0              0  cftmdl(int, int, float*, float*)
18        0.6422  0              0  checkpoint(unsigned char)
14        0.4995  0              0  floor
12        0.4281  0              0  f_GetTrueMean(float*, int, float, int, int)
10        0.3568  0              0  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
10        0.3568  0              0  sw_sum5_t31(float**, PoTPlan*)
9         0.3211  1        12.5000  MFILE::MFILE()
9         0.3211  0              0  f_GetPeak(float*, int, int, float, float, float*)
8         0.2854  1        12.5000  _int_free
7         0.2497  0              0  .divsi3_skip_div0_test
7         0.2497  0              0  memcpy
6         0.2141  0              0  malloc_consolidate
5         0.1784  1        12.5000  cft1st(int, float*, float*)
5         0.1784  0              0  logl
4         0.1427  0              0  FindSpikes(float*, int, int, SETI_WU_INFO&)
4         0.1427  0              0  data_description_t::data_description_t()
4         0.1427  0              0  sw_sum2_t31(float**, PoTPlan*)
4         0.1427  0              0  sw_sum4_t31(float**, PoTPlan*)
4         0.1427  0              0  tape::tape()
4         0.1427  0              0  time_to_ra_dec(double, double*, double*)
4         0.1427  0              0  workunit_grp::workunit_grp()
3         0.1070  0              0  GAUSS_INFO::~GAUSS_INFO()
3         0.1070  0              0  __divsi3
3         0.1070  0              0  cftfsub(int, float*, float*)
3         0.1070  0              0  f_GetChiSq(float*, int, int, float, float, float*, float*)
3         0.1070  0              0  free
3         0.1070  0              0  isnanl
3         0.1070  0              0  result::result()
3         0.1070  0              0  v_GetPowerSpectrum(float (*) [2], float*, int)
2         0.0714  0              0  PulseProgressUnits(double, int)
2         0.0714  0              0  calc_detection_freq(double, double, double)
2         0.0714  0              0  lcgf(double, double)
2         0.0714  1        12.5000  sinl
2         0.0714  1        12.5000  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
1         0.0357  0              0  __udivsi3
1         0.0357  1        12.5000  cosl
1         0.0357  0              0  memset
1         0.0357  0              0  operator delete(void*)
1         0.0357  0              0  top_sum3(float**, PoTPlan*)
 
```

## running same for 120s ##
```
Mon Oct  3 09:02:10 PDT 2011
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted CPU_CYCLES events (Number of CPU cycles) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_BRANCH_MIS_PRED events (Branch mispredicted or not predicted. Counts pipeline flushes because of misprediction) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_BRANCH_MIS_USED events (Branch or change in program flow that could have been predicted) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_IMM_BRANCH events (Immediate branch instruction executed (taken or not)) with a unit mask of 0x00 (No unit mask) count 200000
CPU_CYCLES:200000|PC_BRANCH_MIS_...|PC_BRANCH_MIS_...|PC_IMM_BRANCH:...|
  samples|      %|  samples|      %|  samples|      %|  samples|      %|
------------------------------------------------------------------------
   306808 93.8122       554 69.8613     15774 91.7733     14415 92.6473 seti_boinc
    15926  4.8697       187 23.5813       842  4.8988       617  3.9656 no-vmlinux
     1794  0.5485        24  3.0265       293  1.7047       271  1.7418 libc-2.13.so
      854  0.2611        13  1.6393        83  0.4829        80  0.5142 bash
      644  0.1969         4  0.5044        45  0.2618        44  0.2828 ld-2.13.so
      571  0.1746         1  0.1261       103  0.5993        89  0.5720 oprofiled
       84  0.0257         2  0.2522        10  0.0582        10  0.0643 libglib-2.0.so.0.2800.6
       45  0.0138         0       0         4  0.0233         3  0.0193 dbus-daemon
       41  0.0125         1  0.1261        11  0.0640        10  0.0643 locale-archive
       28  0.0086         0       0         5  0.0291         5  0.0321 tr
       25  0.0076         0       0         4  0.0233         0       0 libgobject-2.0.so.0.2800.6
       24  0.0073         2  0.2522         4  0.0233         4  0.0257 ophelp
       22  0.0067         2  0.2522         0       0         0       0 mawk
       21  0.0064         0       0         4  0.0233         0       0 libpthread-2.13.so
       16  0.0049         1  0.1261         1  0.0058         1  0.0064 libdbus-1.so.3.5.4
       16  0.0049         1  0.1261         1  0.0058         1  0.0064 libpixman-1.so.0.20.2
       14  0.0043         0       0         0       0         1  0.0064 libgio-2.0.so.0.2800.6
       12  0.0037         0       0         0       0         1  0.0064 Xorg
       11  0.0034         0       0         1  0.0058         0       0 thttpd
        8  0.0024         0       0         0       0         0       0 libdl-2.13.so
        8  0.0024         0       0         1  0.0058         2  0.0129 libpangoft2-1.0.so.0.2800.4
        6  0.0018         0       0         0       0         1  0.0064 libm-2.13.so
        6  0.0018         0       0         0       0         1  0.0064 libcairo.so.2.11000.2
        6  0.0018         0       0         0       0         0       0 ntpd
        6  0.0018         0       0         0       0         0       0 sshd
        4  0.0012         0       0         0       0         0       0 grep
        4  0.0012         0       0         0       0         0       0 sudo
        4  0.0012         0       0         1  0.0058         0       0 libpango-1.0.so.0.2800.4
        3 9.2e-04         0       0         0       0         0       0 libncurses.so.5.7
        3 9.2e-04         0       0         0       0         0       0 libX11.so.6.3.0
        3 9.2e-04         0       0         0       0         1  0.0064 libgdk-x11-2.0.so.0.2400.4
        2 6.1e-04         1  0.1261         0       0         1  0.0064 dash
        2 6.1e-04         0       0         0       0         0       0 init
        2 6.1e-04         0       0         0       0         0       0 libgthread-2.0.so.0.2800.6
        2 6.1e-04         0       0         0       0         0       0 libpangocairo-1.0.so.0.2800.4
        2 6.1e-04         0       0         0       0         0       0 libxcb.so.1.1.0
        2 6.1e-04         0       0         0       0         0       0 libdbus-glib-1.so.2.1.0
        2 6.1e-04         0       0         0       0         0       0 libgtk-x11-2.0.so.0.2400.4
        2 6.1e-04         0       0         0       0         0       0 libshadow.so
        1 3.1e-04         0       0         0       0         0       0 ls
        1 3.1e-04         0       0         0       0         0       0 libgcc_s.so.1
        1 3.1e-04         0       0         0       0         0       0 libnss_compat-2.13.so
        1 3.1e-04         0       0         0       0         0       0 libpam.so.0.82.3
        1 3.1e-04         0       0         0       0         0       0 libpcre.so.3.12.1
        1 3.1e-04         0       0         0       0         0       0 libpopt.so.0.0.0
        1 3.1e-04         0       0         0       0         0       0 pam_gnome_keyring.so
        1 3.1e-04         0       0         0       0         0       0 gdm-simple-greeter
        1 3.1e-04         0       0         0       0         0       0 module-console-kit.so
        1 3.1e-04         0       0         0       0         0       0 imuxsock.so
        1 3.1e-04         0       0         0       0         0       0 console-kit-daemon
        1 3.1e-04         0       0         0       0         0       0 rsyslogd
        0       0         0       0         0       0         1  0.0064 libnih.so.1.0.0
        0       0         0       0         1  0.0058         0       0 libfb.so
 
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted CPU_CYCLES events (Number of CPU cycles) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_BRANCH_MIS_PRED events (Branch mispredicted or not predicted. Counts pipeline flushes because of misprediction) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_BRANCH_MIS_USED events (Branch or change in program flow that could have been predicted) with a unit mask of 0x00 (No unit mask) count 200000
Counted PC_IMM_BRANCH events (Immediate branch instruction executed (taken or not)) with a unit mask of 0x00 (No unit mask) count 200000
samples  %        samples  %        samples  %        samples  %        symbol name
48333    15.7535  6         1.0830  290       1.8385  263       1.8245  cftmdl(int, int, float*, float*)
45311    14.7685  135      24.3682  3174     20.1217  2977     20.6521  cosl
39806    12.9742  150      27.0758  3971     25.1743  3663     25.4110  sinl
19123     6.2329  3         0.5415  68        0.4311  72        0.4995  cft1st(int, float*, float*)
18904     6.1615  1         0.1805  118       0.7481  125       0.8672  bitrv2(int, int*, float*)
18826     6.1361  42        7.5812  929       5.8894  704       4.8838  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
12765     4.1606  8         1.4440  795       5.0399  571       3.9612  floor
11590     3.7776  1         0.1805  440       2.7894  446       3.0940  v_GetPowerSpectrum(float (*) [2], float*, int)
8630      2.8128  7         1.2635  923       5.8514  879       6.0978  sincos
8355      2.7232  1         0.1805  1100      6.9735  1098      7.6171  FindSpikes(float*, int, int, SETI_WU_INFO&)
8116      2.6453  1         0.1805  133       0.8432  143       0.9920  cftfsub(int, float*, float*)
6892      2.2464  7         1.2635  56        0.3550  63        0.4370  f_GetChiSq(float*, int, int, float, float, float*, float*)
6641      2.1645  4         0.7220  215       1.3630  191       1.3250  GetFixedPoT(float*, int, int, float*, int, int)
6035      1.9670  6         1.0830  375       2.3773  307       2.1297  GaussFit(float*, int, int)
5930      1.9328  16        2.8881  235       1.4898  228       1.5817  analyze_pot(float*, int, ChirpFftPair_t&)
5663      1.8458  3         0.5415  194       1.2299  159       1.1030  lcgf(double, double)
5308      1.7301  1         0.1805  112       0.7100  110       0.7631  memcpy
5083      1.6567  16        2.8881  616       3.9052  619       4.2941  f_GetTrueMean(float*, int, float, int, int)
4152      1.3533  6         1.0830  391       2.4788  408       2.8304  f_GetPeak(float*, int, int, float, float, float*)
3968      1.2933  13        2.3466  203       1.2869  172       1.1932  __ieee754_log
2691      0.8771  7         1.2635  203       1.2869  216       1.4984  find_triplets(float const*, int, float, int, int)
1566      0.5104  0              0  102       0.6466  110       0.7631  float_to_uchar(float*, unsigned char*, long, float)
1532      0.4993  9         1.6245  84        0.5325  79        0.5480  find_pulse(float const*, int, float, int, int)
1192      0.3885  9         1.6245  84        0.5325  54        0.3746  sw_sum3_t31(float**, PoTPlan*)
1024      0.3338  4         0.7220  88        0.5579  72        0.4995  malloc
967       0.3152  13        2.3466  77        0.4881  42        0.2914  sw_sum4_t31(float**, PoTPlan*)
947       0.3087  10        1.8051  131       0.8305  138       0.9573  _int_malloc
917       0.2989  12        2.1661  128       0.8115  116       0.8047  free
829       0.2702  8         1.4440  76        0.4818  34        0.2359  sw_sum5_t31(float**, PoTPlan*)
727       0.2370  4         0.7220  30        0.1902  21        0.1457  logl
648       0.2112  8         1.4440  63        0.3994  62        0.4301  sw_sum2_t31(float**, PoTPlan*)
645       0.2102  8         1.4440  15        0.0951  15        0.1041  csloww1
430       0.1402  3         0.5415  70        0.4438  54        0.3746  _int_free
378       0.1232  1         0.1805  10        0.0634  6         0.0416  isnanl
297       0.0968  1         0.1805  36        0.2282  16        0.1110  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
242       0.0789  0              0  29        0.1838  33        0.2289  time_to_ra_dec(double, double*, double*)
198       0.0645  2         0.3610  18        0.1141  13        0.0902  checkpoint(unsigned char)
185       0.0603  3         0.5415  16        0.1014  9         0.0624  fraction_done(double, double)
156       0.0508  0              0  1         0.0063  1         0.0069  __dubsin
152       0.0495  1         0.1805  5         0.0317  6         0.0416  __dubcos
123       0.0401  1         0.1805  27        0.1712  10        0.0694  malloc_consolidate
82        0.0267  0              0  7         0.0444  3         0.0208  TripletProgressUnits()
81        0.0264  1         0.1805  18        0.1141  6         0.0416  PulseProgressUnits(double, int)
80        0.0261  3         0.5415  4         0.0254  8         0.0555  workunit_grp::workunit_grp()
73        0.0238  0              0  1         0.0063  3         0.0208  gaussian::gaussian()
72        0.0235  0              0  5         0.0317  0              0  GAUSS_INFO::~GAUSS_INFO()
72        0.0235  0              0  2         0.0127  1         0.0069  calc_detection_freq(double, double, double)
70        0.0228  1         0.1805  17        0.1078  10        0.0694  .divsi3_skip_div0_test
68        0.0222  1         0.1805  5         0.0317  9         0.0624  operator new(unsigned int)
65        0.0212  0              0  9         0.0571  12        0.0832  analysis_config::analysis_config()
62        0.0202  1         0.1805  9         0.0571  11        0.0763  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
56        0.0183  1         0.1805  5         0.0317  0              0  csloww
50        0.0163  1         0.1805  6         0.0380  9         0.0624  receiver_config::receiver_config()
50        0.0163  1         0.1805  3         0.0190  1         0.0069  result::result()
45        0.0147  0              0  11        0.0697  9         0.0624  memset
45        0.0147  0              0  5         0.0317  4         0.0277  operator delete(void*)
44        0.0143  0              0  0              0  0              0  boinc_fraction_done
42        0.0137  2         0.3610  2         0.0127  0              0  tape::tape()
41        0.0134  1         0.1805  10        0.0634  5         0.0347  boinc_time_to_checkpoint
36        0.0117  3         0.5415  1         0.0063  0              0  MFILE::MFILE()
36        0.0117  0              0  3         0.0190  3         0.0208  _ZN7sqlblobIfEC2EPKfj16tag_xml_encoding.clone.337
35        0.0114  0              0  1         0.0063  0              0  workunit_header::workunit_header()
34        0.0111  1         0.1805  1         0.0063  3         0.0208  __divsi3
33        0.0108  0              0  1         0.0063  1         0.0069  data_description_t::data_description_t()
23        0.0075  0              0  2         0.0127  3         0.0208  GAUSS_INFO::GAUSS_INFO()
23        0.0075  0              0  2         0.0127  0              0  splitter_config::splitter_config()
19        0.0062  2         0.3610  1         0.0063  0              0  recorder_config::recorder_config()
19        0.0062  1         0.1805  0              0  0              0  subband_description_t::subband_description_t()
18        0.0059  0              0  2         0.0127  0              0  __docos
18        0.0059  1         0.1805  0              0  0              0  __udivsi3
18        0.0059  0              0  0              0  0              0  cnvt_bin_hz(int, int)
16        0.0052  0              0  2         0.0127  0              0  seti_analyze(ANALYSIS_STATE&)
13        0.0042  0              0  2         0.0127  4         0.0277  GaussianProgressUnits()
11        0.0036  2         0.3610  3         0.0190  1         0.0069  _ZN7sqlblobI12coordinate_tEC2EPKS0_j16tag_xml_encoding.clone.343
9         0.0029  0              0  1         0.0063  0              0  MFILE::~MFILE()
9         0.0029  0              0  0              0  0              0  __ieee754_log10
7         0.0023  0              0  2         0.0127  0              0  _ZN7sqlblobI17chirp_parameter_tEC2EPKS0_j16tag_xml_encoding.clone.342
5         0.0016  0              0  0              0  0              0  log10l
5         0.0016  0              0  0              0  0              0  timer_handler()
4         0.0013  0              0  0              0  0              0  boinc_sleep(double)
4         0.0013  0              0  0              0  0              0  spike::spike()
3        9.8e-04  0              0  0              0  0              0  SPIKE_INFO::SPIKE_INFO()
3        9.8e-04  0              0  0              0  0              0  SPIKE_INFO::~SPIKE_INFO()
3        9.8e-04  0              0  0              0  0              0  SpikeProgressUnits(int)
3        9.8e-04  0              0  0              0  2         0.0139  _ZN7sqlblobIhEC2EPKhj16tag_xml_encoding.clone.336
3        9.8e-04  0              0  0              0  0              0  __default_sa_restorer_v2
3        9.8e-04  0              0  0              0  1         0.0069  fmodl
3        9.8e-04  0              0  0              0  0              0  getrusage
2        6.5e-04  0              0  0              0  0              0  ____libc_disable_asynccancel_veneer
2        6.5e-04  0              0  0              0  0              0  cdft(int, int, float (*) [2], int*, float*)
2        6.5e-04  0              0  0              0  0              0  nanosleep
2        6.5e-04  0              0  0              0  0              0  usleep
2        6.5e-04  0              0  0              0  0              0  worker_signal_handler(int)
1        3.3e-04  0              0  0              0  0              0  ____libc_enable_asynccancel_veneer
1        3.3e-04  0              0  0              0  0              0  __gnu_cxx::stdio_sync_filebuf<wchar_t, std::char_traits<wchar_t> >::sync()
1        3.3e-04  0              0  0              0  0              0  __libc_disable_asynccancel
1        3.3e-04  0              0  0              0  0              0  __libc_enable_asynccancel
1        3.3e-04  0              0  0              0  0              0  dtime()
1        3.3e-04  0              0  0              0  1         0.0069  gettimeofday
1        3.3e-04  0              0  0              0  0              0  timer_thread(void*)
 
 
Mon Oct  3 09:04:31 PDT 2011
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted CO_LF_HIT events (Number of coherent linefill requests which hit in another CPU, meaning that the linefill data is fetched directly from the relevant cache) with a unit mask of 0x00 (No unit mask) count 200000
Counted CO_LF_MISS events (Number of coherent linefill requests which miss in all other CPUs, meaning that the request is sent to external memory) with a unit mask of 0x00 (No unit mask) count 200000
 CO_LF_HIT:200000|CO_LF_MISS:200000|
  samples|      %|  samples|      %|
------------------------------------
       13 100.000        27  1.4241 no-vmlinux
        0       0         7  0.3692 bash
        0       0      1855 97.8376 seti_boinc
        0       0         3  0.1582 ld-2.13.so
        0       0         4  0.2110 libc-2.13.so
 
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted CO_LF_MISS events (Number of coherent linefill requests which miss in all other CPUs, meaning that the request is sent to external memory) with a unit mask of 0x00 (No unit mask) count 200000
samples  %        symbol name
618      33.3154  cftmdl(int, int, float*, float*)
274      14.7709  bitrv2(int, int*, float*)
138       7.4394  v_GetPowerSpectrum(float (*) [2], float*, int)
136       7.3315  cft1st(int, float*, float*)
119       6.4151  GetFixedPoT(float*, int, int, float*, int, int)
115       6.1995  FindSpikes(float*, int, int, SETI_WU_INFO&)
112       6.0377  memcpy
105       5.6604  cftfsub(int, float*, float*)
76        4.0970  analyze_pot(float*, int, ChirpFftPair_t&)
64        3.4501  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
53        2.8571  floor
27        1.4555  sinl
4         0.2156  cosl
3         0.1617  __ieee754_log
2         0.1078  analysis_config::analysis_config()
1         0.0539  GaussFit(float*, int, int)
1         0.0539  __dubcos
1         0.0539  __dubsin
1         0.0539  _int_malloc
1         0.0539  cdft(int, int, float (*) [2], int*, float*)
1         0.0539  dtime()
1         0.0539  find_triplets(float const*, int, float, int, int)
1         0.0539  operator new(unsigned int)
1         0.0539  workunit_header::workunit_header()
 
 
Mon Oct  3 09:06:53 PDT 2011
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted DTLB_REFILL events (Data R/W that causes a TLB refill) with a unit mask of 0x00 (No unit mask) count 200000
Counted ITLB_MISS events (Instruction fetch misses from TLB) with a unit mask of 0x00 (No unit mask) count 200000
DTLB_REFILL:20...| ITLB_MISS:200000|
  samples|      %|  samples|      %|
------------------------------------
      623 90.1592         8 26.6667 seti_boinc
       61  8.8278        18 60.0000 no-vmlinux
        3  0.4342         1  3.3333 libc-2.13.so
        2  0.2894         1  3.3333 ld-2.13.so
        1  0.1447         0       0 libglib-2.0.so.0.2800.6
        1  0.1447         0       0 libpangoft2-1.0.so.0.2800.4
        0       0         2  6.6667 bash
 
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted DTLB_REFILL events (Data R/W that causes a TLB refill) with a unit mask of 0x00 (No unit mask) count 200000
Counted ITLB_MISS events (Instruction fetch misses from TLB) with a unit mask of 0x00 (No unit mask) count 200000
samples  %        samples  %        symbol name
162      26.0032  0              0  bitrv2(int, int*, float*)
131      21.0273  0              0  GetFixedPoT(float*, int, int, float*, int, int)
119      19.1011  0              0  find_triplets(float const*, int, float, int, int)
100      16.0514  0              0  analyze_pot(float*, int, ChirpFftPair_t&)
19        3.0498  1        12.5000  malloc
16        2.5682  0              0  GaussFit(float*, int, int)
12        1.9262  1        12.5000  __ieee754_log
8         1.2841  0              0  find_pulse(float const*, int, float, int, int)
6         0.9631  0              0  floor
5         0.8026  0              0  f_GetPeak(float*, int, int, float, float, float*)
5         0.8026  0              0  f_GetTrueMean(float*, int, float, int, int)
3         0.4815  0              0  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
3         0.4815  1        12.5000  FindSpikes(float*, int, int, SETI_WU_INFO&)
3         0.4815  0              0  _int_malloc
3         0.4815  1        12.5000  sinl
2         0.3210  0              0  cftfsub(int, float*, float*)
2         0.3210  1        12.5000  cftmdl(int, int, float*, float*)
2         0.3210  0              0  lcgf(double, double)
2         0.3210  0              0  sw_sum3_t31(float**, PoTPlan*)
2         0.3210  0              0  sw_sum4_t31(float**, PoTPlan*)
2         0.3210  0              0  sw_sum5_t31(float**, PoTPlan*)
2         0.3210  0              0  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
1         0.1605  0              0  MFILE::MFILE()
1         0.1605  0              0  analysis_config::analysis_config()
1         0.1605  0              0  cft1st(int, float*, float*)
1         0.1605  0              0  checkpoint(unsigned char)
1         0.1605  0              0  float_to_uchar(float*, unsigned char*, long, float)
1         0.1605  0              0  free
1         0.1605  0              0  isnanl
1         0.1605  0              0  logl
1         0.1605  0              0  malloc_consolidate
1         0.1605  0              0  memset
1         0.1605  0              0  seti_analyze(ANALYSIS_STATE&)
1         0.1605  0              0  tape::tape()
1         0.1605  0              0  v_GetPowerSpectrum(float (*) [2], float*, int)
1         0.1605  0              0  workunit_grp::workunit_grp()
0              0  1        12.5000  GaussianProgressUnits()
0              0  2        25.0000  cosl 
```

## profile script ##

```
#!/bin/bash
# ARM Cortex A9 Oprofile Script
SleepSeconds=120 #on real run
date
#rm state.sah
#sudo opcontrol --shutdown
./seti_boinc --standalone &

# Running Timer Mode
sudo opcontrol --init
sudo opcontrol --no-vmlinux
sudo opcontrol --reset
sudo opcontrol --event=CPU_CYCLES:200000:0x0:0:1 --event=INSTR_EXECUTED:200000:0x0:0:1 --event=CLK_INT_EN:200000:0x0:0:1 --event=PC_BRANCH_MIS_PRED:200000:0x0:0:1 --event=PC_BRANCH_MIS_USED:200000:0x0:0:1 --event=PC_IMM_BRANCH:200000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
echo "profiling for $SleepSeconds seconds"
sleep $SleepSeconds
sudo opcontrol --dump
date >> ARM_Versatile_Oprofile.txt
opreport >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt
opreport -l /home/user41/seti_boinc/client/seti_boinc >> ARM_Versatile_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt


# Running next event
sudo opcontrol --init
sudo opcontrol --no-vmlinux
sudo opcontrol --reset
sudo opcontrol --event=CO_LF_MISS:200000:0x0:0:1 --event=CO_LF_HIT:200000:0x0:0:1 --event=INS_FP_RR:200000:0x0:0:1 --event=INS_NEON_RR:200000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> ARM_Versatile_Oprofile.txt
opreport >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt
opreport -l /home/user41/seti_boinc/client/seti_boinc >> ARM_Versatile_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt


# Running next event
sudo opcontrol --init
sudo opcontrol --no-vmlinux
sudo opcontrol --reset
sudo opcontrol --event=ITLB_MISS:200000:0x0:0:1 --event=DTLB_REFILL:200000:0x0:0:1 --event=STALL_INS_TLB:200000:0x0:0:1 --event=STALL_DATA_TLB:200000:0x0:0:1 --event=STALL_INS_UTLB:200000:0x0:0:1 --event=STALL_DATA_ULTB:200000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> ARM_Versatile_Oprofile.txt
opreport >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt
opreport -l /home/user41/seti_boinc/client/seti_boinc >> ARM_Versatile_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt
```