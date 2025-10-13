# Uso do VENV
```
O Problema (A Analogia da Caixa de Ferramentas):
Imagine que você tem um único caixote de ferramentas para todos os seus projetos de marcenaria. Para o Projeto A (uma cadeira), você precisa de uma lixa de grão 80. Para o Projeto B (uma estante),
você precisa de uma lixa de grão 120. Se você só tem espaço para uma, um dos projetos ficará comprometido. Em software, essas "ferramentas" são as bibliotecas (código de terceiros).
O Projeto A pode precisar da biblioteca requests versão 2.25, enquanto o Projeto B precisa da versão 2.28. Instaladas globalmente, elas criam conflitos.

A Solução (venv):
Um ambiente virtual é como criar uma caixa de ferramentas separada e exclusiva para cada projeto. Cada caixa contém sua própria versão do Python e suas
próprias bibliotecas, completamente isolada de todas as outras.
```
- como fazer:
- Crie uma pasta para o nosso projeto de controle de gastos e entre nela:
```bash
mkdir projeto_teste
cd projeto_teste
```
- Agora, dentro da pasta projeto_teste, execute o seguinte comando para criar o ambiente virtual. Vamos chamar nossa "caixa de ferramentas" de venv:
```bash
python -m venv venv
```
- isso diz ao python para rodar (-m) o módulo venv e criar um ambiente chamado venv
- assim, uma pasta chamada venv será criada, agora precisamos *abrir* a caixa de ferramentas, ou seja, ativar o ambiente
- powershell:
```powershell
.\venv\Scripts\activate
```
- bash:
```bash
source venv/bin/activate
```
- para saber que deu certo o comando, agora o prompt de comando será prefixado com (venv)
- agora sempre que baixar algo com o *pip* vai ser instalado dentro desse ambiente (caixa), sem afetar os outros projetos, quando terminar de trabalhar, basta fazer um deactivate no terminal.
- caso tenha algum problema para usar o python no venv, aperta cntrl + shift + P, e vai em Python: interpreter select e bota o que tem venv, e pronto, seu ambiente virtual vai rodar o python.

# Exceções
- é bem parecido com o java, o try é o mesmo uso
- *except*, o except é o equivalente ao catch, ou seja, quando ocorre a exceção, esse bloco será executado
- *else*, esse não tem no java, será executado quando o try é executado, ou seja, quando dá certo
- *finally*, equivalente ao java, esse bloco vai ser sempre executado.
- em python, todas as exceções herdam de uma classe base chamada Exception
- hierarquia:
```
BaseException  (Similar ao Throwable do Java - a base de tudo)
 +-- Exception (Similar ao Exception do Java - base para a maioria dos erros de aplicação)
 |    +-- ValueError (Argumento com tipo correto, mas valor inadequado)
 |    +-- TypeError (Operação aplicada a um objeto de tipo inadequado)
 |    +-- ZeroDivisionError (Divisão por zero)
 |    +-- FileNotFoundError (Arquivo não encontrado)
 |    +-- KeyError (Chave de dicionário não encontrada)
 |    +-- IndexError (Índice de lista fora do intervalo)
 |    +-- ... e muitas outras
 +-- KeyboardInterrupt (Usuário pressiona Ctrl+C)
 +-- SystemExit (Função sys.exit() é chamada)
```
- quando fazemos *except ValueError as e*, fazemos o mesmo que o *catch(Exception e)*
- em python não existe checked e unchecked exceptions, ou seja, você nunca é obrigado a tratar uma exceção, pois o python confia

## criando a própria exceção
- basicamente criamos uma classe que herda de Exception:
```python
# 1. DEFININDO UMA EXCEÇÃO CUSTOMIZADA
# É tão simples quanto herdar da classe Exception.
class ErroDeMatricula(Exception):
    """Exceção customizada para erros na lógica de matrícula."""
    pass # 'pass' significa que a classe não tem métodos ou atributos próprios por enquanto.

# 2. USANDO A EXCEÇÃO NA LÓGICA
def matricular_aluno(aluno, semestre):
    # Imagina que aqui você consulta um banco de dados
    aluno_ja_matriculado = True # Vamos simular que o aluno já está matriculado

    if aluno_ja_matriculado:
        # Em vez de retornar um código de erro ou imprimir, lançamos uma exceção.
        # 'raise' é o equivalente ao 'throw new' do Java.
        raise ErroDeMatricula(f"O aluno '{aluno}' já possui matrícula no semestre {semestre}.")
    
    # ... resto da lógica de matrícula ...
    print(f"Aluno '{aluno}' matriculado com sucesso!")


# 3. TRATANDO A EXCEÇÃO CUSTOMIZADA
try:
    matricular_aluno("João Silva", 3)
except ErroDeMatricula as e:
    # Agora podemos capturar nosso tipo de erro específico!
    print(f"Falha no processo de matrícula: {e}")
```
