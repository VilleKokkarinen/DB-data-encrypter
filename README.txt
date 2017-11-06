
 README / MANUAL
 DATABASE -DATA, ENCRYPTING SOFTWARE

 Here we go through every setting, found in "settings.json".

>>> Please consider reading and filling the settings file properly before executing this program. <<<
  
>>  If you "accidentally" encrypt vital files from the database you may corrupt your database. <<
 

> If you encrypt your database with a faulty password / forget your password,
> there is a chance you end up encrypting your data as a 1 way ticket, without a chance to regain the data.


> If you have a copy of the RECOVERY_KEYS.txt, that will be generated to the root folder with a time stamp
> It is possible to recover the Hash Password by
> sending your RECOVERY_KEY.txt LOG / specified key to the email address of the author given below.


Creator, Owner, Developer, Author - Kokkarinen Ville


kokkarinen.ville@gmail.com






1_______________________________________________________________________________________________________________
 Encrypt & Decrypt

 When encrypt is set as "true", attempts to encrypt data
      ¯¯¯¯¯¯¯                               ¯¯¯¯¯¯¯
 When decrypt is set as "true", attempts to decrypt data
      ¯¯¯¯¯¯¯                               ¯¯¯¯¯¯¯
 Both cannot be true, nor false, at the same time.

 Type: Boolean

 Encrypt = true
 Encrypt = false
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯



2_______________________________________________________________________________________________________________
 EditShortFields

 When EditShortFields is set as "true",
 will also edit fields that are too short to receive encrypted data back,
 with the value defined at "ValueForShortFields".

 Type: Boolean

 EditShortFields = true
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯



3_______________________________________________________________________________________________________________
 ValueForShortFields

 When EditShortFields is set as "true" and "ValueForShortFields" has a value,
 edits fields that are too short to receive encrypted data back,
 with the value defined at "ValueForShortFields".
 
 Type: String

 ValueForShortFields = "XYZ"
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯



4_______________________________________________________________________________________________________________
 Connectionstring

 Required to connect to a database
 ¯¯¯¯¯¯¯¯
 Example. connectionstring:
 "User ID=sysdba;Password=admin;Database=192.168.0.1:C:/Databases/Database.fdb;Datasource=192.168.0.1;"

 Type: string

 connectionstring = ""
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯



5_______________________________________________________________________________________________________________
 HashingPassword

 Password used to SHA256 hash data
 ¯¯¯¯¯¯¯¯
 Must be atleast 8 characters long
 ¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
 Not necessary but preferably, 10+ characters long with 3 or more of the following categories:
 - Contains UPPERCASE letters
 - Contains lowercase letters
 - Contains numerals 0-9
 - Contains special characters: !"¤%&/ etc.
 - Contains characters, which are not found on a keyboard, and can be generated
   with certain ALT + number combinations.

 Type: string

 HashingPassword = "admin123!"
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯



6_______________________________________________________________________________________________________________
 TableNames
 
 Array of tables, to encrypt / decrypt
          ¯¯¯¯¯¯
 The program fetches all tables from the database, and then removes all tables which are not defined here
 
 Note that each field requires a comma, if there is another record after it.
 
 "TableNames":[
 "table1",
 "table2",
 "table3"
 ]
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯



7_______________________________________________________________________________________________________________
 ColumnNames
 
 Array of columns to encrypt/decrypt
          ¯¯¯¯¯¯¯
 The program fetches all columns from the database, and then removes all columns,
 which are not defined here, or their table is not defined in the TableNames array

 > Means that only the columns are modified, which are found in the tables from TableNames array,
 > and the column name matches a value in ColumnNames array.
 

 Note that each field requires a comma, if there is another record after it.
 
 "ColumnNames": [
 "Column1",
 "Column2",
 "Column3"
 ]
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯

