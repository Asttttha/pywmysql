# pywmysql
My first repository (py with mysql)
import mysql.connector
             import sys
             def data():
                     db=mysql.connector.connect(host="localhost",user="root",passwd="2003")
                     cursor=db.cursor()
                     try:
                cursor.execute("create Database FOODVILLA")
                         print("Database Created")
                     except:
                         print("Database already created")
             def table():
                                           db=mysql.connector.connect(host="localhost",user="root",passwd="2003",database="FOODVILLA")
                     cursor=db.cursor()
                     try:
                         cursor.execute("create table MENU (meal char(10), villa number int(10))")
                         print("Table created")
                         cursor.execute("insert into MENU values ('Breakfast',01)")
                         cursor.execute("insert into MENU values ('Lunch',02)")
                         cursor.execute("insert into MENU values ('Dinner',03)")
                         cursor.execute("insert into MENU values ('Desserts',04)")
                         cursor.execute("insert into MENU values ('Drinks',05)")
                         cursor.execute("insert into MENU values ('Snacks',06)") 
                     except:
                         print("Table already created")
             def select():
                                         db=mysql.connector.connect(host="localhost",user="root",passwd="2003",database="FOODVILLA",table="MENU")
                                         cursor=db.cursor()
                                         query=("SELECT * FROM MENU")
                                         cursor.execute(query)
                                         r=cursor.fetchall()
                                         for row in r:
                                                                     print(row)

             while True:
                                               print("Menu \n 1. create database \n 2. create table \n 3. select \n 4. Exit")
                                               ch=int(input("Enter Your Choice"))
                                               if ch==1:
                                                                     data()
                                               if ch==2:         
                                                                     table()
                                               if ch==3:      
                                                                     select()
                                               if ch==4:
                                                                     print("Thankyou")
                                                                     sys.exit()
