Precisamos aprender a andar de ÔNIBUS!

A interface das carteiras e das exchanges precisam melhorar para melhor atender os seus usuários, mostrar novas opções opcionais.

As carteiras precisam acompanhar os últimos blocos para ter uma ideia dos fees, analisar a distribuição da densidade dos fees nos blocos, mostrar um gradiente de urgência para o usuário poder se posicionar (ao invés de apenas "devagar"/"rápido"), uma estimativa do tempo esperado com base em provedores deste serviço (um nó que tenha um mempool rasoável) e a densidade dos fees da transação a ser feita em si.

As carteiras também precisam mostrar não apenas a somatória do saldo do usuário, mas sim cada saldo individualmente, contido nas pontas das cadeias de transações em seu controle. Cada saída de transação (não gasta) deve ser visualizada individualmente, para que então o usuário possa combiná-las da forma que achar mais viável, de forma que estas saídas não gastas possam de fato serem gastas através de uma transação nova. Porém cada saída desta transação nova também deve ser mostrada individualmente, de forma que o usuário também possa as combinar de forma mais viável.

Tudo isso tem o objetivo de economizar )espaço na blockchain( em fees.

Uma transação pode ter várias entradas e várias saídas. Cada entrada aponta para uma saída ainda não gasta de uma transação que ocorreu no passado. Cada saída descreve o endereço que estará autorizado a gastar tal saída, e também define as condições para que tal gasto seja válido (por meio de um script primitivo, no qual, geralmente, autoriza apenas quem implicitamente conhecer a chave privada da chave pública utilizada para assinar a própria transação).
Quando você não envia todo o saldo contido na saída de uma transação, você precisar enviar o que sobra, excluindo os fees, de volta para um endereço sob seu controle. Porém isso é uma saída a mais. Como cada saída consome espaço, você pode estar pagando mais fee à toa, dependendo do seu caso de uso.

É como pedir um táxi, no qual ele vai te cobrar para ir buscar o seu saldo, para levar o dinheiro ao seu destinatário e também vai te cobrar para te levar o seu troco. Seria mais barato se posicionar, se possível, de maneira que você não precisará de nenhum troco. Daí você paga apenas pela busca do seu saldo e pelo envio ao destinatário.

Aproveitando: se você precisa mandar para várias pessoas, é melhor mandar na mesma viagem. O táxi vai te cobrar pela viagem para cada destinatário, mas ao menos vai te cobrar apenas uma vez para buscar o seu saldo. Se você fizer uma transação para cada destinatário, pagará por cada viagem ao seu saldo. E poderia ser pior, pois a carteira pode combinar saldos diferentes (lembra? os saldos estão nas saídas não gastas de transações passadas), de forma que o táxi irá te cobrar por cada viagem a cada saldo.

Portanto, se você precisará fazer uma transação e enviar X, mas tem a espectativa de enviar Y para três pessoas diferentes no futuro, você pode já colocar X numa saída, mais 3 saídas com um Y cada, e mais uma saída com o seu troco. Pode parecer mais caro fazer isso, porém no futuro, você pode economizar fees por não precisar pagar por três envios de troco. Isso pode parecer que dá na mesma (você adiantou 3 saídas para economizar em 3 saídas), porém no final desta situação, você tem apenas uma saída de troco restante, ao invés de ter três. Daí se quisesse gastar tudo que você tem, precisará pagar por apenas uma busca do saldo (ao invés de três - mais fragmentado), portanto, como disse anteriormente, dependendo do seu caso de uso, você pode economizar fees se posicionar suas transações estrategicamente (do inglês: strategy).

Acredito que as exchanges consideram estas coisas ao receber/enviar bitcoin de/para seus clientes. Mas vou considerar que não fazem isso, para simplificar.

Cada usuário, pra cada situação específica, tem a sua preferência entre fee e tempo de espera. Economizar em fee dado o mesmo tempo de espera é melhor; e ecomizar e tempo de espera dado o mesmo fee é melhor. As exchanges podem melhor gerenciar isso se abrirem a gama de opções que são a escolha dos encadeamentos das transações.

Creio que seria do interesse dos usuários adotarem padrões para as quantidades de transações. Quero dizer, aqueles que adotarem um padrão poderão aumentar suas chances de economizar em fees, dependendo do seu caso.
Portanto uma opção seria ter um padrão de saldo para "saídas disponíveis" aos usuários, de forma que o usuário, ao depositar, já deposita num padrão que provavelmente será utilizado por outro usuário no saque (lucro pra exchange e também para o usuário). E também de preferência, que este usuário, no depósito, não envie troco para ele mesmo (lucro pro usuário).
Portanto se um usuário for sacar de uma saída padronizada, ele não precisaria pagar pelo troco da exchange - economizando em fee mas perdendo em maleabilidade de saque. Porém se ele espera que futuramente utilizará tal transação também sem precisar enviar troco para si mesmo, ele evita de gastar o fee do troco novamente, e na prática não perdeu tanto em maleabilidade.

Outra opção seria como planejar uma viagem de ônibus. Você pega alguns acentos deste ônibus (de acordo com o saldo daquela transação) e possivelmente espera ele enxer. Se a exchange pagar as pessoas desta forma, de novo, elas economizam em taxa de troco.
A dinâmica da escolha destes acentos me é incerta. Vários pontos poderiam estar em jogo, como: a reserva de um (ou mais) ônibus, o quão antecipado foi esta reserva; pegar o último lugar antes do ônibus sair, etc. Tudo tem implicações sobre o quão dispostos os usuários estão em pagar mais fees e esperar mais pela confirmação da transação. Me parece que seria ótimo se os usuários pudessem "competir" pelas reservas e pelas vagas dos ônibus: os que reservam (que tem um tempo de partida mais certo, e provavelmente conseguem sacar com bastante maleabilidade) se comprometem a pagar pelo valor do troco (se existir), enquanto os sem reservas competem para pegar os assentos disponíveis.

Existem vários algoritmos sobre esta questão, sobre como preencher e liberar o espaço em heap da memória ram, por exemplo. Mas creio que tais algoritmos seria mais úteis como suporte a um sistema que facilita a coordenação e sincronização das transações de seus usuários.

Creio que isso também vale para as outras criptos ;)
E espero que tenha gostado!
