### awk
cat xrxs-waves-sql.log | awk -F time: '$2>20000 {print $2}'

-F 分隔符  


### sort && uniq
cat waves.log | sort | uniq -c 

### which
which java


### 查看文件大小
du -sh *
	

### xargs
ls *.log | xargs rm -f


### 查

 | grep 'RecruitmentFlowListener'

cat error.log | grep 'dtalkPId is null'  |  awk -F messageId:  '{print $2}'| sort | uniq -c 

cat error.log|  awk -F messageId: '{print $2}'| sort | uniq -c 


cat error.log.2019-01-23* | grep 'nterviewBusiness' -C 20 | awk -F interviewJob '{print $2}' | awk -F interviewTimeDate '{print $1}'


cat error.log.2019-01-23* | grep 'ajaxAddInterview方法' | grep 'dtalkPId is null' | awk -F '01-23' '{print $2}' | awk -F '[qtp' '{print $1}'


















