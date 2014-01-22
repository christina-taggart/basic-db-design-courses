!(http://i.imgur.com/1cRKnOe.png)

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
    </datatypes><table x="355" y="154" name="students">
    <row name="id" null="1" autoincrement="1">
    <datatype>INTEGER</datatype>
    <default>NULL</default></row>
    <row name="first_name" null="1" autoincrement="0">
    <datatype>VARCHAR</datatype>
    <default>NULL</default></row>
    <row name="last_name" null="1" autoincrement="0">
    <datatype>VARCHAR</datatype>
    <default>NULL</default></row>
    <row name="birthday" null="1" autoincrement="0">
    <datatype>DATE</datatype>
    <default>NULL</default></row>
    <row name="phone" null="1" autoincrement="0">
    <datatype>VARCHAR</datatype>
    <default>NULL</default></row>
    <row name="created_at" null="1" autoincrement="0">
    <datatype>TIMESTAMP</datatype>
    <default>NULL</default></row>
    <row name="updated_at" null="1" autoincrement="0">
    <datatype>TIMESTAMP</datatype>
    <default>NULL</default></row>
    <key type="PRIMARY" name="">
    <part>id</part>
    </key>
    </table>
    <table x="578" y="50" name="students_class_sections">
    <row name="id" null="1" autoincrement="1">
    <datatype>INTEGER</datatype>
    <default>NULL</default></row>
    <row name="student_id" null="1" autoincrement="0">
    <datatype>INTEGER</datatype>
    <default>NULL</default><relation table="students" row="id" />
    </row>
    <row name="course_id" null="1" autoincrement="0">
    <datatype>INTEGER</datatype>
    <default>NULL</default><relation table="classes" row="id" />
    </row>
    <row name="section_id" null="1" autoincrement="0">
    <datatype>INTEGER</datatype>
    <default>NULL</default><relation table="classes_sections" row="id" />
    </row>
    <row name="created_at" null="1" autoincrement="0">
    <datatype>TIMESTAMP</datatype>
    <default>NULL</default></row>
    <row name="updated_at" null="1" autoincrement="0">
    <datatype>TIMESTAMP</datatype>
    <default>NULL</default></row>
    <key type="PRIMARY" name="">
    <part>id</part>
    <part>student_id</part>
    <part>course_id</part>
    </key>
    <key type="INDEX" name="">
    <part>student_id</part>
    <part>course_id</part>
    </key>
    </table>
    <table x="566" y="250" name="students_grades">
    <row name="id" null="1" autoincrement="1">
    <datatype>INTEGER</datatype>
    <default>NULL</default></row>
    <row name="student_id" null="1" autoincrement="0">
    <datatype>INTEGER</datatype>
    <default>NULL</default><relation table="students" row="id" />
    </row>
    <row name="section_id" null="1" autoincrement="0">
    <datatype>INTEGER</datatype>
    <default>NULL</default><relation table="classes_sections" row="id" />
    </row>
    <row name="grade" null="1" autoincrement="0">
    <datatype>DECIMAL</datatype>
    <default>NULL</default></row>
    <row name="created_at" null="1" autoincrement="0">
    <datatype>TIMESTAMP</datatype>
    <default>NULL</default></row>
    <row name="updated_at" null="1" autoincrement="0">
    <datatype>TIMESTAMP</datatype>
    <default>NULL</default></row>
    <key type="PRIMARY" name="">
    <part>id</part>
    </key>
    </table>
    <table x="1099" y="36" name="classes">
    <row name="id" null="1" autoincrement="1">
    <datatype>INTEGER</datatype>
    <default>NULL</default></row>
    <row name="department_id" null="1" autoincrement="0">
    <datatype>INTEGER</datatype>
    <default>NULL</default><relation table="departments" row="id" />
    </row>
    <row name="name" null="1" autoincrement="0">
    <datatype>VARCHAR</datatype>
    <default>NULL</default></row>
    <row name="created_at" null="1" autoincrement="0">
    <datatype>TIMESTAMP</datatype>
    <default>NULL</default></row>
    <row name="updated_at" null="1" autoincrement="0">
    <datatype>TIMESTAMP</datatype>
    <default>NULL</default></row>
    <key type="PRIMARY" name="">
    <part>id</part>
    </key>
    </table>
    <table x="1208" y="244" name="teachers">
    <row name="id" null="1" autoincrement="1">
    <datatype>INTEGER</datatype>
    <default>NULL</default></row>
    <row name="first_name" null="1" autoincrement="0">
    <datatype>VARCHAR</datatype>
    <default>NULL</default></row>
    <row name="last_name" null="1" autoincrement="0">
    <datatype>VARCHAR</datatype>
    <default>NULL</default></row>
    <row name="birthday" null="1" autoincrement="0">
    <datatype>DATE</datatype>
    <default>NULL</default></row>
    <row name="phone" null="1" autoincrement="0">
    <datatype>VARCHAR</datatype>
    <default>NULL</default></row>
    <row name="created_at" null="1" autoincrement="0">
    <datatype>TIMESTAMP</datatype>
    <default>NULL</default></row>
    <row name="updated_at" null="1" autoincrement="0">
    <datatype>TIMESTAMP</datatype>
    <default>NULL</default></row>
    <key type="PRIMARY" name="">
    <part>id</part>
    </key>
    </table>
    <table x="879" y="198" name="classes_sections">
    <row name="id" null="1" autoincrement="1">
    <datatype>INTEGER</datatype>
    <default>NULL</default></row>
    <row name="class_id" null="1" autoincrement="0">
    <datatype>INTEGER</datatype>
    <default>NULL</default><relation table="classes" row="id" />
    </row>
    <row name="teacher_id" null="1" autoincrement="0">
    <datatype>INTEGER</datatype>
    <default>NULL</default><relation table="teachers" row="id" />
    </row>
    <row name="start_time" null="1" autoincrement="0">
    <datatype>TIME</datatype>
    <default>NULL</default></row>
    <row name="end_time" null="1" autoincrement="0">
    <datatype>TIME</datatype>
    <default>NULL</default></row>
    <row name="start_date" null="1" autoincrement="0">
    <datatype>DATE</datatype>
    <default>NULL</default></row>
    <row name="end_date" null="1" autoincrement="0">
    <datatype>DATE</datatype>
    <default>NULL</default></row>
    <row name="schedule_block" null="1" autoincrement="0">
    <datatype>VARCHAR</datatype>
    <default>NULL</default></row>
    <row name="created_at" null="1" autoincrement="0">
    <datatype>TIMESTAMP</datatype>
    <default>NULL</default></row>
    <row name="updated_at" null="1" autoincrement="0">
    <datatype>TIMESTAMP</datatype>
    <default>NULL</default></row>
    <key type="PRIMARY" name="">
    <part>id</part>
    <part>teacher_id</part>
    <part>class_id</part>
    </key>
    <key type="INDEX" name="">
    <part>class_id</part>
    </key>
    </table>
    <table x="1291" y="67" name="departments">
    <row name="id" null="1" autoincrement="1">
    <datatype>INTEGER</datatype>
    <default>NULL</default></row>
    <row name="name" null="1" autoincrement="0">
    <datatype>VARCHAR</datatype>
    <default>NULL</default></row>
    <row name="created_at" null="1" autoincrement="0">
    <datatype>TIMESTAMP</datatype>
    <default>NULL</default></row>
    <row name="updated_at" null="1" autoincrement="0">
    <datatype>TIMESTAMP</datatype>
    <default>NULL</default></row>
    <key type="PRIMARY" name="">
    <part>id</part>
    </key>
    </table>
    </sql>
