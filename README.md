# Perfil Políticos Brasileiros
Repositório com códigos para obtenção de notícias do G1 relativos à Deputados Federais, com Reconhecimento de Entidades Nomeadas (NER), Similaridade usando BERT e Sumarização Palavras chave usando GPT.


#### Aluno: [Luiza Henriques](https://github.com/luizahenriques)
#### Orientador: [Felipe Borges](https://github.com/FelipeBorgesC)


---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".
- [Extração Notícias G1 NER e Similaridade](2024_01_19ExtraçãoNotíciasG1SpicyIncremental.ipynb);
- [Obtenção Ação Deputado](Deputados_AçãodoDeputado.ipynb);
- [Obtenção Keywords](Deputados_keywords.ipynb);
- [Obtenção Sumarização](Deputados_SumarizarNoticias2.ipynb);
- [Código ETL](ETLNoticiasEmpilhadas.ipynb)



---

### Resumo

Este trabalho visa criar uma ferramenta inovadora para que a sociedade acompanhe as atividades dos políticos brasileiros pós-eleições e início das atividades nos cargos. Utilizando uma API para coletar notícias políticas do site G1 (https://g1.globo.com/politica) desde dezembro de 2023, a ferramenta emprega a biblioteca spaCy para identificar os nomes dos políticos nas reportagens (NER). Também incorpora dados da API da Câmara dos Deputados sobre os legisladores das últimas duas legislaturas para ser a base de referência de busca. Para mensurar similaridade, optou-se por utilizar um modelo pré-treinado baseado em BERT, disponível (bert-base-portuguese-cased-assin2-similarity). A ferramenta calcula scores de similaridade, filtrando com um ponto de corte para garantir precisão das buscas. Para complementar e ampliar a análise, a API da OpenAI, com o GPT, é utilizada para sumarizar as notícias, extrair palavras-chave e trazer o específico envolvimento do político na notícia. Os resultados são apresentados em um painel no Power BI, tornando as informações acessíveis aos usuários. Este trabalho representa uma contribuição significativa para o acompanhamento transparente e participativo das atividades políticas, oferecendo à sociedade uma visão mais detalhada e crítica do cenário político brasileiro.

### Abstract

This dissertation aims to develop an innovative tool for society to monitor the activities of Brazilian politicians post-elections and the commencement of their terms. Leveraging an API to gather political news from the G1 website (https://g1.globo.com/politica) since December 2023, the tool utilizes the spaCy library for Named Entity Recognition (NER) to identify politicians' names in news articles. Additionally, it incorporates data from the Chamber of Deputies API, providing information on legislators from the last two legislative terms as a reference base. To measure similarity, a pre-trained BERT-based model was employed, accessible at (bert-base-portuguese-cased-assin2-similarity). The tool calculates similarity scores, applying a cutoff point to ensure search accuracy. To enhance the analysis comprehensively, the OpenAI API, featuring GPT, is employed to summarize news articles, extract keywords, and delineate the specific involvement of politicians in the news. The outcomes are presented on a Power BI dashboard, rendering information accessible to users. This work constitutes a significant contribution to transparent and participatory monitoring of political activities, providing society with a more detailed and critical perspective on the Brazilian political landscape.

### 1. Introdução

O papel dos políticos, especialmente dos deputados federais, é fundamental para duas tarefas: legislar e fiscalizar. Como guardiões do interesse público, esses representantes eleitos são incumbidos da responsabilidade de criar leis e advogar pelas necessidades de seus eleitores. No entanto, no cenário pós-eleitoral, frequentemente ocorre lacuna entre as promessas feitas durante as campanhas e o que, de fato, pode ser notado no exercício do cargo. Essa desconexão entre promessas e realidade exige um acompanhamento atento dos eleitores.

Este trabalho de conclusão de curso visa abordar essa crescente demanda por transparência e responsabilidade dos cidadãos na política brasileira e como modelos de Processamento de Linguagem Natural podem nos apoiar nessa missão. A extração de informações relevantes e direcionadas ao objetivo, em grandes cadeias textuais, é um dos focos desses modelos e, para esse trabalho, foram utilizadas reportagens de um grande portal de notícias do Brasil como campo de busca. O objetivo é obter as relevantes atuações dos Deputados Federais das últimas legislaturas que foram merecedoras de serem veiculadas nesses portais.

### 2. Modelagem



### 3. Resultados

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin pulvinar nisl vestibulum tortor fringilla, eget imperdiet neque condimentum. Proin vitae augue in nulla vehicula porttitor sit amet quis sapien. Nam rutrum mollis ligula, et semper justo maximus accumsan. Integer scelerisque egestas arcu, ac laoreet odio aliquet at. Sed sed bibendum dolor. Vestibulum commodo sodales erat, ut placerat nulla vulputate eu. In hac habitasse platea dictumst. Cras interdum bibendum sapien a vehicula.

Proin feugiat nulla sem. Phasellus consequat tellus a ex aliquet, quis convallis turpis blandit. Quisque auctor condimentum justo vitae pulvinar. Donec in dictum purus. Vivamus vitae aliquam ligula, at suscipit ipsum. Quisque in dolor auctor tortor facilisis maximus. Donec dapibus leo sed tincidunt aliquam.

### 4. Conclusões

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin pulvinar nisl vestibulum tortor fringilla, eget imperdiet neque condimentum. Proin vitae augue in nulla vehicula porttitor sit amet quis sapien. Nam rutrum mollis ligula, et semper justo maximus accumsan. Integer scelerisque egestas arcu, ac laoreet odio aliquet at. Sed sed bibendum dolor. Vestibulum commodo sodales erat, ut placerat nulla vulputate eu. In hac habitasse platea dictumst. Cras interdum bibendum sapien a vehicula.

Proin feugiat nulla sem. Phasellus consequat tellus a ex aliquet, quis convallis turpis blandit. Quisque auctor condimentum justo vitae pulvinar. Donec in dictum purus. Vivamus vitae aliquam ligula, at suscipit ipsum. Quisque in dolor auctor tortor facilisis maximus. Donec dapibus leo sed tincidunt aliquam.

---

Matrícula: 123.456.789

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
