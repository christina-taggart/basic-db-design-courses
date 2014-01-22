[Imgur](http://i.imgur.com/bOeiej4.png)

<?xml version="1.0" encoding="utf-8" ?>
<!-- SQL XML created by WWW SQL Designer, http://code.google.com/p/wwwsqldesigner/ -->
<!-- Active URL: http://ondras.zarovi.cz/sql/demo/ -->
<sql>
<datatypes db="mysql">
  <group label="Numeric" color="rgb(238,238,170)">
    <type label="TINYINT" length="0" sql="TINYINT" quote=""/>
    <type label="SMALLINT" length="0" sql="SMALLINT" quote=""/>
    <type label="MEDIUMINT" length="0" sql="MEDIUMINT" quote=""/>
    <type label="INT" length="0" sql="INT" quote=""/>
    <type label="Integer" length="0" sql="INTEGER" quote=""/>
    <type label="BIGINT" length="0" sql="BIGINT" quote=""/>
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
</datatypes><table x="259" y="584" name="students">
<row name="id" null="1" autoincrement="1">
<datatype>TINYINT</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="315" y="369" name="classes">
<row name="id" null="1" autoincrement="1">
<datatype>TINYINT</datatype>
<default>NULL</default></row>
<row name="teacher_id" null="1" autoincrement="0">
<datatype>TINYINT</datatype>
<default>NULL</default><relation table="teachers" row="id" />
</row>
<row name="department_id" null="1" autoincrement="0">
<datatype>TINYINT</datatype>
<default>NULL</default><relation table="departments" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="285" y="264" name="teachers">
<row name="id" null="1" autoincrement="1">
<datatype>TINYINT</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="92" y="424" name="enrollment">
<row name="id" null="1" autoincrement="1">
<datatype>TINYINT</datatype>
<default>NULL</default></row>
<row name="section_id" null="1" autoincrement="0">
<datatype>TINYINT</datatype>
<default>NULL</default><relation table="sections" row="id" />
</row>
<row name="student_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="students" row="id" />
</row>
<row name="class_id" null="1" autoincrement="0">
<datatype>TINYINT</datatype>
<default>NULL</default><relation table="classes" row="id" />
</row>
<row name="grade" null="1" autoincrement="0">
<datatype>CHAR(2)</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
<key type="UNIQUE" name="">
<part>student_id</part>
<part>class_id</part>
</key>
</table>
<table x="88" y="232" name="sections">
<row name="id" null="1" autoincrement="1">
<datatype>TINYINT</datatype>
<default>NULL</default></row>
<row name="start" null="1" autoincrement="0">
<datatype>TIME</datatype>
<default>NULL</default></row>
<row name="end" null="1" autoincrement="0">
<datatype>TIME</datatype>
<default>NULL</default></row>
<row name="sched_MWF" null="1" autoincrement="0">
<datatype>BINARY</datatype>
<default>NULL</default></row>
<row name="class_id" null="1" autoincrement="0">
<datatype>TINYINT</datatype>
<default>NULL</default><relation table="classes" row="id" />
</row>
<row name="teacher_id" null="1" autoincrement="0">
<datatype>TINYINT</datatype>
<default>NULL</default><relation table="teachers" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="349" y="504" name="departments">
<row name="id" null="1" autoincrement="1">
<datatype>TINYINT</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
</sql>
