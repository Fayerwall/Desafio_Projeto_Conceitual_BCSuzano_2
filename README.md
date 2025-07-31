# Desafio_Projeto_Conceitual_BCSuzano_2
Diferentemente do primeiro, esse desafio foi de modelar do 0 utilizando EER um sistema de gerenciamento de Ordens de Serviço, de uma oficina mecânica.

A narrativa passada no bootcamp para a realização do modelo foi:

1.Sistema de controle e gerenciamento de execução de ordens de serviço em uma oficina mecânica
2.Clientes levam veículos à oficina mecânica para serem consertados ou para passarem por revisões  periódicas
3.Cada veículo é designado a uma equipe de mecânicos que identifica os serviços a serem executados e preenche uma OS com data de entrega.
4.A partir da OS, calcula-se o valor de cada serviço, consultando-se uma tabela de referência de mão-de-obra
5.O valor de cada peça também irá compor a OS
6.O cliente autoriza a execução dos serviços
7.A mesma equipe avalia e executa os serviços
8.Os mecânicos possuem código, nome, endereço e especialidade
9.Cada OS possui: n°, data de emissão, um valor, status e uma data para conclusão dos trabalhos.

Criei, a princípio, 4 tabelas, sendo elas "Cliente", "Mecânico", "Veículo" e "OS" e, a partir daí, me atentei a suas relações.
Relacionei Cliente e veículo (1:n), onde um cliente pode ter mais de um veículo. 
A princípio iria fazer uma relação n:m entre veículo e mecânico, onde vários mecânicos poderiam ser atribuídos a um veículo, porém, como na narrativa é passada a ideia de uma equipe, criei uma nova tabela equipe, onde vários mecânicos poderiam estar em uma equipe apenas (1:n), e relacionei a equipe a veículo, onde diversos veículos poderiam estar atribuídos a uma equipe (1:n, imaginando que não seja atribuído mais de uma equipe a um único veículo, embora essa questão não seja abordada). 
Essa equipe, além disso, é relacionada a OS (ordens de serviço), nesse caso, muitas OS podem estar relacionada a uma equipe (1:n).Essa tabela OS contém sua data de emissão e de conclusão (que imaginei ser também a data de entrega, mas podendo ser adicionada outro atributo na tabela para essa data, caso sejam diferentes), o Status e seu valor total.
Para chegar a esse valor total, criei outras duas tabelas, "Serviços" e "Peças", a primeira com o nome do serviço, descrição e valor, e a segunda com nome, valor e quantidade disponível (optei por essas tabelas separadas pela própria narrativa conter uma "tabela de referência"). relacionei ambas a OS, onde diversos serviços podem ser prestados e peças podem ser utilizadas em diversas OS diferentes (n:m).
A narrativa diz que o cliente autoriza a execução dos serviços, mas imagino que isso possa ser apenas um tipo de status dentro da própria OS, como "aguardando autorização do cliente" e "autorizada". Além disso, por ja existir uma relação entre equipe e OS, ja que a mesma equipe avalia e executa os serviços, não achei necessário realizar outro relacionamento entre eles, ja que o status da OS pode ser "em execução".

Obs.: Assim como no primeiro projeto, a workbench foi usada apenas como ferramenta para modelagem do modelo EER, as questões relacionadas a chaves primárias/estrangeiras não são o foco desse projeto, podendo ser corrigidos posteriormente, caso exista algum equívoco.
