```XML

<?xml version="1.0" encoding="utf-8" ?>
<!-- SQL XML created by WWW SQL Designer, http://code.google.com/p/wwwsqldesigner/ -->
<!-- Active URL: https://socrates.devbootcamp.com/sql -->
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
</datatypes><table x="26" y="523" name="Students">
<row name="id" null="1" autoincrement="1">
  <datatype>INTEGER</datatype>
  <default>NULL</default></row>
  <row name="first_name" null="1" autoincrement="0">
    <datatype>VARCHAR</datatype>
    <default>NULL</default></row>
    <row name="last_name" null="1" autoincrement="0">
      <datatype>VARCHAR</datatype>
      <default>NULL</default></row>
      <key type="PRIMARY" name="">
        <part>id</part>
      </key>
    </table>
    <table x="431" y="282" name="Classes">
      <row name="id" null="1" autoincrement="1">
        <datatype>INTEGER</datatype>
        <default>NULL</default></row>
        <row name="title" null="1" autoincrement="0">
          <datatype>VARCHAR</datatype>
          <default>NULL</default></row>
          <row name="department_id" null="1" autoincrement="0">
            <datatype>INTEGER</datatype>
            <default>NULL</default><relation table="departments" row="id" />
          </row>
          <row name="true_class_id" null="1" autoincrement="0">
            <datatype>INTEGER</datatype>
            <default>NULL</default><relation table="true_classes" row="id" />
          </row>
          <key type="PRIMARY" name="">
            <part>id</part>
          </key>
        </table>
        <table x="679" y="504" name="Teachers">
          <row name="id" null="1" autoincrement="1">
            <datatype>INTEGER</datatype>
            <default>NULL</default></row>
            <row name="first_name" null="1" autoincrement="0">
              <datatype>VARCHAR</datatype>
              <default>NULL</default></row>
              <row name="last_name" null="1" autoincrement="0">
                <datatype>VARCHAR</datatype>
                <default>NULL</default></row>
                <key type="PRIMARY" name="">
                  <part>id</part>
                </key>
              </table>
              <table x="188" y="386" name="Grades">
                <row name="id" null="1" autoincrement="1">
                  <datatype>INTEGER</datatype>
                  <default>NULL</default></row>
                  <key type="PRIMARY" name="">
                    <part>id</part>
                  </key>
                </table>
                <table x="200" y="522" name="sections_students">
                  <row name="id" null="1" autoincrement="1">
                    <datatype>INTEGER</datatype>
                    <default>NULL</default></row>
                    <row name="student_id" null="1" autoincrement="0">
                      <datatype>INTEGER</datatype>
                      <default>NULL</default><relation table="Students" row="id" />
                    </row>
                    <row name="section_id" null="1" autoincrement="0">
                      <datatype>INTEGER</datatype>
                      <default>NULL</default><relation table="sections" row="id" />
                    </row>
                    <row name="grade_id" null="1" autoincrement="0">
                      <datatype>INTEGER</datatype>
                      <default>NULL</default><relation table="Grades" row="id" />
                    </row>
                    <key type="PRIMARY" name="">
                      <part>id</part>
                    </key>
                  </table>
                  <table x="430" y="491" name="sections">
                    <row name="id" null="1" autoincrement="1">
                      <datatype>INTEGER</datatype>
                      <default>NULL</default></row>
                      <row name="class_id" null="1" autoincrement="0">
                        <datatype>INTEGER</datatype>
                        <default>NULL</default></row>
                        <row name="start_time" null="1" autoincrement="0">
                          <datatype>TIME</datatype>
                          <default>NULL</default></row>
                          <row name="stop_time" null="1" autoincrement="0">
                            <datatype>TIME</datatype>
                            <default>NULL</default></row>
                            <row name="weekly_schedule" null="1" autoincrement="0">
                              <datatype>VARCHAR</datatype>
                              <default>NULL</default></row>
                              <row name="teacher_id (UNIQUE)" null="1" autoincrement="0">
                                <datatype>INTEGER</datatype>
                                <default>NULL</default><relation table="Teachers" row="id" />
                              </row>
                              <row name="true_class_id" null="1" autoincrement="0">
                                <datatype>INTEGER</datatype>
                                <default>NULL</default><relation table="true_classes" row="id" />
                              </row>
                              <key type="PRIMARY" name="">
                                <part>id</part>
                              </key>
                            </table>
                            <table x="228" y="131" name="departments">
                              <row name="id" null="1" autoincrement="1">
                                <datatype>INTEGER</datatype>
                                <default>NULL</default></row>
                                <row name="name" null="1" autoincrement="0">
                                  <datatype>VARCHAR</datatype>
                                  <default>NULL</default></row>
                                  <key type="PRIMARY" name="">
                                    <part>id</part>
                                  </key>
                                </table>
                                <table x="614" y="395" name="true_classes">
                                  <row name="id" null="1" autoincrement="1">
                                    <datatype>INTEGER</datatype>
                                    <default>NULL</default></row>
                                    <key type="PRIMARY" name="">
                                      <part>id</part>
                                    </key>
                                  </table>
                                </sql>

```