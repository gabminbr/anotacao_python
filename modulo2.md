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
