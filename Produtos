# Bibliotecas

import os
import fdb


# Conexão com o Banco

def firebirdConnectionData():    
    lib = 'C:/Program Files/Firebird/Firebird_3_0/fbclient.dll'
    user='sysdba'
    password = 'masterkey'
    host = 'localhost'
    port = 3050
    database = 'C:\\EstoqueProdutos\\DADOS.FDB'
    conn = [user, password, host, port, database, lib]
    return conn

def connectFirebird():
    connData = firebirdConnectionData()
    print('connecting to firebird')
    connection = fdb.connect(user=connData[0], password=connData[1], port=connData[3], host=connData[2], database=connData[4], fb_library_name=connData[5])
    return connection

conexao = connectFirebird()
cur = conexao.cursor()

# CRUD


menu = 0
while menu != 5:
    try:
        print("Lojinha Aberta!!!")       
        menu = int(input("Escolha uma opcao do menu: \n1 - Inserir \n2 - Mostrar \n3 - Alterar \n4 - Excluir \n5 - Fechar Loja\n "))
        if menu == 1:
            os.system('cls')
            id = str(input("Digite o id do novo produto: "))
            nome = str(input("Digite nome do produto: "))
            tipo = str(input("Digite o tipo do produto: "))
            valor = str(input("Digite o valor do produto: "))
            inserir = "insert into PRODUTOS values('"+id+"','"+nome+"', '"+tipo+"', '"+valor+"')"
            cur.execute(inserir)
            conexao.commit()
            print("Produto inserido com sucesso ")
            os.system('pause')
        elif menu == 2:
            os.system('cls')
            escolher = str(input("Digite o id do produto que deseja mostrar: "))
            mostrar = "select * from PRODUTOS where id ="+escolher
            cur.execute(mostrar)
            resultado = (cur.fetchall())
            print (resultado)
            os.system('pause')
        elif menu == 3:
            opcao = 0
            while opcao != 4:
                try:
                    opcao = int(input("Escolha:\n1 - Altera nome \n2 - Altera valor \n3 - Altera tipo \n4 - Sair\n "))
                    if opcao == 1:
                        id = str(input("Digite o id o produto que deseja alterar: "))
                        nome = str(input("Digite novo nome do produto: "))
                        alterar = "update PRODUTOS set nome = '"+nome+"' where id = "+id
                        cur.execute(alterar)
                        conexao.commit()
                        print("Produto alterado com sucesso ") 
                        os.system('pause')
                    elif opcao == 2:
                        id = str(input("Digite o id o produto que deseja alterar: "))
                        valor = str(input("Digite o novo valor: "))
                        alterar = "update PRODUTOS set valor = '"+valor+"' where id = "+id
                        cur.execute(alterar)
                        conexao.commit()
                        print("Produto alterado com sucesso ") 
                        os.system('pause')
                    elif opcao == 3:
                        id = str(input("Digite o id o produto que deseja alterar: "))
                        tipo = str(input("Digite o novo tipo do produto: "))
                        alterar = "update PRODUTOS set tipo = '"+tipo+"' where id = "+id
                        cur.execute(alterar)
                        conexao.commit()
                        print("Produto alterado com sucesso ") 
                        os.system('pause')
                    elif opcao == 4:
                        print(menu)
                    else:
                        os.system('cls')
                        print('Opção inválida')
                        os.system('pause')
                except:
                    os.system('cls')
                    print("Nenhum item alterado!")
                    os.system('pause')                    
        elif menu == 4:
            os.system('cls')
            escolherproduto = str(input("Digite o id do produto que deseja excluir: "))
            excluir = "delete from PRODUTOS where id="+escolherproduto
            cur.execute(excluir)
            conexao.commit()
            print("Produto excluido! ")
            os.system('pause')
        else:
            os.system('cls') 
            print("Lojinha fechada")
            os.system('pause')
    except:
        os.system('cls')
        print("Opcao invalida!")
        os.system('pause')




















