# Data Sourcing Challenge
### Module 6 Challenge

#### __Part 1.__
* Request CME data from the NASA API
* Convert Data to json
* Convert Data to DataFrame keeping only 'activityID', 'startTime', and 'linkedEvents'
* Use for loops to iterate each row in the DataFrame and append the multiple value cells from the 'linkedEvents' column into new rows
* Store the expanded rows into a new DataFrame
* Create a function 'extract_activityID_from_dict()' to extract the activityID from the Linked events dictionary values and apply the new function with a lambda function, assigning the values to a new column 'GST_ActivityID'
* Drop rows with missing 'GST_ActivityID' values
* Convert 'GST_ActivityID' values into string format
* Convert 'startTime' values into datetime format and rename to 'startTime_CME'
* Rename 'activityID' column to 'cmeID'
* Drop the 'linkedEvents' column
* Check conversions
* Drop rows which do not contain the string "GST" from the 'GST_Activity' column

#### __Part 2.__
* Request GST data from the NASA API
* Convert Data to json
* Convert Data to DataFrame keeping only 'gstID', 'startTime', and 'linkedEvents'
* Use the explode() function to split multiple value cells from the 'linkedEvents' column into new rows
* Store the exploded rows into a new DataFrame
* Apply the extract_activityID_from_dict()' function to the gst exploded DataFrame, assigning to a new column 'CME_ActivityID'
* Drop rows with missing 'CME_ActivityID' values
* Convert 'CME_ActivityID' values into string format
* Convert 'gstID' values into string format
* Convert 'startTime' values into datetime format and rename to 'startTime_GST'
* Rename 'activityID' column to 'cmeID'
* Drop the 'linkedEvents' column
* Check conversions
* Drop rows which do not contain the string "CME" from the 'CME_Activity' column

#### __Part 3.__
* Merge both Datasets
* Verify the new DataFrame has the same number of rows
* Compute the time difference between 'startTime_GST' and 'startTime_CME', assigning the values to a new column 'timeDiff'
* Compute the mean and median time with the describe() function
* Print out the mean and median as a result
* Export data to a CSV file without the DataFrame's index