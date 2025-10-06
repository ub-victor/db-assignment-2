# Assignment II: Database Creation, Deletion & OEM

**Student:** Ushindi Victoire  
**StudentID:** 27269  
**Date:** 2025-09-29  -- 2025-10-06 at 11:59

## Overview
- Task 1: Created PDB `us_pdb_27269` and admin user `ushindi_plsqlauca_27269`.
- Task 2: Created and then deleted PDB `us_to_delete_pdb_27269`.
- Task 3: Accessed EM Express and captured dashboard.

## Commands used
(See create_pdb.sql and create_then_drop_pdb.sql)

## Screenshots
- Task1: `screenshots/task1_create_pdb.png`
- Task2 created: `screenshots/task2_create_to_delete.png`
- Task2 deleted: `screenshots/task2_after_delete.png`
- Task3 OEM: `screenshots/task3_oem_dashboard.png`

## Issues encountered and fixes
- Missing `libaio.so.1` → installed / created symlink.
- Permission issues while converting RPM → used `alien --scripts` and ensured directories owned by Oracle.
- (Add any errors you hit and how you solved them.)

## Conclusion
All tasks completed. If instructor wants access to the database, credentials are:
- PDB admin: `ushindi_plsqlauca_27269` / system
