# SQL-Duplication-Scenario1
Eliminating Multiple Variable Duplication Using CTEs

This problem was provided as a skill assessment for a data warehousing project.  

Scenario 1
A school district database has an enrollment table (enrollment_table) that specifies when a particular student started and completed enrollment at a particular school (<null> in the leave_date field indicates that the student is currently still enrolled).  It also indicates the student’s guidance counselor during that period of time:
school_id	student_id	enrollment_id	entry_date	leave_date	counselor_name	record_change_date
4016	235876	12457680	8/10/2011	8/14/2011	C. Robinson	8/14/2011
4016	235876	12457681	8/15/2011	null	M. Thompson	8/20/2011
4016	235876	12457682	8/15/2011	null	J. Allen	8/18/2011
5815	734890	14472365	8/10/2011	9/20/2011	A. Jones	9/20/2011
5815	734890	14472366	9/21/2011	null	J. Allen	9/24/2011
5815	734890	14472367	9/21/2011	null	B. Rhodes	9/24/2011
5815	734890	14472368	9/21/2011	null	T. Smith	9/21/2011

Upon review, it is discovered that duplicate records exist in the system for the same enrollment periods, as shown above.  The requirement is to determine the student’s MOST RECENT guidance counselor for each unique enrollment period.  Per inquiry with the client, it is determined that in order to determine the most current record when duplication of enrollment date ranges exist, the record_change_date field should be used (e.g., the most recent record_change_date is the most current).  If duplication still exists, the highest numbered enrollment_id should be used in addition to record_change_date to determine the most current record.  Using a SQL SELECT statement, how would you remove duplicate enrollments to meet the requirement?  The result should look as follows:
school_id	student_id	enrollment_id	entry_date	leave_date	counselor_name
4016	235876	12457680	8/10/2011	8/14/2011	C. Robinson
4016	235876	12457681	8/15/2011	null	M. Thompson
5815	734890	14472365	8/10/2011	9/20/2011	A. Jones
5815	734890	14472367	9/21/2011	null	B. Rhodes

Feel free to use temporary tables or whatever means/syntax you are most comfortable with.  Please also add comments in the code to describe the logic/steps being performed.
