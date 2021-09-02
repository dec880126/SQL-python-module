# SQL-python-module

A module that simplify the process to call SQL database

## How to use

1. Put **sql_command.py** at the same directory with your main python file
2. Use import method: `import sql_command`
3. `import pymysql`
4. set up your database setting
5. `conn = pymysql.connect(**db_settings)`
6. `executor = conn.cursor()`
7. `executor.execute(SQL-python-module Supported functions)`
8. Get the result by `executor.fetchall()` or `executor.fetchone()`
9. Remind to `conn.close()` or you can just use `with conn.cursor() as executor:` at start

## Download

 - [Latest Release](https://github.com/dec880126/SQL-python-module/releases)

## Supported functions

### searchCommand()

    searchCommand(listFrom="資料表", key="搜尋條件", searchBy = 搜尋值)
    - 搜尋值為單一資料
      - SELECT * FROM `資料表` WHERE `搜尋條件` IN '搜尋值'

    - 搜尋值為 List
      - SELECT * FROM `資料表` WHERE `搜尋條件` IN ('搜尋值1', '搜尋值2', ...)

### searchCommand_sp()

     - searchCommand_sp("資料表", "欄位")
       - SELECT `欄位` FROM `資料表` WHERE 1

     - searchCommand_sp("資料表", "欄位", "條件欄位", "條件值")
       - SELECT `欄位` FROM `資料表` WHERE `條件欄位` = '條件值'

### listAllCommand()

    listAllCommand(listFrom="資料表")
     - SELECT * FROM `資料表`

### deleteCommand()

    deleteCommand(listFrom="資料表", key="搜尋條件", searchBy = 搜尋值)
     - DELETE FROM `資料表` WHERE '搜尋條件' = '搜尋值'

### insertCommand()

    insertCommand(listFrom="資料表", key=("欄位1", "欄位2", ...), searchBy = ("值1", "值2", ...))
     - INSERT INTO `資料表` (`欄位1`, `欄位2`, ...) VALUES ("值1", "值2", ...)

### editCommand()

    editCommand("資料表", "欲設定之欄位", "欲設定之值", "搜尋條件", "搜尋值")
     - UPDATE `資料表` SET `欲設定之欄位`= '欲設定之值' WHERE `搜尋條件` = '搜尋值'

### countCommand()

     - countCommand("資料表")
       - SELECT COUNT(*) FROM `資料表` WHERE 1  

     - countCommand("資料表", "欄位", "值")
       - SELECT COUNT(*) FROM `資料表` WHERE `欄位` = '值'
