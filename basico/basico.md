# Main
- em python, os arquivos *.py* são chamados de *módulos*, e cada um pode ser executado diretamente, como um programa em si, ou importado por outro módulo.
- em python, é convenção usarmos a função:
```python
  if __name__ == '__main__':
    main()
```
- a __name__ nos indica o nome do contexto em que o módulo está rodando, ou seja, ela representa o nome do módulo, quando está sendo executado por si só, __name__ é definido para '__main__', diferente de quando o módulo é importado, no qual o valor fica igual ao nome do módulo.

 # Listas
 - usamos os colchetes [] para criar listas:
```python
  frutas = ['banana', 'maçã']
  print(frutas[1])

  # resultado: banana
```
- append(elemento): serve para adicionar o item ao final da lista;
- pop(index): remove o elemento que esta no index;

 # Dicionários
 - os dicionários guardam dados em pares de chave-valor, usa-se chaves:
```python
  aluno = {
    "nome": "Carlos",
    "idade": 22,
    "curso": "Ciência da Computação"
  }

  print(f"curso: {aluno["curso"]}")
```
- podemos adicionar novas chaves:
```python
  aluno["genero"] = "Masculino"
```
- para percorrer sobre um dicionario, usamos o *.items()*:
```python
  for chave, valor in livro.items():
    print(f"{chave}: {valor}")
```
