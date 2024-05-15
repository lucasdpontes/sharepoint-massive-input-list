# Input massivo de registros em lista de SharePoint
## sharepoint-massive-input-list

O objetivo deste projeto é fornecer uma solução para criar registros massivos nas Listas (ou tabelas) no ambiente Share Point, em cenários nos quais não é possível utilizar o Power Automate.

Seu princípio básico de funcionamento é, através da biblioteca Selenium, simular ações humanas para preencher o formulário de criação de itens da Lista, cuja fonte de dados é um arquivo em Excel.

É possível adaptá-lo para outros tipos de fontes de dados, através do ajuste das referências à fonte e variáveis (coluna_a, ... coluna_j).

A coluna de controle 'Cadstrado' determina se um registro será criado ou não (nesse exemplo, isso só ocorre nas linhas vazias e com as demais colunas preenchidas, para evitar o cadastro de registros incompletos).

Ao criar um registro, a coluna de controle é atualizada para 'Sim' e, ao se deparar com colunas vazias (ou com o valor 'Pular'), a mesma é atualizada para 'Não'.

Caso haja falha no código, basta executá-lo novamente para voltar a criação dos registros de onde parou.

É recomendado fazer um backup da fonte de dados, pois há a possibilidade do arquivo ser corrompido devido à alta taxa de atualização, ou desativar o antivirus para evitar conflitos.

! A interação com os campos de formulário varia de acordo com seu tipo. Nesse projeto, temos:
- Coluna A, B, C, E, F, I: seleção única
- Coluna D, G e J: texto
- Coluna H: data e hora
