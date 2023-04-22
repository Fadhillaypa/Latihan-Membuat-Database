# Latihan-Membuat-Database
Fadhilla Yunandrika P A_V3922018_TI D

import mysql.connector

dataBase = mysql.connector.connect(
    host="localhost",
    user="root",
    passwd=""
)

# preparing a cursor object
cursorObject = dataBase.cursor()

# creating database
cursorObject.execute("CREATE DATABASE D3_TI_2023")

import mysql.connector
​
dataBase = mysql.connector.connect(
    host="localhost",
    user="root",
    passwd=""
)
​
# preparing a cursor object
cursorObject = dataBase.cursor()
​
# creating database
cursorObject.execute("CREATE DATABASE D3_TI_2023")
​
import sqlite3
​
conn = sqlite3.connect('d3_ti_2023')
​
print ("Opened database successfully")
Opened database successfully
import mysql.connector
​
dataBase = mysql.connector.connect(
    host = "localhost",
    user = "root",
    passwd = "",
    database = "d3_ti_2023"
)
​
#preparing cursor
cursorObject = dataBase.cursor()
​
#creating table
studentRecord = """CREATE TABLE Mahasiswa (
                   NIM VARCHAR (10) NOT NULL,
                   NAMA VARCHAR (30),
                   ALAMAT VARCHAR (255),
                   MATA_KULIAH VARCHAR (10),
                   KELAS VARCHAR (10),
                   DOSEN_PEMBIMBING VARCHAR (30),
                   TAHUN_MASUK INT
                   )"""
​
#table created
cursorObject.execute(studentRecord)
​
#Disconnect
dataBase.close()
import mysql.connector
​
dataBase = mysql.connector.connect(
    host = "localhost",
    user = "root",
    passwd = "",
    database = "d3_ti_2023"
)
​
#preparing cursor
cursorObject = dataBase.cursor()
​
#creating table
studentRecord = """CREATE TABLE Dosen (
                   NIP VARCHAR (20) NOT NULL,
                   NAMA_DOSEN VARCHAR (50),
                   MATA_KULIAH_YANG_DIAJAR VARCHAR (50),
                   TAHUN_MENGAJAR INT,
                   BANYAK_KELAS_YANG_DIAJAR INT,
                   TAHUN_PENSIUN INT,
                   ALAMAT VARCHAR (50)
                   )"""
​
#table created
cursorObject.execute(studentRecord)
​
#Disconnect
dataBase.close()
import mysql.connector
​
dataBase = mysql.connector.connect(
    host = "localhost",
    user = "root",
    passwd = "",
    database = "d3_ti_2023"
)
​
#preparing cursor
cursorObject = dataBase.cursor()
​
#creating table
studentRecord = """CREATE TABLE Mata_Kuliah (
                   KODE_MATKUL VARCHAR (10),
                   NAMA_MATKUL VARCHAR (50),
                   WAKTU DATE,
                   RUANGAN VARCHAR (10),
                   DOSEN_PENGAMPU VARCHAR (50),
                   SKS INT
                   )"""
​
#table created
cursorObject.execute(studentRecord)
​
#Disconnect
dataBase.close()
import mysql.connector
​
dataBase = mysql.connector.connect(
    host = "localhost",
    user = "root",
    passwd = "",
    database = "d3_ti_2023"
)
​
#preparing cursor
cursorObject = dataBase.cursor()
​
sql = "INSERT INTO Mahasiswa (NIM, NAMA, ALAMAT, MATA_KULIAH, KELAS, DOSEN_PEMBIMBING, TAHUN_MASUK) VALUES (%s, %s, %s, %s, %s, %s, %s)"
val = [("3922018", "Fadhilla Yunandrika Putra Adyatma", "Ponorogo", "KWU", "TI-D", "Pak Darmawan", "2022"),
       ("3922040", "Muhammad Rafi Naufal", "Sukoharjo", "Praktik Web", "TI-E", "Bu Nur", "2022"),
       ("3922041", "Subekti Bimo Wicaksono", "Magetan", "Praktik Sistem Operasi", "TI-E", "Bu Masbahah", "2022"),
       ("3922006", "Angga Yudho", "Balerejo", "APSI", "TI-D", "Pak Darmawan", "2022"),
       ("3922043", "Mahesa Agung", "Mejayan", "Mitrokontroller", "TI-E", "Pak fendy", "2022"),
      ]
        
cursorObject.executemany (sql, val)
dataBase.commit()
​
#Disconnect
dataBase.close()
import mysql.connector
​
dataBase = mysql.connector.connect(
    host = "localhost",
    user = "root",
    passwd = "",
    database = "d3_ti_2023"
)
​
#preparing cursor
cursorObject = dataBase.cursor()
​
sql = "INSERT INTO Dosen (NIP, NAMA_DOSEN, MATA_KULIAH_YANG_DIAJAR, TAHUN_MENGAJAR, BANYAK_KELAS_YANG_DIAJAR, TAHUN_PENSIUN, ALAMAT) VALUES (%s, %s, %s, %s, %s, %s, %s)"
val = [("6747484", "Pak Yusuf", "Wireless", "2012", "4", "-", "-"),
       ("92837322", "Bu Kanthi", "Etika", "2012", "1", "-", "-"),
       ("339922811", "Bu Masbahah", "Praktik Web", "2015", "5", "-", "-"),
       ("893282918", "Bu Trisna", "Statistika", "2012", "1", "-", "-"),
        ("112489382", "Bu Nur", "Sistem Operasi", "2014", "2", "-", "-")
      ]
​
cursorObject.executemany (sql, val)
dataBase.commit()
​
#Disconnect
dataBase.close()
import mysql.connector
​
dataBase = mysql.connector.connect(
    host = "localhost",
    user = "root",
    passwd = "",
    database = "d3_ti_2023"
)
​
#preparing cursor
cursorObject = dataBase.cursor()
​
sql = "INSERT INTO Mata_Kuliah (KODE_MATKUL, NAMA_MATKUL, WAKTU, RUANGAN, DOSEN_PENGAMPU, SKS) VALUES (%s, %s, %s, %s, %s, %s)"
val = [("23678889",  "Wireless", "2023-1-1", "Lab 3", "Pak Yusuf", 2),
       ("66755531",  "Statistika", "2023-1-4", "Daring", "Bu Trisna", 2),
       ("65545556",  "Praktik Web", "2023-1-3", "Lab 2", "Bu Masbahah", 2),
       ("63322445",  "Etika", "2023-1-5", "Daring", "Bu Kanthi", 1),
       ("45332234",  "Sitem Operasi", "2023-1-2", "Daring", "Bu Nur", 2)
      ]
​
cursorObject.executemany(sql, val)
dataBase.commit()
​
#Disconnect
dataBase.close()
import mysql.connector
​
dataBase = mysql.connector.connect(
    host = "localhost",
    user = "root",
    passwd = "",
    database = "d3_ti_2023"
)
​
#preparing cursor
cursorObject = dataBase.cursor()
​
query = "SELECT NAMA_MATKUL, DOSEN_PENGAMPU FROM Mata_Kuliah"
cursorObject.execute (query)
​
myresult = cursorObject.fetchall()
​
for x in myresult:
    print(x)
    
dataBase.close()
('Wireless', 'Pak Yusuf')
('Statistika', 'Bu Trisna')
('Praktik Web', 'Bu Masbahah')
('Etika', 'Bu Kanthi')
('Sitem Operasi', 'Bu Nur')
