1. Creating a Pluggable Database (PDB)
- To create a new pluggable database (PDB), this example sets up a custom tablespace and admin user.

  CREATE PLUGGABLE DATABASE plsql_class2024db
ADMIN USER ke_plsqlauca IDENTIFIED BY MyPassword
DEFAULT TABLESPACE users
FILE_NAME_CONVERT = ('C:\app\HP\product\21c\oradata\XE\XEPDB1', 
                     'C:\app\HP\product\21c\oradata\XE\XEPDB1\plsql_class2024db');


2. Deleting a Pluggable Database (PDB)
- Before removing a PDB, make sure it's closed and placed in MOUNT mode.

- Step 1: Close the pluggable database
ALTER PLUGGABLE DATABASE my_pdb CLOSE IMMEDIATE;

- Step 2: Set the pluggable database to MOUNT mode
ALTER PLUGGABLE DATABASE my_pdb OPEN MOUNT;

- Step 3: Drop the pluggable database and delete its associated files
DROP PLUGGABLE DATABASE my_pdb INCLUDING DATAFILES;
                    

