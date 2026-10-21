# Documento Flask
## instalação do UV astral
entramos no aplicativo uv e fomos para parte installation
onde colocamos em qualquer terminal que seja powershell:
"Bypass -c powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex""
## comandos 
1- O uv é um gerenciador de pacotes e projetos Python onde seria tudo em um, substitui varias ferramentas tradissionais para mais simples
2- usamos "uv -V" para descobrir a versão que esta sendo usada
3- "uv init" Inicializa um novo projeto Python no diretório atual.
4- "uv sync" Sincroniza o ambiente virtual do projeto com as dependências especificadas no arquivo
5-"uv vent" cria a pasta .venv
6-"uv run flask run" serve para executar a aplicação Flask utilizando o ambiente virtual (não conseguimos executar esse codigo se ele estiver aberto em outro terminal tbm)
## app.py
importamos o flask/markupsafe usando o "import"

request: Usada para pegar dados enviados pelo usuário através da URL

escape: Uma ferramenta que limpa o texto inserido pelo usuário

o render_template, responsavel criar uma pagina HTML

 O "@app.route("/")" significa que quando alguém acessar a raiz do seu site (ex: http://localhost:5000/), essa função será executada.
 ### parte do codigo
@app.route("/pessoa")
def ola_pessoa():
    nome = request.args.get("nome", "Flask")
    return f'ola, {escape(nome)}'

ela le um parâmetro passado na URL após um ponto de interrogação (?).
### exemplo
Se você acessar http://localhost:5000/pessoa?nome=allan, a variável nome recebe "allan" e a página mostra ola, allan. Se você acessar apenas /pessoa sem passar nada, ele usa "Flask" q é o valor padrão se a pessoa não colocar nada.

@app.route("/ola/")
@app.route("/ola/<"nome">")
conhecida como rotas duplas Repare que ela possui dois @app.route. Isso significa que tanto acessando /ola/ quanto /ola/joao, essa mesma função será acionada.

"endif" encerra a estrutura, um if no HTML



