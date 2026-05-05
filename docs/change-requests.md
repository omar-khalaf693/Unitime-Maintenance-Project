## Change Requests Description
##Bugs
1. Fix NullPointerException in Multiple Classes
Type: Bug Fix
Description: SonarQube detected NullPointerException risks in multiple classes including Debug.java (L47), ClassInstructorAssignmentForm.java (L172), SolverSettingsForm.java (L130), and TimeHint.java (L57) where nullable objects are used without null checks.
Motivation: These bugs cause system crashes at runtime affecting reliability. SonarQube reported 1,600 reliability issues in the codebase.

2. Fix XXE Vulnerability in XML Parsing
Type: Bug Fix
Description: SonarQube detected that XML parsing in multiple classes like DatabaseUpdate.java, BaseImport.java, and SolverInfo.java does not disable access to external entities, making the system vulnerable to XXE attacks.
Motivation: This is a High severity security vulnerability that can allow attackers to read internal files. SonarQube reported 120 security issues in the codebase.

3. Reduce High Cognitive Complexity in Methods
Type: Bug Fix
Description: SonarQube detected multiple methods with cognitive complexity exceeding the allowed limit of 15, including NaturalOrderComparator.java (L75 - complexity 27) and MultiComparable.java (L71 - complexity 16). These methods are difficult to understand and maintain.
Motivation: High cognitive complexity makes the code hard to maintain and increases the risk of introducing bugs during future changes. SonarQube reported 51,000 maintainability issues in the codebase.

4. Fix Unclosed Resources
Type: Bug Fix
Description: SonarQube detected multiple unclosed streams and resources such as FileOutputStream, InputStream, and BufferedReader in WikiGet.java (L76, L78) and DatabaseUpdate.java (L161) that are not properly closed using try-with-resources.
Motivation: Unclosed resources cause memory leaks that degrade system performance over time. Identified by SonarQube Reliability analysis.

##Features
1. Instructor Preferences

Type: New Feature

Description:
Add a feature that allows instructors to specify their preferred days and time slots for teaching. The system will consider these preferences during timetable generation.

Motivation:
This improves user satisfaction and increases scheduling efficiency by aligning generated timetables with instructor availability and preferences.


2. Export Timetable

Type: New Feature

Description:
Implement functionality to export the generated timetable into PDF or CSV format for external use.

Motivation:
This enhances usability by allowing users to share, print, or store timetables outside the system.


3. Room Capacity Validation

Type: New Feature

Description:
Add validation to ensure that the number of students assigned to a course does not exceed the capacity of the assigned room.

Motivation:
This prevents invalid scheduling scenarios and ensures that room assignments are realistic and consistent with physical constraints.

SonarQube reported missing validation checks across 
the codebase as part of its 51,000 maintainability issues.


4. Manual Schedule Adjustment
Type: New Feature

Description:
Allow administrators to manually adjust or override automatically generated timetables in case of special requirements or conflicts.

Motivation:
This feature provides flexibility to handle exceptional cases that cannot be resolved automatically by the system, improving usability and control.
