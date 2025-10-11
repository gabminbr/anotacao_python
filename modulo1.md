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

