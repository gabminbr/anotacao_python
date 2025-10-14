# OOP
- como era em java:
```java
public class Pessoa{
  private String name;
  private int idade;
  private String cpf;

  public Pessoa(String name, int idade, String cpf){
    this.name = name;
    this.idade = idade;
    this.cpf = cpf;
  }

  public void imprimeDados(){
    System.out.println("Nome: " + this.name);
    System.out.println("CPF: " + this.cpf);
    System.out.println("Idade: " + this.idade);
}
```
- equivalente em python:
```python
def main():
  nome = input("Digite o nome: ")
  idade = int(input("Digite sua idade: ")
  cpf = input("Digite o cpf: ")

  pessoa = Pessoa(nome, idade, cpf)
  pessoa.imprime_dados()

class Pessoa:
  def __init__(self, nome, idade, cpf):
    self.nome = nome
    self.idade = idade
    self.cpf = cpf

  def imprime_dados(self):
    print(f"Nome: {self.nome}")
    print(f"Idade: {self.idade}")
    print(f"CPF: {self.cpf}")

  if __name__ == '__main__':
    main()
```
## Destrinchando
- *__init__*: ele é o construtor da classe, ele tem que levar obrigatoriamente o *self*, pois é ele que vai referenciar o próprio objeto que está sendo criado, é equivalente ao *this* do java.

### Herança
- em java:
```java
public class Animal{
  private String nome;

  public Animal(String nome){
    this.nome = nome;
  }

  public void fazerSom(){
    System.out.println("O animal faz um som");
  }
}

public class Cachorro extends Animal{
  public Cachorro(String nome){
    super(nome);
  }
}
```
- em python:
```python
class Animal:
  def __init__(self, nome):
    self.nome = nome

  def fazer_som(self):
    print("O animal faz um som")

class Cachorro(Animal):
  def __init__(nome, raça):
    super().__init__(nome)
    self.raca = raça

meu_cachorro = Cachorro("Rex")
print(meu_cachorro.nome)
meu_cachorro.fazer_som()
```
- método *super*: em java, ao referenciarmos o construtor da classe mãe, usávamos apenas super(atributos), entretanto, aqui em python, usaremos super().__init__(atributos que tem no construtor da classe mae)
- **MRO**: para cada classe criada, o python gera uma lista de consulta chamada MRO, que vai definir a ordem exata em que o python vai procurar por um método quando você o chama, no exemplo anterior seria:
```
[Cachorro, Animal, object]
```
- o super() serve para indicar que comece a busca no MRO a partir da proxima classe na lista.

### Polimorfismo
