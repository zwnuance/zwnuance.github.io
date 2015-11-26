quartz
====
表达式总共7位,不同于**linux crontab**

    Seconds Minutes Hours Day-of-Month Month Day-of-Week Year

position | unit        | remark
-------- | ----------- | ----------------------
1        | Seconds     | 用数字0－59 表示
2        | Minutes     | 用数字0－59 表示
3        | Hours       | 用数字0-23表示
4        |Day-of-Month | 用数字1-31 中的任一一个值，但要注意一些特别的月份
5        | Month       | 用数字0-11 或用字符串  “JAN, FEB, MAR, APR, MAY, JUN, JUL, AUG, SEP, OCT, NOV and DEC” 表示
6        | Day-of-Week | 用数字1-7表示（1 ＝ 星期日）或用字符口串“SUN, MON, TUE, WED, THU, FRI and SAT”表示
7        |  Year       | 年份，可选

“/”：为特别单位，表示为“每”如“0/15”表示每隔15分钟执行一次,“0”表示为从“0”分开始, “3/20”表示表示每隔20分钟执行一次，“3”表示从第3分钟开始执行

“?”：表示每月的某一天，或第周的某一天

“L”：用于每月，或每周，表示为每月的最后一天，或每个月的最后星期几如“6L”表示“每月的最后一个星期五”

“W”：表示为最近工作日，如“15W”放在每月（day-of-month）字段上表示为“到本月15日最近的工作日”

““#”：是用来指定“的”每月第n个工作日,例 在每周（day-of-week）这个字段中内容为"6#3" or "FRI#3" 则表示“每月第三个星期五”
