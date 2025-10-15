# Persistência de Dados
- salvar os objetos que criamos em um arquivo/lugar quando o programa fecha e poder acessá-los novamente, usaremos o JSON.
## Serialização
- É o processo de converter um objeto complexo da memória (como nosso objeto Aluno) em um formato de texto (JSON) que pode ser facilmente salvo em um arquivo.
- Desserialização: É o processo inverso: ler o texto do arquivo JSON e reconstruir os objetos originais na memória.

## JSON
- JSON (JavaScript Object Notation) é uma linguagem universal que quase todos os sistemas e linguagens de programação entendem, sua ideia se baseia em:
```
1 - Objetos (Dictionaries em Python): Um conjunto de pares "chave-valor" dentro de chaves {}. A única regra é que a chave deve sempre ser uma string entre aspas duplas.
2 - Arrays (Lists em Python): Uma lista ordenada de valores dentro de colchetes [].
```
- exemplo, um objeto do tipo Aluno:
```json
[
    {
        "__class__": "AlunoDeGraduacao",
        "nome": "João Silva",
        "semestre": 3,
        "mensalidade_base": 900.0,
        "matricula_ativa": true
    },
    {
        "__class__": "AlunoDePosGraduacao",
        "nome": "Maria Souza",
        "semestre": 5,
        "mensalidade_base": 1200.0,
        "matricula_ativa": true,
        "orientador": "Dr. Carlos"
    }
]
```
