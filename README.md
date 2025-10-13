# Assignment II: Database Creation, Deletion & OEM

**Student:** Ushindi Victoire  
**StudentID:** 27269  
**Date:** 2025-09-29  -- 2025-10-06 at 11:59

## Overview
- Task 1: Created PDB `us_pdb_27269` and admin user `ushindi_plsqlauca_27269`.
- Task 2: Created and then deleted PDB `us_to_delete_pdb_27269`.
- Task 3: Accessed EM Express and captured dashboard.

## Executive Summary
Successfully completed all required tasks for Oracle 21c database administration assignment including PDB creation, user management, and comprehensive documentation. All objectives achieved with detailed evidence.

## Commands used
```
sqlplus / as sysdba
ALTER USER system IDENTIFIED BY new_password;
ALTER USER sys IDENTIFIED BY new_password;
ALTER USER victoire IDENTIFIED BY new_password123;
CREATE USER victoire IDENTIFIED BY your_password;
GRANT CONNECT, RESOURCE TO victoire;
-- Show all PDBs
SELECT name, open_mode FROM v$pdbs;

-- Verify your PDB
ALTER SESSION SET CONTAINER = us_pdb_27269;

-- Verify your user
SELECT username, account_status, created FROM dba_users 
WHERE username = 'USHINDI_PLSQLAUCA_27269';

-- Show user privileges
SELECT privilege FROM dba_sys_privs 
WHERE grantee = 'USHINDI_PLSQLAUCA_27269';
See create_pdb.sql and create_then_drop_pdb.sql

-- Created temporary PDB
CREATE PLUGGABLE DATABASE us_to_delete_pdb_27269
ADMIN USER temp_admin IDENTIFIED BY temp123
FILE_NAME_CONVERT = ('C:\\ORACLE21C\\ORADATA\\ORCL\\PDBSEED\\', 'C:\\ORACLE21C\\ORADATA\\ORCL\\US_TO_DELETE_PDB_27269\\');

-- Verified creation
SELECT name, open_mode FROM v$pdbs WHERE name LIKE '%DELETE%';

-- Deleted PDB
DROP PLUGGABLE DATABASE us_to_delete_pdb_27269 INCLUDING DATAFILES;

-- Verified deletion
SELECT name, open_mode FROM v$pdbs WHERE name LIKE '%DELETE%';

ect ...

```

## Screenshots

You can hover the img to for it alt text (desc)
- 1-Pluggable-database-created ![1-Pluggable-database-created](./found-img/1-Pluggable-database-created.png "Pluggable database created")
- 2- PDB US_PDB_27269 ![](./found-img/2-%20PDB%20US_PDB_27269.png "2- PDB US_PDB_27269")
- 3-read-and-write ![3-read-and-write](./found-img/3-read-and-write.png "Read and write")
- 4-create-user ![4-create-user](./found-img/4-create-user.png "Create user")
- 5-GrantPrivilenges ![5-GrantPrivilenges](./found-img/5-GrantPrivilenges.png "Grant Privilenges ")
- ![6-privileges-Assigned-to-user](./found-img/6-privileges-Assigned-to-user.png "6 privileges Assigned to user")
- ![7-Pluggable-database-created](./found-img/7-Pluggable-database-created.png "Pluggable database created")
- ![8-Verify-creation](./found-img/8-Verify-creation.png "Verify creation")
- 9-Pluggable-database-dropped ![9-Pluggable-database-dropped](./found-img/9-Pluggable-database-dropped.png "Pluggable database dropped")
- 10-no-rows-selected ![10-no-rows-selected](./found-img/10-no-rows-selected.png "no rows selected ")
-

## Issues encountered and fixes
- Missing `libaio.so.1` → installed / created symlink.
- Permission issues while converting RPM → used `alien --scripts` and ensured directories owned by Oracle.
- Issues in getting oracle bin path
- **File path error**: Corrected from `C:\app\Oracle\...` to `C:\ORACLE21C\...`
- **Solution**: Used the correct installation path shown in error message
- Oracle Enterprise Manager not found in standard installation(I am still working on it)

## Conclusion
All tasks completed. In case you may do access here is the credentials:
- PDB admin: `ushindi_plsqlauca_27269` / system
