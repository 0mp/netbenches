```
inet4 packets-per-second-forwarded:
x net.isr.maxthreads=1 (default)
+ net.isr.maxthreads="-1" (using all core)
+--------------------------------------------------------------------------+
|x                               +     x x  +  +       + +     x          x|
|              |_________________________M_A____________________________|  |
|                                     |________A_________|                 |
+--------------------------------------------------------------------------+
    N           Min           Max        Median           Avg        Stddev
x   5      11768793      11805162      11788602      11789965      13992.03
+   5      11784870      11796465      11791911      11791873      4683.524
No difference proven at 95.0% confidence
```
