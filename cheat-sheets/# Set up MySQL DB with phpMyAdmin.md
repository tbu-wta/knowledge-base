# Set up MySQL DB with phpMyAdmin

## Administration
 * Alter tables and file versioning:
    major.minor[.build[.revision]]
    mynewproject-1.0.7.3
    major: tables are dropped
    minor: tables are created
    build: tables are altered
    version: minor revisions
 * Central Columns
    

## New DB
 * Database Name: 
    same as project name
    no delimiter
    mynewprojectdb
 * Collation:
    Sorting accuracy vs. performande
     __utf8_unicode_ci__: slightly less performaiv but more accurate
     utf8_general_ci: faster but less accurate
     specific language utf8: contain additional language rueles
 * Engine:
    MyISAM

## New Table
 * Name:
    Name of the table
    only small cahracters
    _ [undderscore] as delimiter
    package / project abriviation (2-3 litters) as prefix (MyNewProject)
    mnp_tablename
 * Number of columns:
    No. of fields to populate youre table

## Column Fields
 ### Name: 
    Name of the field
    only small characters
    _ [underscore] as delimiter
    table abbriviation (2-3 letters) as prefix (TabLeName)
    tln_fieldname
    use descriptive names
    avoide reserved words as unique, sort, etc.

 ### Type:
    1. Numeric
     * Exact Integer Types:
      * TINYINT [-128; 127][0; 125]
      * SMALLINT [-32768; 32767] [0; 65535]
      * MEDIUMINT [-8388608; 8388607] [0; 16777215]
      * INT [-2147483648; 2147483647] [0; 4294967295]
      * BIGINT [-9223372036854775808; 9223372036854775807] [0; 18446744073709551615]

    * Exact Fixed-Point Types:
     * DECIMAL [precision(M); scale(D)] M[1; 65]
      (Stores exacte numeric data values. Used, when it is important to preserve exact precision. Precisioin: number of significant digits; Scale: number of digits following the decimal point)
    * Approximate Float-Point Types
     * FLOAT [M,D] M[0; 23]
     * DOUBLE [M,D] M[24; 53]
     * REAL [Treated as a synonym for DOUBLE PRECISION, unless the REAL_AS_FLOAT SQL mode is enabled]

        BIT
        BOOLEAN
        SERIAL

    1. DATE TIME
     * Out of range or otherwise invalid value for a date or time type are automatically converted to “zero” value for that type
     * in a DATE or DATETIME column, day or month and day may be zero [1894-00-00] (NO_ZERO_IN_DATE mode must be disabled)
     * “relaxed” format for values specified as strings, in which any punctuation character may be used as the delimiter between date parts or time parts (2016:12:32 == 2016.12.31).
     * DATETIME and TIMESTAMP can include a trailing fractional seconds part in up to microseconds (6 digits) precision [YYYY-MM-DD HH:MM:SS[.fraction]. The fractional part should always be separated from the rest of the time by a decimal point.
     * TIMESTAMP and DATETIME data types offer automatic initialization and updating to the current date and time (Default: CURRENT_TIMESTAMP & Attributes: on update CURRENT_TIMESTAMP).

     * DATE
      * ['YYYY-MM-DD']
      * ['0000-00-00']
     * DATETIME
      * ['YYYY-MM-DD HH:MM:SS']
      * ['00:00:00']
     * TIMESTAMP
      * ['YYYY-MM-DD HH:MM:SS']
      * ['0000-00-00 00:00:00']
      * Converts current time to UTC for storage, and back to current time on retrieval
     * TIME ['0000-00-00 00:00:00']
     * YEAR [0000]

    1. STRING
     * CHAR & VARCHAR types are declared with a length that indicates the maximum number of characters you want to store (CHAR(30)).

     * CHAR ([0; 255])
      * fixed to the length declared (CAHR (4) == [___b])
      * length can be any value from 0 to 255
     * VARCHAR ([0; 65,535])
      * variable lenght sitrings (VARCHAR (4) == [b])
      * lenght can be any value from 0 to 65,535

    * TEXT
     * values are treated as nonbinary strings (character strings)
     * TINYTEXT [0; 255]
     * TEXT [0; 65,535]
     * MEDIUMTEXT [0; 16,777,215]
     * LONGTEXT [0; 4,294,967,295]

     * The BINARY and VARBINARY types are similar to CHAR and VARCHAR, except that they contain binary strings rather than nonbinary strings. That is, they contain byte strings rather than character strings. This means they have the binary character set and collation, and comparison and sorting are based on the numeric values of the bytes in the values

    * BLOB
     * values are treated as binary strings (byte strings).
     * The four BLOB Types are:
      * TINYBLOB
      * MEDIUMBLOB
      * BLOB
      * LONGBLOB
     * They have the binary character set and collation, and comparison and sorting are based on the numeric values of the bytes in column values.
     * The four BLOB types differ only in the maximum length of values they can hold.
     * They corrspond to the four TEXT types and have the same maximum lengths and storage requirements.

    * ENUM
     * String object with a value chosen from a list of permitted values that are enumerated explicitly in the column specification at table creation time.

    * SET
     * String object that can have zero or more values, each of which must be chosen from a list of permitted values specified when the table is created
     * Maximum of 64 distinct members
     

 ### Length/Values:
  * Set length of NUMERIC or STRING types;
  * Set Values for EMUM or SET types

    1. Numeric Types
     * specifying the display width of integer data types by left-padding them with spaces. The display width does not constrain the range of values that can be stored.

    1. STRING Types
     * Possible nummber of characters (M) is fixed to the defindet value.

    1. DATE TIME, TEXT and BLOB Types have predefined standard lenghts.

    1. ENUM / SET Types
     * Specifie the list values ['a', 'b', 'c', ...'zz'].



 ### Default:
  * default value for a column, in case it is left blank.
  * must be a constant; cannot be a function or an expression.
  * For TIMESTAMP and DATETIME types, CURRENT_TIMESTAMP can be defined as defauld value.
  * BLOB, TEXT, GEOMETRY, and JSON columns cannot be assigned a default value (use CHAR / VARCHAR).
  * For string types other than ENUM, the default value is the empty string.
  * For ENUM, the default is the first enumeration value.

 ### Collation:

 ### Attributes:
  1. Binary
   * the collation for the field will be binary, for example utf8_bin
  1. UNSIGNED
   * Used to permit only nonnegative numbers for INTEGER Float-Point Types
  1. UNSIGNED ZEROFILL
   * Pads the displayed value of the field with zeros up to the display width specified in the column definition.
   * Implies UNSIGNED
  1. on update CURRENT_TIMESTAMP
   * the value for a data type field has the current timestamp as its default value, and is automatically updated


 ### Null:
  * Allow a field to have no value. 
  * All fields except AUTO_INCREAMENT, TEXT, DATE (and similar) must be defined as NOT NULL DEFAULT 'value'

 ### Index:
 * Indexes are used to find rows with specific column values quickly.
 * Improves the performance of SELECT operations.
 * All fields in WHERE and ORDER BY should be defined as INDEX.
 * If text field (CHAR, VARCHAR) is used as index for larger tables (> 5000 records) should be always defined as CHAR.
 1. PRIMARY
  * Represents the column or set of columns that you use in your most vital queries.
  * Unique autoincremeted IDs
 1. UNIQUE
  * Creates a constraint such that all values in the index must be distinct.
  * Permits multiple NULL values for columns that can contain NULL.
 1. INDEX
  * Column is indexed for improved performance.
 1. FULLTEXT
  * Supported only for CHAR, VARCHAR, and TEXT columns.

 ### . A_I [AUTO_INCREMENT]
  * When inserting NULL in an indexed column, column is set to next sequence value
  * Typically value+1, where value is the largest value for the column currently in the table
  * Column must be declared NOT NULL

 ### Comments:
 * Comment about the fields, which will be included in the database sql code.

 ### Virtuality: 
 ### MIME type: 
 ### Browser display transformation:
 ### Browser display transformation options:
 ### Input transformation:
 ### Input transformation options:

