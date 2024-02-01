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

Este trabalho visa criar uma ferramenta para que a sociedade acompanhe as atividades dos políticos brasileiros pós-eleições e início das atividades nos cargos. Utilizando uma API para coletar notícias políticas do site G1 (https://g1.globo.com/politica) desde dezembro de 2023, a ferramenta emprega a biblioteca spaCy para identificar os nomes dos políticos nas reportagens (NER). Também incorpora dados da API da Câmara dos Deputados sobre os legisladores das últimas duas legislaturas para ser a base de referência de busca. Para mensurar similaridade, optou-se por utilizar um modelo pré-treinado baseado em BERT, disponível (bert-base-portuguese-cased-assin2-similarity). A ferramenta calcula scores de similaridade, filtrando com um ponto de corte para garantir precisão das buscas. Para complementar e ampliar a análise, a API da OpenAI, com o GPT, é utilizada para sumarizar as notícias, extrair palavras-chave e trazer o específico envolvimento do político na notícia. Os resultados são apresentados em um painel no Power BI, tornando as informações acessíveis aos usuários. Este trabalho representa uma contribuição significativa para o acompanhamento transparente e participativo das atividades políticas, oferecendo à sociedade uma visão mais detalhada e crítica do cenário político brasileiro.

### Abstract

This dissertation aims to develop an innovative tool for society to monitor the activities of Brazilian politicians post-elections and the commencement of their terms. Leveraging an API to gather political news from the G1 website (https://g1.globo.com/politica) since December 2023, the tool utilizes the spaCy library for Named Entity Recognition (NER) to identify politicians' names in news articles. Additionally, it incorporates data from the Chamber of Deputies API, providing information on legislators from the last two legislative terms as a reference base. To measure similarity, a pre-trained BERT-based model was employed, accessible at (bert-base-portuguese-cased-assin2-similarity). The tool calculates similarity scores, applying a cutoff point to ensure search accuracy. To enhance the analysis comprehensively, the OpenAI API, featuring GPT, is employed to summarize news articles, extract keywords, and delineate the specific involvement of politicians in the news. The outcomes are presented on a Power BI dashboard, rendering information accessible to users. This work constitutes a significant contribution to transparent and participatory monitoring of political activities, providing society with a more detailed and critical perspective on the Brazilian political landscape.

### 1. Introdução

O papel dos políticos, especialmente dos deputados federais, é fundamental para duas tarefas: legislar e fiscalizar. Como guardiões do interesse público, esses representantes eleitos são incumbidos da responsabilidade de criar leis e advogar pelas necessidades de seus eleitores. No entanto, no cenário pós-eleitoral, frequentemente ocorre lacuna entre as promessas feitas durante as campanhas e o que, de fato, pode ser notado no exercício do cargo. Essa desconexão entre promessas e realidade exige um acompanhamento atento dos eleitores.

Este trabalho de conclusão de curso visa abordar essa crescente demanda por transparência e responsabilidade dos cidadãos na política brasileira e como modelos de Processamento de Linguagem Natural podem nos apoiar nessa missão. A extração de informações relevantes e direcionadas ao objetivo, em grandes cadeias textuais, é um dos focos desses modelos e, para esse trabalho, foram utilizadas reportagens de um grande portal de notícias do Brasil como campo de busca. O objetivo é obter as relevantes atuações dos Deputados Federais das últimas legislaturas que foram veiculadas nesses portais.

### 2. Modelagem

O resultado obtido na modelagem é derivado de uma tentativa de utilizar diversas ferramentas de indexação e busca de linguagem natural para conseguir extrair análises específicas. Toda a modelagem foi direcionada para a construção de steps necessários para cumprir o objetivo de filtrar as notícias relacionadas dos políticos e posterior entendimento da relação da personalidade política com o que foi veiculado na reportagem.
A seguir tem-se a relação dos steps percorridos na codificação, para atingir o resultado final:

1) Busca de notícias via RSS: Foi criada uma estrutura de busca e armazenagem de notícias do site G1 (Seção Política) através de RSS disponilizado pelo Globo.com. O RSS (Really Simple Syndication) é um formato de distribuição de informações em tempo real pela internet e os arquivos são disponibilizados em formato XML, que puderam ser facilmente lidos e convertidos para CSV para armazenagem usando a biblioteca Beautiful Soup.
2) Captura de Entidades Nomeadas: Para este passo, foi necessário utilizar a técnica conhecida como NER - Named Entity Recognition. Para tal, o Spacy foi a biblioteca escolhida. Além de reconhecer entidades e visando ser mais preciso nas buscas, foram filtradas apenas rotulações de pessoas (=PER) nas notícias. O resultado obtido foi uma lista com os nomes citados em cada uma das notícias. Vale ressaltar que não necessariamente esses nomes são os nomes dos políticos.
3) Similaridade de texto usando BERT: A avaliação da similaridade textual foi necessária para filtrar adequadamente os nomes já identificados na etapa anterior e compará-los com a base de dados de nomes dos políticos para os quais é almejado realizar a busca. Essa base de políticos de referência pode ser expandida conforme a necessidade. Para o trabalho aqui apresentado, restringiu-se aos Deputados Federais. A lista destes foi obtida e incorporada ao código usando uma API com dados atualizados, fornecida pela Camara Legislativa Brasileira. O limiar de similaridade estabelecido na busca foi ligeiramente inferior ao ponto considerado como correspondência completa. Essa decisão foi tomada visando a uma abordagem mais abrangente, permitindo ao usuário final, durante as análises no Relatório em Power BI, a autonomia para escolher o intervalo desejado para o score de similaridade.

Estes 3 primeiros steps podem ser observados no código disponível nesse arquivo: [Extração Notícias G1 NER e Similaridade](2024_01_19ExtraçãoNotíciasG1SpicyIncremental.ipynb)



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
