###Enforcing time constraints

Enforcing time constraints (that is, students can't attend and teachers can't teach two sections whose times overlap,) could be approached in two different ways. The two approaches offer an
example of the typical memory/processing tradeoff.

First, the time constraints could be hard-coded into the database itself. We could create a
table 'students_schedules' that had fields that store student_id, start_time, end_time, and
day_block. We could then turn these fields into combined primary keys to ensure that there are
unique combinations of each field, thereby enforcing time constraints for each student. The
drawback to this approach is that it requires the duplication of existing data (start_time,
end_time, etc.)

It would also be possible to enforce time constraints using Ruby.  Essentially when a student would "enroll" in a section of a course, the program would check all of that student's existing courses, then check the day/time information for each course and ensure that there were no identical combinations of data for a particular student.  The advantage to this approach is that it saves memory by not duplicating data, however it would obviously take more processing power to accomplish.

###Table Design

```xml
<?xml version="1.0" encoding="utf-8" ?>
<!-- SQL XML created by WWW SQL Designer, http://code.google.com/p/wwwsqldesigner/ -->
<!-- Active URL: https://socrates.devbootcamp.com/sql.html -->
<sql>
<datatypes db="mysql">
  <group label="Numeric" color="rgb(238,238,170)">
    <type label="Integer" length="0" sql="INTEGER" re="INT" quote=""/>
    <type label="Decimal" length="1" sql="DECIMAL" re="DEC" quote=""/>
    <type label="Single precision" length="0" sql="FLOAT" quote=""/>
    <type label="Double precision" length="0" sql="DOUBLE" re="DOUBLE" quote=""/>
  </group>

  <group label="Character" color="rgb(255,200,200)">
    <type label="Char" length="1" sql="CHAR" quote="'"/>
    <type label="Varchar" length="1" sql="VARCHAR" quote="'"/>
    <type label="Text" length="0" sql="MEDIUMTEXT" re="TEXT" quote="'"/>
    <type label="Binary" length="1" sql="BINARY" quote="'"/>
    <type label="Varbinary" length="1" sql="VARBINARY" quote="'"/>
    <type label="BLOB" length="0" sql="BLOB" re="BLOB" quote="'"/>
  </group>

  <group label="Date &amp; Time" color="rgb(200,255,200)">
    <type label="Date" length="0" sql="DATE" quote="'"/>
    <type label="Time" length="0" sql="TIME" quote="'"/>
    <type label="Datetime" length="0" sql="DATETIME" quote="'"/>
    <type label="Year" length="0" sql="YEAR" quote=""/>
    <type label="Timestamp" length="0" sql="TIMESTAMP" quote="'"/>
  </group>

  <group label="Miscellaneous" color="rgb(200,200,255)">
    <type label="ENUM" length="1" sql="ENUM" quote=""/>
    <type label="SET" length="1" sql="SET" quote=""/>
    <type label="Bit" length="0" sql="bit" quote=""/>
  </group>
</datatypes><table x="41" y="258" name="students">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="name" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="year" null="1" autoincrement="0">
<datatype>YEAR</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="733" y="272" name="courses">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="professor_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="professors" row="id" />
</row>
<row name="department_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="departments" row="id" />
</row>
<row name="course_title" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="required_books" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
<part>professor_id</part>
</key>
</table>
<table x="241" y="472" name="student_grades">
<row name="student_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="students" row="id" />
</row>
<row name="section_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="sections" row="id" />
</row>
<row name="grade_percentage" null="1" autoincrement="0">
<datatype>DECIMAL</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>student_id</part>
<part>section_id</part>
</key>
</table>
<table x="734" y="468" name="professors">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="department_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="departments" row="id" />
</row>
<row name="name" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="518" y="309" name="sections">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="course_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="courses" row="id" />
</row>
<row name="start_time" null="1" autoincrement="0">
<datatype>TIME</datatype>
<default>NULL</default></row>
<row name="end_time" null="1" autoincrement="0">
<datatype>TIME</datatype>
<default>NULL</default></row>
<row name="day_block" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="255" y="149" name="sections_students">
<row name="student_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="students" row="id" />
</row>
<row name="section_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="sections" row="id" />
</row>
<row name="course_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="courses" row="id" />
</row>
<key type="PRIMARY" name="">
<part>student_id</part>
<part>course_id</part>
</key>
</table>
<table x="697" y="130" name="departments">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="department_name" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
</sql>

```