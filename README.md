# conectormysql
#conexão mysql
#há necessidade de instalar os complementos via pip #pip install mysql-connector-python#

import mysql.connector

con = mysql.connector.connect(host='0.0.0.0 (ou localhost', database='nome banco de dados', user= 'username', password='senha')

if con.is_connected():
  db_info = con.get_server_info()
  print('Você esta conectado ao servidor', db_info)
  cursor = con.cursor()
  cursor.execute('select database();')
  linha = cursor.fetchone()
  print('Conectado ao banco de dados', linha)

if con.is_connected():
  cursor.close()
  con.close()
  print('Conexão Encerrada')
