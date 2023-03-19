# sql_project_1

I designed a relational database using SQL, which was inspired by the SEN2 Return. The database includes tables that contain information related to individuals aged 0-25 who are receiving education and have EHCPs, as well as information about their parents, schools, whether students are a lac, and the support and funding they receive during provision panels. The primary objective of this database is to enable data-driven decisions that can improve educational outcomes for these individuals. All pieces of information are fictional and most personal data is loosely based on our current demographics in England. 

The ERD diagram shows seven main tables in the database: “students”, “parents”, “officers”, “schools”, “panel_provisions”, “lac_information”, “sen_needs”, and “band”.

Brief description of each entity:
 “students”, table contains information about individual students such as forename, lastname, date of birth, gender ethincity, post code, attendence via a foreign key (school_id).
“parents”, table contains information about the parents or guardians of individual students, such as their forename, lastname, relationship to the student, language spoken, employment status, and contact number. Each parent has a unique identifier (parent_id) and is associated with one or more students via a foreign key (student_id) in the "students" table.
 “officers”, table contains information about individual officers such as first name, last name, and email and an unique identify (officer_id).
“schools”, table contains information about schools such as name, address, contact information and type of school, each has a unique identifier (school_id) and associated with multiple officers via foreign key (officer_id)
“panel_provisions”, table contains information about panels with a unique identifier (panel_id) such as panel_date, panel_outcome (whether it was agreed or disagreed), and associated with a band_id, officer_id and student_id.
 “lac_information”, table contains information about students by foreign key (students.student_id) who are LAC by the LA, including looked after status, legal status, social worker and their LA.
“sen_needs”, table contains information about SEN (Special Educational Needs) of each student including primary and secondary needs. It also includes schools_id column that references schools table. 
“band” contains information about the funding bands allocated to students with EHCPs, including the band ID, band amount.



Relationships between entities:

The “parents” have N - M relationship with “students” since students can have multiple parents, and parents can have multiple children.
The “officers” have 1 - M relationship with “students” since officers are allocated to students, but only one student can have one officer.
The “schools” have 1 - M  relationship with officers since officers are allocated multiple schools but schools can’t have multiple officers.
Students can be associated with more than one school and each school can be associated with multiple students.
Each panel provision is associated with one student, one officer, and one funding band, but one student and one officer can have multiple panel provisions.
Each student in the LAC information table has only one entry, but each entry can be associated with multiple students.
Students are limited to 2 sen needs but sen needs can go to multiple students.
Each student with an EHCP in the band table is associated with one funding band, but one funding band can be associated with multiple students.
