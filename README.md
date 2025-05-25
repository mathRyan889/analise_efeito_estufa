# 📊 Análise de Emissões de Gases de Efeito Estufa por Estado (1970–2021)
Este projeto tem como objetivo realizar uma análise exploratória dos dados de emissões de gases de efeito estufa (GEE) no Brasil, por estado, no período de 1970 a 2021, utilizando a linguagem Python e bibliotecas como pandas e matplotlib.

🧩 Estrutura dos Dados
Os dados foram extraídos do arquivo Emissões.xlsx, mais especificamente da planilha "GEE Estados", que contém informações sobre:

Estados brasileiros

Tipos de emissão (emissão, remoção, bunker)

Setores econômicos

Tipos de gás

Emissões por ano (1970 a 2021)

⚙️ Passos da Análise
1. Leitura dos Dados
python
Copiar
Editar
emissoes_gases = pd.read_excel('Emissões.xlsx', sheet_name='GEE Estados')
2. Inspeção Inicial
python
Copiar
Editar
emissoes_gases.info()
🧹 Limpeza e Filtragem dos Dados
Removemos os seguintes registros:

Remoções: representam retirada de gases da atmosfera.

NCI: não estão contemplados no inventário nacional.

Bunkers: emissões internacionais (não atribuídas a estados).

python
Copiar
Editar
emissoes_gases = emissoes_gases[emissoes_gases['Emissão / Remoção / Bunker'] == 'Emissão']
🔄 Transformação dos Dados
A base original possui colunas de anos (1970–2021). Para facilitar a análise, usamos melt() para transformá-las em uma coluna única chamada Ano.

python
Copiar
Editar
emissao_por_ano = emissoes_gases.melt(
    id_vars=colunas_info,
    value_vars=colunas_emissao,
    var_name='Ano',
    value_name='Emissão'
)
📊 Análises Realizadas
🔹 Emissão total por tipo de gás
python
Copiar
Editar
emissao_por_gás = emissao_por_ano.groupby('Gás')[['Emissão']].sum().sort_values('Emissão', ascending=False)
🔹 Visualização (Top 9 gases)
python
Copiar
Editar
emissao_por_gás.iloc[0:9].plot(kind='barh', figsize=(10,6));
🔹 Porcentagem de CO₂ em relação ao total
python
Copiar
Editar
porcentagem_co2 = (emissao_por_gás.iloc[0:9].sum().sum() / emissao_por_gás.sum().sum()) * 100
🔍 Análise por Setor
🔸 Gases mais emitidos por setor
python
Copiar
Editar
gas_por_setor.groupby(level=1).idxmax()
🔸 Setores mais emissores por tipo de gás
python
Copiar
Editar
gas_por_setor.groupby(level=0).idxmax()
Essas análises geram duas tabelas sumarizadas:

tabela_sumarizada.csv

tabela_sumarizada2.csv

📅 Tendência Temporal
A evolução da emissão ao longo dos anos pode ser visualizada por meio de agrupamentos por ano ou por setor específico em determinado ano (ex: 2021).

python
Copiar
Editar
emissao_por_ano[emissao_por_ano['Ano']==2021].groupby('Nível 1 - Setor')[['Emissão']].sum()
💾 Exportação de Resultados
Todos os resultados relevantes foram exportados para .csv:

emissao_por_ano.csv

tabela_sumarizada.csv

tabela_sumarizada2.csv

📚 Requisitos
Python 3.7+

pandas

matplotlib (para gráficos)

Instalação com pip:

bash
Copiar
Editar
pip install pandas matplotlib
✍️ Autor
Este projeto foi desenvolvido com fins didáticos para analisar dados ambientais e auxiliar a tomada de decisão baseada em evidências.

