```
x enabled-default.inet4.pps
+ disabled.inet4.pps
+--------------------------------------------------------------------------+
|                                       x                             +    |
|x                                     xxx             +             +++   |
|              |________________A_______M________|                         |
|                                                           |______A__M___||
+--------------------------------------------------------------------------+
    N           Min           Max        Median           Avg        Stddev
x   5      21875362      28033334      27830171      26672033     2683322.2
+   5      30237691      32654824      32598388      32108032     1048372.4
Difference at 95.0% confidence
	5.436e+06 +/- 2.97095e+06
	20.3809% +/- 13.1309%
	(Student's t, pooled s = 2.03707e+06)
```

```
x enabled-default.inet6.pps
+ disabled.inet6.pps
+--------------------------------------------------------------------------+
|                                                                +         |
|    x                                                           +         |
| x xx          x                                                + +      +|
||___M_A____|                                                              |
|                                                              |_M_A___|   |
+--------------------------------------------------------------------------+
    N           Min           Max        Median           Avg        Stddev
x   5      27043602      27155718      27061257      27077267      44765.99
+   5      27546506      27623210      27550314      27566580     32283.352
Difference at 95.0% confidence
	489313 +/- 56918.6
	1.8071% +/- 0.212715%
	(Student's t, pooled s = 39027)
```
