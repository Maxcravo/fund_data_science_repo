<h1>datascience_paper_sbc (1).pdf</h1>
<a href="https://github.com/Maxcravo/fund_data_science_repo/blob/main/datascience_paper_sbc%20(1).pdf">datascience_paper_sbc</a>
<p>PDF file that contains the article write STILL IN PROGRESS </p>
<h1>Datascience_Apresentação_final.pdf</h1>
<a href="https://github.com/Maxcravo/fund_data_science_repo/blob/main/Datascience_Apresenta%C3%A7%C3%A3o_final.pdf">Datascience_Apresentação_final</a>
<p>PDF file that contains the presentation made for the discipline</p>

<h1>RBQL.csv</h1>
<p>CSV file presenting the names of cities and their respective latitude and longitude information for laboratories accredited by the Brazilian Milk Quality Network.</p>
<h1>embrapa.csv</h1>
<p>CSV file presenting the names of cities and their respective latitude and longitude information for Embrapa units scattered across Brazil.</p>
<h1>Dataset_final.csv</h1>
<p>The CSV file has 24 rows (one for each year from 2000 to 2023) and 25 columns (variables). It is a temporal dataset ranging from 2000 to 2023 column (year). Generally, it can be divided into 4 different categories, each possessing data for every region of Brazil: Regional milk production, column (average milk production); Climate data (temperature and precipitation) measured in degrees Celsius and millimeters respectively, columns (Average temperature and Average precipitation); Milk price data, involving average production price data, column (average milk price for the producer) and the average price of milk traded between producers, column (Average net milk price (between producers)). Finally, there is inflation variation data, column (ipca_variacao).</p>
<h1>quality_data.csv</h1>
<p>The CSV file contains a total of 4 Parameters CPP, CSS, EST, and ESD, grouped by state/region and by year from 2013 to 2023. The values presented are the maximum and minimum values of that respective year for each parameter.</p>
<h1>script_de_processamento_leite.ipynb</h1>
<p>The file presents the code developed using python notebooks, in which different libraries and processing steps are applied: the main tools used are:&nbsp;</p>
<ul>
<li>
<p><code>pandas</code> and <code>numpy</code>: Data manipulation and aggregation.</p>
</li>
<li>
<p><code>sklearn (KNNImputer)</code>: Used to fill in missing data (imputation), ensuring the final dataset has no gaps.</p>
</li>
<li>
<p><code>prov</code>: Library specialized in documenting data origin (provenance), generating flow diagrams.</p>
</li>
</ul>
<p>The script processes data in thematic blocks that correspond directly to the columns of your final CSV:</p>
<p><strong>A. Price Data (Regional)</strong></p>
<ul>
<li>
<p>The script reads multiple CSV files from regional folders (South, Southeast, Center-West, North, Northeast).</p>
</li>
<li>
<p>Renames original columns (such as "Minimum gross price") and calculates annual averages.</p>
</li>
<li>
<p><em>Generates the columns:</em> <code>average milk price...</code> and <code>Average net price...</code>.</p>
</li>
</ul>
<p><strong>B. Climate Data (Temperature and Precipitation)</strong></p>
<ul>
<li>
<p>Iterates over raw files from meteorological stations (likely from INMET).</p>
</li>
<li>
<p>Extracts temperature and rain data, calculates annual averages/medians for each region.</p>
</li>
<li>
<p><em>Generates the columns:</em> <code>Average temperature...</code> and <code>Average precipitation...</code> for each region (SOUTH, SOUTHEAST, etc.).</p>
</li>
</ul>
<p><strong>C. Production Data</strong></p>
<ul>
<li>
<p>Loads a specific productivity file (<code>producao</code>).</p>
</li>
<li>
<p><em>Generates the columns:</em> <code>average milk production...</code> (millions).</p>
</li>
</ul>
<p><strong>D. Economic Data</strong></p>
<ul>
<li>
<p>Processes inflation files to calculate the annual variation.</p>
</li>
<li>
<p><em>Generates the column:</em> <code>ipca_variacao</code>.</p>
</li>
</ul>
<h3>3. Data Treatment</h3>
<p>Part of the script uses the <strong>KNN (K-Nearest Neighbors)</strong> algorithm to fill in null values.</p>
<h3>4. Documentation and Provenance</h3>
<p>The end of the script (after CSV generation) is dedicated to creating "Data Provenance" diagrams. It visually maps where each piece of data came from (e.g., "INMET" -> "Climate Processing" -> "Final Dataset"), ensuring scientific traceability for the project.</p>
<h1>leite_visualization_script.ipynb</h1>
<h3>Geospatial Analysis (Maps)</h3>
<p>The script uses the <code>folium</code>, <code>geopandas</code>, and <code>HTML</code> libraries to create interactive visualizations.</p>
<ul>
<li>
<p><strong>Input Data: </strong>manually defines a dictionary <code>coordenadas_cidades</code> with latitudes and longitudes of Brazilian capitals (Rio Branco, Maceió, Macapá, etc.).</p>
</li>
<li>
<p><strong>Visualization:</strong> Generates maps pointing out locations, correlating Embrapa headquarters or milk quality centers with these coordinates.</p>
</li>
</ul>
<h1>milk_production._map.html</h1>
<p>HTML file, which allows access to the constructed map and presents the dataset data dynamically, grouped by region. Furthermore, it presents information related to the geographic position of milk research and analysis centers (Embrapa and RBQL).</p>
<h1>Prov_xxx.png</h1>
<p>All files starting with <strong>prov_&nbsp;</strong>present the provenance of each obtained datum in image format. The image presents information about the data acquisition and transformation process, from the location where it was obtained until being transformed into the dataframe format to be unified in the final dataset in the future. Specifically, quality_prov.png is the provenance graph of the quality dataset.&nbsp;</p>
<h1>requirements_script_leite.txt</h1>
<p>The file requirements_script_leite.txt presents information on the libraries used in the environment where the data processing and dataset construction script was executed. It is worth mentioning that the cited environment was Colab, so the main packages essential to run the file are presented in the produced article.</p>
<h1>requirements_map_script.txt</h1>
<p>The file requirements_script_leite.txt presents information on the libraries used in the environment where the script for the development of data visualization was executed.</p>
