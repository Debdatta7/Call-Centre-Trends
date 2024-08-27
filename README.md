# Call-Centre-Trends
Pwc Power BI Virtual Work - Task 1
### **Problem Statement:**
In this project, create a dashboard in power bi for the call centre manager that reflects all relevant Key performance indicators (Kpi) and metrics in datasets.

### Datasource :
Dataset used for this task was presented by Pwc.
* Dataset: Call centre trends

### **Possible kpi indicators:**
* Overall customer satisfaction
* Overall calls answered/abandoned
* Calls by time
* Average speed of answer
* Agent’s performance quadrant -> average handle time (talk duration) vs calls answered

### **Data analysis (DAX):**
* **Average of speed of answered** = AVERAGE('call centre trends'[Speed of answer in seconds])

* **Average of satisfaction** = AVERAGE('call centre trends'[Satisfaction rating])

* **Count satisfaction rating** = COUNT('call centre trends'[Satisfaction rating])

* **Overall Customer Satisfaction** = DIVIDE([Positive satisfaction rating],[Count satisfaction rating],0)

* **Positive satisfaction rating** = CALCULATE(COUNT('call centre trends'[Satisfaction rating]),FILTER('call centre trends','call centre trends'[Satisfaction rating] IN {4,5}))

* **Resolved calls** = COUNTX(FILTER('call centre trends','call centre trends'[Resolved] = "Yes"), 'call centre trends'[Resolved])

* **Unresolved calls** = COUNTX(FILTER('call centre trends','call centre trends'[Resolved] = "No"), 'call centre trends'[Resolved])

* **Total calls** = CALCULATE('Table'[total calls answered] + 'Table'[total calls unanswered])

* **Total calls answered** = COUNTX(FILTER('call centre trends','call centre trends'[Answered (Y/N)] = "Yes"),'call centre trends'[Answered (Y/N)])

* **Total calls unanswered** =COUNTX(FILTER('call centre trends','call centre trends'[Answered (Y/N)] = "No"), 'call centre trends'[Answered (Y/N)])


### **Insights:** 
* Most of the satisfaction ratings from each call are 3 and 4.
* The average satisfaction rating has decreased over the span of three months. January brought the highest satisfaction rating and March the lowest.
* The percentage of issues resolved in January was the highest, with a dip in February. It increased again in march.
* The majority of calls come in the morning.
* The average speed of answer by Joe is the highest.
* The call resolution rate of Jim is the highest, even though the average speed of his answers is lower compared to those of Joe, Martha and Dan. The calls answered by - him are also higher than the average number of calls answered.
* Becky's speed of answer is the lowest among all, and her rate of calls resolved is higher. She is in the 5th position in the call resolution rate.
* Martha has the highest speed of answered in the sec

