### :point_right: This starter repo has moved to the [ionic-team/starters](https://github.com/ionic-team/starters/tree/master/ionic1/official/blank) repo! :point_left:

mysqltutorial.org

var mysql = require("mysql")

var configuration = {
	host: 'us-cdbr-east-04.cleardb.com',
	user: 'b8f3dd1d8d9c29',
	password: '0611b499',
	database: 'heroku_23ebff43a942f06',
	multipleStatements: true
}

var connection = mysql.createConnection(configuration)

var SQL = 'SHOW TABLES'
connection.query(SQL, [], function(errors, results, fields) { console.log(results) })

Tables:
	HISTORY (PHONE VARCHAR(10), ONE VARCHAR(50), TWO VARCHAR(50), THREE VARCHAR(50), FOUR VARCHAR(50), FIVE VARCHAR(50), APPOINTMENT VARCHAR(18))
	APPOINTMENTS (AVAILABLE VARCHAR(18))
		AVAILABLE = 'MM/DD/YYYY HH:MM(AM/PM)'
	ORDERS (PHONE VARCHAR(10), ITEM VARCHAR(100), LOCATION VARCHAR(200), TIME VARCHAR(50))

USE DATABASE
SHOW TABLES
CREATE TABLE TABLE_NAME (
    ROW_NAME PRIMARY KEY
    COLUMN_NAME VARCHAR(LENGTH_INT)
)
DROP TABLE TABLE_NAME
DESCRIBE TABLE_NAME
SELECT * FROM TABLE_NAME
SELECT * FROM TABLE_NAME WHERE COLUMN_NAME = ?
INSERT INTO TABLE_NAME (COLUMN_NAME) SELECT COLUMN_NAME FROM TABLE_NAME WHERE COLUMN_NAME = ?
INSERT INTO TABLE_NAME (COLUMN_NAME) VALUES (?) --> connection.query(SQL, [[?]], function(errors, results, fields) {}), (?) = [[?]]

LOGIN     SELECT * FROM HISTORY WHERE PHONE = ?
SCHEDULE  SELECT TIME FROM APPOINTMENTS WHERE PHONE = ?
SCHEDULE  INSERT INTO HISTORY (APPOINTMENT) SELECT AVAILABLE FROM APPOINTMENTS WHERE PHONE = ?
REGISTER  INSERT INTO HISTORY (PHONE, ONE, TWO, THREE, FOUR, FIVE) VALUES (?, "none", "none", "none", "none", "none")
ORDERS    SELECT * FROM ORDERS WHERE PHONE = ?
ORDER     INSERT INTO ORDERS (PHONE, ITEM, LOCATION, TIME) VALUES (?)