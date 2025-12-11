<h1>RBQL.csv</h1>
<p>Arquivo csv apresenta os nomes das cidades e suas respectivas informa&ccedil;&otilde;es de latitude e longitude dos laborat&oacute;rios cred&ecirc;ncias da Rede&nbsp; Brasileira de Qualidade de Leite.</p>
<h1>embrapa.csv</h1>
<p>Arquivo csv que apresenta os nomes das cidades e suas respectivas informa&ccedil;&otilde;es de latitude e longitude de unidades da Embrapa espalhadas pelo Brasil.</p>
<h1>Dataset_final.csv</h1>
<p>O arquivo csv possui 24 linhas (um para cada ano de 2000 a 2023) e 25 colunas (vari&aacute;veis). &Eacute; um dataset temporal que vai de 2000 at&eacute; 2023 coluna (year), de maneira geral pode ser dividido em 4 categorias diferentes, cada categoria possuindo dados para cada uma das regi&otilde;es do Brasil: Produ&ccedil;&atilde;o de leite regional, coluna (m&eacute;dia da produ&ccedil;&atilde;o de leite), Dados clim&aacute;ticos (temperatura e precipta&ccedil;&atilde;o) medidos em graus celsius e milimetros respectivamente, colunas (Temperatura m&eacute;dia e Precipita&ccedil;&atilde;o m&eacute;dia) Dados de pre&ccedil;o do leite, que envolve dados da m&eacute;dia de pre&ccedil;o para produ&ccedil;&atilde;o do leite, coluna (m&eacute;dia do pre&ccedil;o do leite para o produtor) e a m&eacute;dia de pre&ccedil;o do leite comercializado entre produtores, coluna (Pre&ccedil;o l&iacute;quido m&eacute;dio do leite (entre produtores)). Por fim existe dados da varia&ccedil;&atilde;o da infla&ccedil;&atilde;o, coluna (ipca_variacao).</p>
<h1>quality_data.csv</h1>
<p>O arquivo CSV possui ao total 4 Par&acirc;metros CPP, CSS, EST e ESD, agrupados por estado/regi&atilde;o e por ano de 2013 at&eacute; 2023, os valores apresentados s&atilde;o os valores m&aacute;ximos e m&iacute;nimos daquela ano respectivo para cada par&acirc;metro.</p>
<h1>script_de_processamento_leite.ipynb</h1>
<p>O arquivo apresenta os c&oacute;digos desenvolvidos utilizando python notebooks, nele s&atilde;o aplicados diferentes bibliotecas e etapas de processamento: as principais ferramentas utilizadas s&atilde;o:&nbsp;</p>
<ul>
<li>
<p><code>pandas</code> e <code>numpy</code>: Manipula&ccedil;&atilde;o e agrega&ccedil;&atilde;o de dados.</p>
</li>
<li>
<p><code>sklearn (KNNImputer)</code>: Usado para preencher dados faltantes (imputa&ccedil;&atilde;o), garantindo que o dataset final n&atilde;o tenha lacunas.</p>
</li>
<li>
<p><code>prov</code>: Biblioteca especializada para documentar a origem dos dados (proveni&ecirc;ncia), gerando diagramas de fluxo.</p>
</li>
</ul>
<p>O script processa os dados em blocos tem&aacute;ticos que correspondem diretamente &agrave;s colunas do seu CSV final:</p>
<p><strong>A. Dados de Pre&ccedil;os (Regionais)</strong></p>
<ul>
<li>
<p>O script l&ecirc; m&uacute;ltiplos arquivos CSV de pastas regionais (Sul, Sudeste, Centro-Oeste, Norte, Nordeste).</p>
</li>
<li>
<p>Renomeia colunas originais (como "Pre&ccedil;o bruto m&iacute;nimo") e calcula m&eacute;dias anuais.</p>
</li>
<li>
<p><em>Gera as colunas:</em> <code>m&eacute;dia do pre&ccedil;o do leite...</code> e <code>Pre&ccedil;o l&iacute;quido m&eacute;dio...</code>.</p>
</li>
</ul>
<p><strong>B. Dados Clim&aacute;ticos (Temperatura e Precipita&ccedil;&atilde;o)</strong></p>
<ul>
<li>
<p>Itera sobre arquivos brutos de esta&ccedil;&otilde;es meteorol&oacute;gicas (provavelmente do INMET).</p>
</li>
<li>
<p>Extrai dados de temperatura e chuva, calcula m&eacute;dias/medianas anuais para cada regi&atilde;o.</p>
</li>
<li>
<p><em>Gera as colunas:</em> <code>Temperatura m&eacute;dia...</code> e <code>Precipita&ccedil;&atilde;o m&eacute;dia...</code> para cada regi&atilde;o (SUL, SUDESTE, etc.).</p>
</li>
</ul>
<p><strong>C. Dados de Produ&ccedil;&atilde;o</strong></p>
<ul>
<li>
<p>Carrega um arquivo espec&iacute;fico de produtividade (<code>producao</code>).</p>
</li>
<li>
<p><em>Gera as colunas:</em> <code>m&eacute;dia da produ&ccedil;&atilde;o de leite...</code> (milh&otilde;es).</p>
</li>
</ul>
<p><strong>D. Dados Econ&ocirc;micos</strong></p>
<ul>
<li>
<p>Processa arquivos de infla&ccedil;&atilde;o para calcular a varia&ccedil;&atilde;o anual.</p>
</li>
<li>
<p><em>Gera a coluna:</em> <code>ipca_variacao</code>.</p>
</li>
</ul>
<h3>3. Tratamento de Dados</h3>
<p>Uma parte do script utiliza o algoritmo <strong>KNN (K-Nearest Neighbors)</strong> para preencher valores nulos.</p>
<h3>4. Documenta&ccedil;&atilde;o e Proveni&ecirc;ncia</h3>
<p>O final do script (ap&oacute;s a gera&ccedil;&atilde;o do CSV) &eacute; dedicado a criar diagramas de "Data Provenance". Ele mapeia visualmente de onde veio cada dado (ex: "INMET" -&gt; "Processamento Clim&aacute;tico" -&gt; "Dataset Final"), garantindo rastreabilidade cient&iacute;fica para o projeto.</p>
<h1>leite_visualization_script.ipynb</h1>
<h3>An&aacute;lise Geoespacial (Mapas)</h3>
<p>O script utiliza as bibliotecas <code>folium</code>, <code>geopandas</code> e <code>HTML</code> para criar visualiza&ccedil;&otilde;es interativas.</p>
<ul>
<li>
<p><strong>Dados de Entrada: </strong>define manualmente um dicion&aacute;rio <code>coordenadas_cidades</code> com latitudes e longitudes de capitais brasileiras (Rio Branco, Macei&oacute;, Macap&aacute;, etc.).</p>
</li>
<li>
<p><strong>Visualiza&ccedil;&atilde;o:</strong> Gera mapas apontando localiza&ccedil;&otilde;es, correlacionando as sedes da Embrapa ou centros de qualidade de leite com essas coordenadas.</p>
</li>
</ul>
<h1>milk_production._map.html</h1>
<p>Arquivo HTML, que permite acessar o mapa construido e que apresenta os dados do dataset de maneira din&acirc;mica, agrupados por regi&atilde;o, al&eacute;m disso apresenta as informa&ccedil;&otilde;es relacionadas a posi&ccedil;&atilde;o geogr&aacute;fica de centros de pesquisa e analise do leite (embrapa e RBQL).</p>
<h1>Prov_xxx.png</h1>
<p>Todos arquivos que come&ccedil;am com <strong>prov_&nbsp;</strong>apresentam em formato de imagem a proveni&ecirc;ncia de cada dado obtido, a imagem apresenta informa&ccedil;&otilde;es sobre o processo de obten&ccedil;&atilde;o e transforma&ccedil;&atilde;o dos dados, desde do local onde foi obtido at&eacute; ser transformado no formato dataframe para futuramente ser unificado no dataset final. Especificamente o quality_prov.png &eacute; o grafo de proveni&ecirc;ncia do dataset de qualidade.&nbsp;</p>
<h1>requirements_script_leite.txt</h1>
<p>O arquivo requirements_script_leite.txt apresenta informa&ccedil;&otilde;es das bibliotecas utilizadas no ambiente no qual o script de processamento dos dados e constru&ccedil;&atilde;o do dataset foi executado, cabo citar que o ambiente citado foi o colab, assim os principais pacotes que s&atilde;o essenciais para executar o arquivo est&atilde;o apresentado no artigo produzido.</p>
<h1>requirements_map_script.txt</h1>
<p>O arquivo requirements_script_leite.txt apresenta informa&ccedil;&otilde;es das bibliotecas utilizadas no ambiente no qual o script para o desenvolvimento da visualiza&ccedil;&atilde;o dos dados foi executado</p>
