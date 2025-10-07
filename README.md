# API DE DOENÇA CARDÍACA 🫀

## Autor
Alyson Alves

## Descrição
Aplicação desenvolvida com **FastAPI** para prever a probabilidade de uma pessoa ter **doença cardíaca**, com base em idade, colesterol e tipo de dor no peito (`cp`).  

O modelo foi treinado usando **TensorFlow** e dados do repositório **UCI Machine Learning**. Os resultados são armazenados em um banco de dados **SQLite** e exibidos via interface HTML.

## Recursos
- ✅ Interface web (HTML + Jinja2)
- ✅ Banco de dados SQLite para histórico de pacientes
- ✅ Modelo simples de aprendizado de máquina em TensorFlow
- ✅ API REST com rota de listagem de pacientes
- ✅ Inserção automática de dados fictícios (300 pacientes)

## Requisitos
Instale as dependências com:

```bash
pip install fastapi uvicorn tensorflow pandas scikit-learn ucimlrepo jinja2
Execução
Para rodar a aplicação:

bash
Copiar código
uvicorn main:app --reload
Depois acesse: http://127.0.0.1:8000

Estrutura esperada
css
Copiar código
projeto/
 ┣ templates/
 ┃ ┗ index.html
 ┣ main.py
 ┗ data.db (gerado automaticamente)
Endpoints
GET / → Exibe a página inicial com formulário para previsão.

POST / → Recebe os dados do formulário, realiza a previsão e salva no banco.

GET /pacientes → Retorna todos os pacientes cadastrados em JSON.

Detalhes Técnicos
Modelo: Neurônio único treinado manualmente em TensorFlow.

Banco de Dados: SQLite (data.db), tabela pacientes.

Preprocessamento: Normalização de idade e colesterol, one-hot encoding de cp.

Inicialização do Banco de Dados
O banco é criado automaticamente ao iniciar a aplicação. Caso esteja vazio, ele será populado com 300 registros fictícios.

Funções Principais
prever_doenca(idade, colesterol, cp) → Retorna a probabilidade de doença cardíaca em porcentagem.

init_db() → Inicializa e popula o banco de dados.

get_connection() → Retorna conexão com SQLite.

Observações
Este projeto é educacional e não substitui avaliação médica.

A interface HTML utiliza Jinja2 para exibição dinâmica dos resultados.

O modelo é simples e não deve ser usado para diagnóstico real.
