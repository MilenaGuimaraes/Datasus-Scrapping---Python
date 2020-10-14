# Datasus-Scrapping---Python

O Datasus é o O Departamento de Informática do Sistema Único de Saúde e possui como missão Promover modernização por meio da tecnologia da informação para apoiar o Sistema Único de Saúde – SUS (https://datasus.saude.gov.br/sobre-o-datasus/).
Todos os estabelecimentos de saúde reportam informações ao Datasus (especificamente ao Cadastro Nacional de Estabelecimentos de Saúde - CNES) e os dados desses estabelecimentos estão disponíveis em  ftp://ftp.datasus.gov.br/dissemin/publicos/CNES/200508_/ .

Os dados do datasus são disponibilizados em sua maioria mensalmente por estado, ano e categoria e possuem uma extensão específica (.dbc) que precisa ser convertida para um formato que possibilite tabulação. Para a conversão tabular, o datasus provê um sistema chamado TabWin, que permite converter arquivos de extensão .dbc para .bdf e a partir dessa para diversas extensões como .xlm, .csv, .cnv e até mesmo para um arquivo de query sql que possibilita criar uma tabela e inserir os dados do arquivo nessa.
Embora o TabWin cumpra o papel de quanto a conversão dos dados, o modo em que esses são disponibilizados é limitante a pesquisas de grande porte com essas informações públicas, pois além da dependência da ferramenta que só roda em sistemas Windows,  essa não é open source, o que torna o processo para melhorias lento e ineficiente e, além disso,  para a conversão de arquivo .dbf para formato tabular, é preciso abrir um arquivo por vez.Diante desses fatores limitantes, diversas iniciativas foram feitas pela comunidade de usuários interessadas no acesso a essas informações, afim de simplificar a análise desses dados. 
Esse projeto, visa apresentar uma alternativa de ao acesso a essas informações, através de um processo ETL que acessa as informações do ftp público, filtra arquivos desejados, copia dados para pasta desejada do computador, le esses arquivos, tranforma em dataframe e os empilha para posterior inserção em carga em banco de dados. 

Bibliotecas utilizadas na solução: 

os - Para acessar arquivos do sistema;
ftplib - Para acessar ftp; 
glob - Para trabalhar com listagem de arquivos do sistema; 
pandas - Para manipular dataframes; 
dbfread - Para ler arquivos de extensão dbf
