### awk
cat xrxs-waves-sql.log | awk -F time: '$2>20000 {print $2}'

-F 分隔符  

### sort && uniq
cat waves.log | sort | uniq -c 

### which
which java

	