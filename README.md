# 🌍 Análise de Emissões de Gases de Efeito Estufa no Brasil (1970–2021)
Este projeto tem como objetivo analisar as emissões de gases de efeito estufa (GEE) por estado brasileiro, com base nos dados oficiais do inventário nacional. A análise cobre o período de 1970 a 2021 e busca responder perguntas como:

Quais são os gases mais emitidos?

Quais setores econômicos mais poluem?

Como as emissões evoluíram ao longo dos anos?

📄 Fonte dos Dados
Utilizamos um arquivo Excel contendo diversas planilhas. Neste projeto, selecionamos apenas a aba "GEE Estados", pois ela reúne as informações de emissões estaduais.

🧹 Limpeza e Filtragem de Dados
Para garantir que os dados analisados fossem realmente representativos das emissões reais dos estados brasileiros, removemos:

Remoções: registros de retirada de gases da atmosfera, que são o oposto da emissão.

NCI (Não Contemplados): dados que não fazem parte do inventário oficial.

Bunkers: emissões de transporte marítimo e aéreo internacional, que não pertencem a nenhum estado específico.

Após essa filtragem, mantivemos somente os dados classificados como "Emissão".

🔁 Transformação da Base de Dados
A estrutura original da planilha traz os anos como colunas. Para facilitar a análise e visualização dos dados, reorganizamos a tabela de modo que:

Os anos passaram a ocupar uma única coluna.

As emissões passaram a ser valores em uma outra coluna.

Essa transformação permite agrupar, comparar e visualizar tendências com muito mais facilidade.

📊 Principais Análises
1. Gases mais emitidos no Brasil
Identificamos os gases de efeito estufa mais presentes nas emissões totais. O gás CO₂ se destacou como o mais poluente, representando mais de 70% das emissões.

2. Setores mais poluentes
Agrupamos os dados por setores econômicos para entender qual atividade emite mais GEE. Os principais setores emissores incluem:

Agropecuária

Energia

Mudança de Uso da Terra e Floresta

3. Cruzamento entre gases e setores
Também cruzamos informações para saber:

Qual setor emite mais para cada tipo de gás.

Qual gás é mais emitido por cada setor.

Esses cruzamentos foram organizados em tabelas sumarizadas para facilitar a interpretação.

📈 Evolução ao Longo dos Anos
Através de visualizações, conseguimos observar se as emissões aumentaram ou diminuíram com o passar do tempo, permitindo entender o impacto de políticas públicas, mudanças no uso do solo e industrialização.

📁 Arquivos Gerados
emissao_por_ano.csv: Base tratada com as emissões organizadas por ano.

tabela_sumarizada.csv: Tabela com os setores que mais emitem cada tipo de gás.

tabela_sumarizada2.csv: Tabela com os gases mais emitidos em cada setor.

🚀 Próximos Passos
Criar visualizações interativas para explorar os dados.

Comparar os estados entre si.

Avaliar políticas públicas com base nos dados de emissão.

🧠 Conclusão
Esta análise é essencial para entender o impacto das atividades humanas nas mudanças climáticas. Compreender as fontes e tipos de emissão permite direcionar ações de mitigação de forma mais eficiente e estratégica.

