Solutions Considered:
Manual Log Extraction: This approach involved manually searching and copying logs for specific dates. However, it was inefficient and impractical for large log files.
Using Command-Line Tools: Tools like grep were considered for date-based filtering, but they lacked cross-platform compatibility and customization options.
Automated Python Script: This solution offered flexibility, better error handling, and maintainability. It also allowed for custom buffer sizes and organized output management.
Final Solution Summary:
The automated Python script was chosen as the final solution due to its efficiency, platform independence, and ease of maintenance. It allows users to extract logs by date with minimal 
effort while providing clear error handling and organized output files. Additionally, to test the extraction tool, a log generator script was implemented to create synthetic log data. This 
combination ensures reliable validation and testing of the extraction functionality.


Im attachinng the sample output below 
2024-12-01 07:45:52 DEBUG User logged out
2024-12-01 04:32:08 DEBUG Unauthorized access attempt
2024-12-01 19:13:27 INFO Database query executed
2024-12-01 23:37:11 WARN File not found
2024-12-01 03:02:03 DEBUG Database query executed
2024-12-01 10:31:50 WARN Server restarted successfully
2024-12-01 21:41:06 ERROR Database query executed
2024-12-01 05:50:57 DEBUG Unauthorized access attempt
2024-12-01 17:15:25 INFO User logged out
2024-12-01 10:26:25 DEBUG User logged out
2024-12-01 01:02:48 ERROR Unauthorized access attempt
2024-12-01 07:13:43 ERROR User logged out
2024-12-01 21:38:29 WARN Server restarted successfully
2024-12-01 02:06:20 WARN Memory usage high
2024-12-01 01:04:47 DEBUG User logged out
2024-12-01 15:49:29 WARN Connection timeout
2024-12-01 01:14:49 WARN Connection timeout
