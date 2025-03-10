Tuning coalesing parameters (reduce a lot CPU interrupt usage)
  - dev.mce.X.conf.[rx|tx]_queue_size="8192"
  - dev.mce.X.conf.[rx|tx]_coalesce_usecs="200"
  - dev.mce.X.conf.[rx|tx]_coalesce_pkts="1024"

inet4 packets-per-second forwarded:

```
x default parameters
+ tuned
+--------------------------------------------------------------------------+
|+                 +   +       ++                          x   x     x   xx|
|                                                            |______AM____||
|        |___________A_M__________|                                        |
+--------------------------------------------------------------------------+
    N           Min           Max        Median           Avg        Stddev
x   5      32330128      32482212      32425486      32416663     66797.584
+   5      31713500      32039463      31945133      31926233     131756.69
Difference at 95.0% confidence
	-490430 +/- 152342
	-1.5129% +/- 0.468504%
	(Student's t, pooled s = 104455)
```

System load (nstat -mI mce0):
Default:
```
[root@pxetest2]~# nstat -mI mce0
 InMpps OMpps  InGbs   OGbs err TCP   Est %CPU syscalls   csw irq    GBfree   MemRd     MemWr    MemRW
 33.00   0.00  15.84   0.00 2071      1   94.29    726 375813 188987 123.77   1433.60   1071.68  2505.28
 33.00   0.00  15.84   0.00 2462      1   93.85    731 375366 188771 123.77   3766.74   2630.88  6397.62
 32.99   0.00  15.83   0.00 68        1   93.18    721 375186 188523 123.76   3760.33   2633.23  6393.56
 33.00   0.00  15.84   0.00 814       1   93.77    732 373010 187580 123.76   3755.27   2628.24  6383.51
 32.99   0.00  15.84   0.00 3022      1   94.44    838 371844 186815 123.76   3755.33   2620.39  6375.71
 33.00   0.00  15.84   0.00 2351      1   94.07    720 374124 187932 123.76   3754.98   2631.69  6386.66
 33.02   0.00  15.85   0.00 732       1   94.24    720 372640 187363 123.76   3749.93   2624.18  6374.11
 32.98   0.00  15.83   0.00 2417      1   92.96    700 372115 186931 123.76   3762.54   2634.86  6397.40
```
Tuned:
```
 InMpps OMpps  InGbs   OGbs err TCP    Est %CPU syscalls   csw  irq   GBfree   MemRd     MemWr   MemRW
 32.98   0.00  15.83   0.00 16757      1   92.13    740  69830  22098 123.18   8269.41   5343.12 13612.53
 32.99   0.00  15.83   0.00 3969       1   93.23    735  68414  21913 123.18   8208.03   5323.12 13531.15
 32.99   0.00  15.84   0.00 16701      1   92.35    726  68615  22027 123.18   8227.79   5334.11 13561.90
 32.99   0.00  15.83   0.00 16087      1   92.85    736  71343  22499 123.18   8216.12   5319.86 13535.98
 32.99   0.00  15.84   0.00 8193       1   93.44    870  65372  21043 123.18   8204.90   5316.65 13521.55
 32.98   0.00  15.83   0.00 12444      1   92.54    732  69787  22105 123.18   8219.96   5326.67 13546.63
 32.99   0.00  15.84   0.00 15155      1   93.16    726  69403  22068 123.18   8209.86   5318.19 13528.04
 33.00   0.00  15.84   0.00 8530       1   93.70    730  68521  21925 123.18   8206.64   5326.21 13532.85
 32.98   0.00  15.83   0.00 6603       1   92.77    738  68871  22022 123.18   8227.44   5328.18 13555.62
```
