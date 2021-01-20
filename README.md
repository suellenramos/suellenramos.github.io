# Atividade Acadêmica: Orientação a Objetos usando Python.

class Clientes:
  def __init__(self, nome, cpf, endereco, telefone):
    self.nome = nome
    self.cpf = cpf
    self.endereco = endereco
    self.telefone = telefone
    
class Func:
  def __init__(self, funcnome, matricula, telefone):
    self.funcnome = funcnome
    self.matricula = matricula
    self.telefone = telefone

class Produto:
  def __init__(self, prodnome, cod, preco):
    self.prodnome = prodnome
    self.cod = cod
    self.preco= preco

class Vendas:
  def __init__(self, produto, cliente, funcionario,qtd):
    self.produto = produto
    self.cliente = cliente
    self.funcionario= funcionario
    self.qtd=qtd

list_clientes = []

list_produtos= []

list_funcionarios=[]

list_vendas= []


def criar_clie():

  print("Definindo dados do cliente: ")

  nome= input("Digite seu nome: ")
  cpf= input("Digite seu cpf: ")
  endereco = input("Digite o endereco: ")
  telefone = input("Digite seu telefone: ")

  DadosC = Clientes(nome, cpf, endereco, telefone)
  return DadosC

def criar_func():

  print("Definindo dados do funcionário: ")
  nome= input("Digite seu nome: ")
  matricula= input("Digite sua matricula: ")
  telefone = input("Digite seu telefone: ")

  DadosFunc = Func(nome, matricula, telefone)
  return DadosFunc

def criar_prod():

  print("Definindo dados do produto: ")
  nome= input("Digite o nome do produto: ")
  codigo = input("Digite o codigo: ")
  preco = input("Digite o preço: ")

  DadosProd = Produto(nome, codigo, preco)
  
  return DadosProd

def criaVendas():
  cliente= criar_clie()
  funcionario = criar_func()
  produto = criar_prod()
  qtd= input("Digite a quantidade de produtos: ")
  vendas= Vendas(produto, cliente, funcionario,qtd)
  list_vendas.append(vendas)


while (True):

  print("Digite 1 para criar uma nova venda: ")

  print("Digite 2 para mostrar informações: ")

  a= input()
  if a == "1":
    criaVendas()
  if a == "2":
    print("Clientes")
    for i in list_vendas:
      print(i.cliente.nome)

    print("Funcionarios")
    for i in list_vendas:
      print(i.funcionario.funcnome) 

    print("Produtos")

    for j in list_vendas:
      print(j.produto.prodnome)
      print(j.qtd)
      print("Preço Unitáio:",j.produto.preco)
      print("Preço Total:", float(j.produto.preco)*float(j.qtd))
