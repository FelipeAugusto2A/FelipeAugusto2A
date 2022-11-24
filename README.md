class Vasco:
    def __init__(self, id, nome, idade):
        self.nome = nome
        self.idade = idade
        self.id = id

class jogador(Pessoa):
    def __init__(self,id, nome, idade, registro):
        super().__init__(nome, idade, id)
        self.registro = registro

    def criar_jogador(self):
        with connection.cursor() as cursor:
            sql = "INSERT INTO `registro` (nome, idade, id, registro) VALUES (%s, %s, %s, %s)"
            cursor.execute(sql, (self.nome, self.idade, self.id, self.registro))
            connection.commit()

    @staticmethod
    def listar_jogador():
        print(connection.cursor())
        with connection.cursor() as cursor:
            cursor.execute('SELECT * FROM jogador')
            resultado = cursor.fetchall()
            for linha in resultado:
                print(linha)

    @staticmethod
    def deletar_jogador(id):
        with connection.cursor() as cursor:
            sql = 'DELETE FROM jogador WHERE id = %s'
            cursor.execute(sql, (id))
            connection.commit()

    @staticmethod
    def atualizar_jogador(id, nome):
        with connection.cursor() as cursor:
            print(id, nome)
            sql = 'UPDATE jogador SET nome=%s WHERE id=%s'
            cursor.execute(sql, (id, nome))
            connection.commit()
from conexao import *

class Pessoa:
    def __init__(self, nome, idade, id):
        self.nome = nome
        self.idade = idade
        self.id = id

class Funcionario(Pessoa):
    def __init__(self, id, nome, idade, funçao):
        super().__init__(nome, idade, id)
        self.funçao= funçao

    def criar_funcionario(self):
        with connection.cursor() as cursor:
            sql = "INSERT INTO `funcionario` (nome, idade, id, funçao) VALUES (%s, %s, %s, %s)"
            cursor.execute(sql, (self.nome, self.idade, self.id, self.funçao))
            connection.commit()

    @staticmethod
    def listar_funcionario():
        print(connection.cursor())
        with connection.cursor() as cursor:
            cursor.execute('SELECT * FROM funcionario')
            resultado = cursor.fetchall()
            for linha in resultado:
                print(linha)

    @staticmethod
    def deletar_funcionario(id):
        with connection.cursor() as cursor:
            sql = 'DELETE FROM funcionario WHERE id = %s'
            cursor.execute(sql, (id))
            connection.commit()

    @staticmethod
    def atualizar_funcionario(id, nome):
        with connection.cursor() as cursor:
            print(id, nome)
            sql = 'UPDATE funcionario SET nome=%s WHERE id=%s'
            cursor.execute(sql, (id, nome))
            connection.commit()
from conexao import *

class Pessoa:
    def __init__(self, nome, idade, id):
        self.nome = nome
        self.idade = idade
        self.id = id

class Professor(Pessoa):
    def __init__(self, id, nome, idade, salario):
        super().__init__(nome, idade, id)
        self.salario = salario

    def criar_treinador(self):
        with connection.cursor() as cursor:
            sql = "INSERT INTO `treinador` (nome, idade, id, salario) VALUES (%s, %s, %s, %s)"
            cursor.execute (sql, (self.nome, self.idade, self.id, self.salario))
            connection.commit()
            print('O professor foi inserido com sucesso')

    @staticmethod
    def listar_treinador():
        print(connection.cursor())
        with connection.cursor() as cursor:
            cursor.execute('SELECT * FROM treinador')
            resultado = cursor.fetchall()
            for linha in resultado:
                print(linha)

    @staticmethod
    def deletar_treinador(id):
        with connection.cursor() as cursor:
            sql = 'DELETE FROM treinador WHERE id = %s'
            cursor.execute(sql, (id))
            connection.commit()

    @staticmethod
    def atualizar_treinador(id, nome):
        with connection.cursor() as cursor:
            print(id, nome)
            sql = 'UPDATE treinador SET nome=%s WHERE id=%s'
            cursor.execute(sql, (id, nome))
            connection.commit()
from conexao import *

class Vasco:
    def __init__(self, nome, idade, id):
        self.nome = nome
        self.idade = idade
        self.id = id

class reserva(Vasco):
    def __init__(self, id, nome, idade, desempenho):
        super().__init__(nome, idade, id)
        self.desempenho = desempenho

    def criar_reserva(self):
        with connection.cursor() as cursor:
            sql = "INSERT INTO `reserva` (nome, idade, id, desempenho) VALUES (%s, %s, %s, %s)"
            cursor.execute(sql, (self.nome, self.idade, self.id, self.desempenho))
            connection.commit()
    
    @staticmethod
    def apagar_desempenho(id):
        with connection.cursor() as cursor:
            sql = 'DELETE FROM desempenho WHERE id = %s'
            cursor.execute(sql, (id))
            connection.commit()
    
    @staticmethod
    def ver_desempenho():
        with connection.cursor() as cursor:
            cursor.execute('SELECT * FROM desempenho')
            resultado = cursor.fetchall()
            for linha in resultado:
                print(linha)
