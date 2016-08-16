##Syria Program Map Workflow

###Activity Numbers
In R:  
**National Level Initiatives**
  - Completed and Ongoing:   
  `length(unique(subset(programs,Place=="National" & (status == "Completed" | status == "Closed" | status == "Cleared"))$activityNumber))`
  - Pending:  
  `length(unique(subset(programs,Place=="National" & status == "Pending")$activityNumber))`
  
**Local Or Provincial Councils**
  - Completed and Ongoing:  
  `length(unique(subset(programs,Place!="National" & (status == "Completed" | status == "Closed" | status == "Cleared"))$activityNumber))`
  - Pending:  
  `length(unique(subset(programs,Place!="National" & status == "Pending")$activityNumber))`  
