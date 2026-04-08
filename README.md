# Sistema de Gerenciamento de Projetos

Aplicacao em Python com interface web para gerenciar projetos e visualizar um roadmap no estilo da imagem enviada.

## Recursos

- Cadastro, edicao e exclusao de projetos
- Persistencia em SQLite
- Login de usuarios locais
- Perfis `admin` e `visualizador`
- Historico de alteracoes por projeto
- Filtros dinamicos por setor e status
- Filtro de periodo
- Importacao de projetos por CSV/Excel
- Exportacao para Excel e PDF
- Cronograma Gantt com zoom e rolagem

## Como executar

1. Entre na pasta do projeto:

```powershell
cd C:\Masutti\Python\roadmap_ti_app
```

2. Instale as dependencias:

```powershell
pip install -r requirements.txt
```

3. Rode a aplicacao:

```powershell
python -m streamlit run app.py
```

## Banco de dados

Na primeira execucao o sistema cria `data/roadmap.db` e importa os projetos iniciais.

## Login padrao

- Usuario: `admin`
- Senha: `admin123`

## Perfis

- `admin`: gerencia projetos, usuarios e exportacoes
- `visualizador`: consulta projetos, grafico e exportacoes sem editar

## Importacao de projetos

O arquivo de importacao deve conter estas colunas:

- `descricao`
- `setor`
- `demandante`
- `status`
- `inicio`
- `final`

Valores aceitos:

- `setor`: `Infraestrutura` ou `Sistemas`
- `status`: `Concluido`, `Em andamento` ou `Previsto`
- `inicio` e `final`: datas reconheciveis pelo pandas, preferencialmente `YYYY-MM-DD`
