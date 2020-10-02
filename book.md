# Introdução

Apenas uma pequena percentagem dos grandes projetos de software do governo são bem-sucedidos. Os projetos estaduais de tecnologias de informação, em particular, costumam correr mal porque o estado não possui conhecimentos básicos sobre o desenvolvimento de software moderno e dependende de processos de aquisição desatualizados. Todos os anos, o governo gasta muito dinheiro em projetos para manter e modernizar os sistemas de TI usados, mas os esforços para modernizar esses sistemas legados fracassam a uma taxa alarmante e com grande custo para o nosso orçamento.

A nossa administração pública depende cada vez mais de software e hardware modernos para implementar programas e fornecer serviços essenciais ao público, e o sucesso de qualquer iniciativa depende do sucesso da infraestrutura de software subjacente. Todas as entidades governamentais enfrentam desafios semelhantes, enfrentando restrições de orçamento e de pessoal enquanto lutam para modernizar os sistemas de tecnologia legados que estão desatualizados e são inflexíveis, caros e ineficazes. Funcionários da administração pública muitas vezes contam com os mesmos processos antigos que levaram aos problemas em primeiro lugar.

O público merece um governo que forneça a mesma tecnologia de topo que consegue obter no mercado comercial. A confiança no governo depende disso.

Este manual foi elaborado para executivos, especialistas em orçamento, legisladores e outros tomadores de decisão "não técnicos" que financiam ou supervisionam projetos de tecnologia do governo e implementam a tecnologia necessária para apoiar a administração pública. Ele pode ajudá-lo a preparar esses projetos para o sucesso, fazendo as perguntas certas, identificando os resultados certos e, igualmente importante, capacitá-lo com o conhecimento básico dos princípios fundamentais do design e construção de software moderno.

Este manual também fornece as ferramentas de que precisa para começar a lidar com problemas relacionados, como:

- A necessidade de simultaneamante usar, manter e modernizar sistemas legados
- Organizações isoladas e culturas avessas ao risco
- Longos ciclos de orçamento que nem sempre correspondem às práticas modernas de design de software
- Ameaças à segurança
- Contratação, pessoal e outras restrições de recursos

Este documento foi escrito especificamente para a aquisição de software feito à medida, mas é importante reconhecer que o software comercial genérico é frequentemente customizado e que o Software como Serviço frequentemente requer código customizado. Assim que qualquer personalização for feita, a maioria dos conselhos neste manual aplicam-se a essas ofertas comerciais. (Consulte "Cuidado com a armadilha de software comercial personalizado" para obter detalhes.)

Como funcionários governamentais, devemos ser bons administradores do dinheiro público, exigindo ferramentas digitais sustentáveis, económicas e fáceis de usar pelo público e funcionários da administração pública. Este manual ajudá-lo-á a fazer exatamente isso.

# Princípios Básicos

## Princípios básicos do design moderno de software

As hipóteses de sucesso de um projeto de tecnologia aumentam quando os líderes governamentais "não técnicos" que o financiam e supervisionam entendem seis conceitos básicos do desenvolvimento de software moderno: **design centrado no utilizador**, **desenvolvimento ágil de software**, **DevOps**, **construção com peças fracamente acopladas**, **contratação modular** e **propriedade do produto**. O leitor não precisa ser um tecnólogo para entender esses conceitos gerais. Depois de entendê-los, parecerá que ganhou um novo superpoder, permitindo-lhe distinguir o jargão e os detalhes técnicos e manter o foco no básico para orientar com sucesso qualquer projeto de software.


### Design centrado no utilizador

Todo o desenvolvimento de software deve ser centrado nas necessidades dos utilizadores finais reais do software, as pessoas específicas que devem usá-lo. Esses "utilizadores finais" podem ser cidadãos-alvo, funcionários de atendimento ao público, funcionários, outros funcionários do estado ou qualquer um de inúmeros outros grupos.

Projetar **com e para** os utilizadores reduz os riscos do projeto, garantindo que o software está resolvendo problemas reais (ao contrário do que algumas partes interessadas pensam que os problemas realmente são). Esses problemas são identificados por meio de uma variedade de táticas de pesquisa que incluem entrevistas e testes de usabilidade.

No design centrado no utilizador, todo o trabalho está a serviço das necessidades dos utilizadores finais. Esse trabalho é identificado e priorizado em colaboração próxima e regular com os utilizadores finais e é informado por, mas não subserviente a, quaisquer restrições técnicas. (Ou seja, o objetivo do trabalho é entregar valor aos utilizadores, o que envolve lidar com as realidades das linguagens de programação ou software de servidor aprovados, mas o trabalho nunca deve ser omitido por causa da percepção de que restrições técnicas o tornariam impossível.) A equipa técnica e os utilizadores finais revêem regularmente o trabalho, conforme ele está sendo executado, e o trabalho de desenvolvimento no novo software não é considerado concluído até que os utilizadores finais concordem que suas necessidades foram atendidas. Projetar com e para os utilizadores reduz os riscos do projeto, garantindo que o software está resolvendo os problemas dos utilizadores.


### Desenvolvimento ágil de software

Planos detalhados e de longo prazo para grandes projetos de software feitos à medida sempre foram a norma no governo. Mas, como engenheiros de software e gestores de projeto aprenderam ao longo dos anos, esses planos nunca estão corretos. Eles precisam de muitas modificações caras, levando a pedidos de mais dinheiro para pagar por "pedidos de alteração". Está na altura de os executivos do governo e responsáveis por orçamentos pararem de pedir planos detalhados de longo prazo e, em vez disso, fazerem o orçamento para projetos de software de uma nova forma.

O planeamento antecipado de um projeto inteiro é conhecido como desenvolvimento em "cascata". Imagine planejar um mês de férias com a família de carro pela Europa. Sob a cascata, isso envolveria um planeamento antecipado da agenda de cada dia, incluindo percurso exato, a reserva de cada quarto de hotel, o pré-pagamento de todas as refeições, a pré-compra de ingressos para entrada em atrações, etc. Isso nunca funcionaria porque as coisas mudam, surgem opções inesperadas, e nenhuma pessoa racional gostaria de tomar todas as decisões no início da jornada quando não sabe o que a jornada trará. Em vez disso, a maioria das pessoas planearia a rota geral a ser seguida e planearia apenas algumas paragens principais - os detalhes seriam resolvidos à medida que progredissem ao longo do caminho.

"Desenvolvimento ágil de software" refere-se ao uso dessa metodologia de planeamento de viagem para construir e modernizar sistemas de software. Em vez de depender de anos de planeamento caro e "compilação de requisitos" antes de começar a escrever software real, os projetos de desenvolvimento ágil são planeados apenas em linhas gerais, com uma descrição bem definida do objetivo geral do projeto e uma forte preferência por _apenas começar_. Uma equipa pequena, com poderes e automotivados (geralmente de 5 a 9 pessoas, incluindo desenvolvedores, gerentes de produto, pesquisadores de utilizadores, escritores e / ou especialistas em segurança) se dedica a cumprir esse objetivo, usando design centrado no utilizador, trabalhando em ciclos semanais para entregar algum software que realmente funcione.

No primeiro dia, a equipa planeia apenas o que fará nas próximas duas semanas. (A duração dos ciclos de um projeto pode ser tão breve quanto uma semana ou até quatro semanas - duas semanas é o mais comum.) Cada tarefa que eles trabalharão tem a forma de uma "história de utilizador" - uma necessidade específica do utilizador revelada pela pesquisa. A coleção inteira de histórias de utilizador a serem trabalhadas é chamada de "backlog".

A equipa trabalha num grupo selecionado destas "histórias de utilizador" por duas semanas e, no final, a equipa analisa o trabalho que eles fizeram, testa-o com os utilizadores finais e, em seguida, planeia as próximas duas semanas retirando mais histórias de utilizador do backlog. Repetir. Cada um desses ciclos de duas semanas é denominado "sprint".

No início, o software que produzido pode não parecer muito (e pode até mesmo ser substituído por algo mais tarde), mas irá informar gradual e sistematicamente a abordagem técnica do projeto e ajudar a equipa a integrar o projeto de forma sensata no sistema pré-existente.

O software funcional é entregue no final de cada sprint, sem exceção - totalmente testado, totalmente documentado, pronto para ser usado. Dessa forma, o valor é entregue constantemente, até que o software seja bom o suficiente para ser implementado para uso amplo. A equipa continua a trabalhar até cumprir todas as metas ou ficar sem dinheiro, o que ocorrer primeiro.

O fornecedor é pago pelo tempo de seus funcionários, não por um sistema de software. Tudo criado pelo fornecedor - software, documentação, pesquisa, projetos, _tudo_ - é propriedade do governo, entregue ao governo no final de cada sprint. Mudanças tecnológicas, mudanças nas políticas governamentais, mudanças nas regulamentações, mudanças nas leis e mudanças nas prioridades da liderança - qualquer projeto planejado em grande detalhe no início não será capaz de se adaptar a essas mudanças e correrá um risco significativo de falha, derrapes de custo e prazo significativos ou "pedidos de mudança" caros.

Ao combinar a agilidade com o design centrado no utilizador, uma equipa de desenvolvimento pode iterar constantemente para resolver as necessidades dos utilizadores finais de maneiras que seriam impossíveis de aprender antecipadamente.


### Propriedade do produto

A reapropriação dos projetos de software pelo governo requer que as equipas do governo se concentrem nos resultados e não nas métricas. Isso significa mudar de algumas das práticas tradicionais do gestão de projetos para uma mentalidade orientada para o produto.

A palavra "produto" pode soar incomum em um contexto governamental, mas é uma parte importante do jargão tecnológico. "Produto" é uma abreviatura para qualquer coisa que está sendo criada: um site, uma aplicação iOS, uma aplicação web, etc. Embora a palavra faça mais sentido para uma empresa que está vendendo um produto tangível, todo o resto sobre este conceito se traduz perfeitamente para o governo.

O proprietário do produto é a pessoa-chave para qualquer projeto de software e _deve_ ser um funcionário do governo. O dono do produto trabalha com utilizadores, partes interessadas, tecnólogos e o fornecedor para prever a direção para o produto, com o objetivo de entregar valor aos utilizadores finais o mais rápido possível. Ele prioriza e define iterativamente o trabalho para a equipa de produto, como parte do processo ágil. Ele mede o progresso em relação a indicadores de desempenho ​​claros e  comunica com as partes interessadas e a equipa multifuncional que está construindo o produto.

O proprietário do produto não precisa ser um tecnólogo forte. Em vez disso, ele deve conhecer os utilizadores do sistema, a empresa e as restrições legais e políticas.

Um proprietário de produto forte garante que a visão seja clara, a estratégia seja clara, que há espaço para que as equipas que criam o software aprendam, assegurando-se de que estão construindo ou comprando a coisa certa para, incrementalmente, mostrar valor aos utilizadores. Eles priorizam implacavelmente para garantir que o produto corresponda às necessidades do utilizador e que a atividade e a atenção sejam focadas nas necessidades de maior prioridade. Eles são habilitados pelo seu departamento para representar as partes interessadas e tomar de decisões rápidas sobre o produto, sem que haja a necessidade de muitas camadas de aprovação. Esse posicionamento garante que o proprietário do produto entenda tudo o que a equipa de desenvolvimento está a fazer e que as necessidades do governo sejam totalmente representadas.
As chances são boas de que a maior parte do software que você usa todos os dias, seja no telefone ou no computador, foi escrita exatamente assim. No DevOps, testar a qualidade do software é automático, testar a segurança do software é automático, fundir o trabalho de vários desenvolvedores é automático e mover o software completo para os servidores é automático. (A incorporação de testes de segurança no DevOps às vezes é rotulada como "DevSecOps".)no detalhado de 5 anos. Mas ele terá uma visão dos resultados que serão entregues aos utilizadores e terá um caminho para a execução. O seu trabalho mais importante é entender o que a equipa de desenvolvimento está a fazer e garantir que se encontre o equilíbrio certo entre as necessidades do governo e as necessidades dos utilizadores finais.

É possível que um proprietário de produto principiante aprenda durante o decorrer do processo, mas é melhor que seja treinado com antecedência. Existem muitas fontes de treino ágil e scrum, algumas especificamente para proprietários de produtos, entre séries de vídeos do YouTube e aulas presenciais de vários dias para se tornar um "Dono de Produto Certificado Scrum". Quanto mais importante o projeto, mais formal e rigoroso deve ser o treino do proprietário do produto.

[ATENÇÃO: "PROPRIETÁRIO DO PRODUTO" ???]


### DevOps

Historicamente, as equipas de desenvolvimento de software são separadas das equipas de TI responsáveis ​​por operar o software. Um fornecedor pode passar anos a criar um novo software e, em seguida, uma equipa de TI do governo (ou um fornecedor que desempenhe essa função) pode exigir muitos meses de trabalho para fazer com que o software funcione corretamente nos seus servidores. Isso geralmente é acompanhado por frustração e acusações, e pode levar a falhas no projeto. Para resolver isso, as agências governamentais costumam insistir que o fornecedor que constrói o software também o aloje indefinidamente na infraestrutura do fornecedor, o que tem o efeito de descartar a maioria dos fornecedores de software (que não estão no negócio de alojamento) e criar uma dependência do fornecedor, com altos preços associados. Contar com essas abordagens antigas vai lhe render menos e custar mais do que se adotasse as metodologias de software modernas que são padrão no setor privado.

A maneira de resolver isso é com DevOps. DevOps é a prática de coordenar o trabalho desses dois grupos para automatizar os testes ao software e disponibilizá-lo num servidor ativo onde as pessoas possam usá-lo - misturando **desenvolvimento** de software e **operações** de sistema. Os programadores escrevem uma série de processos automatizados para garantir que o software funciona corretamente em produção, durante a criação do próprio software. Os programadores não podem simplesmente dar o seu trabalho por concluído e entregá-lo à equipa de operações do sistema e declarar "ei, funciona para nós" - eles são responsáveis, tanto prática quanto contratualmente, por que o seu código funcione corretamente no ambiente designado.

Há uma grande probabiliadde de que a maioria do software que você usa todos os dias, seja no telefone ou no computador, tenha sido escrita exatamente assim. Em DevOps, a qualidade e a segurança do software é testada automaticamente, fundindo o trabalho de vários programadores é automático e disponibilizar o software completo nos servidores é automático. (A incorporação de testes de segurança no DevOps às vezes é rotulada como "DevSecOps".)


### Construindo com peças fracamente acopladas

Projetos de software grandes e complexos tendem a entrar em colapso sob o peso da administração. Nenhum programador pode compreender todo o sistema para o qual está contribuindo, e cada novo membro adicionado a uma equipe de projeto aumenta a complexidade das interações da equipa inteira, obrigando a novas funções de supervisão tais como "arquitetos de software", com quem os programadores devem conferir antes de fazer qualquer trabalho. Os colaboradores precisam de coordenar-se entre si cuidadosamente para evitar conflito e sobreposição entre os seus esforços. À medida que uma equipe cresce, eles são forçados a gastar cada vez mais tempo gerindo o projeto e diminuindo o tempo que passam a realizar o trabalho em si.

Para evitar esse destino, é mais inteligente dividir grandes projetos num punhado de pequenos projetos de software quase independentes. Neste modelo, cada componente comunica com outros componentes por meio de padrões simples e modulares, de forma que qualquer peça pode ser trocada a qualquer momento. Em vez de construir um monólito que todos lamentarão em alguns anos, você constrói um pequeno ecossistema, no qual cada peça pode ser atualizada e modificada facilmente, conforme a necessidade. Cada componente é mantido por uma única equipe ágil, que documenta a interface de programação (API) do componente - as regras gramaticais que outros componentes podem usar para se comunicar com ele. A necessidade de coordenação entre equipes é mínima, porque elas podem simplesmente seguir a documentação da API de outros componentes com os quais precisam interagir.

Quando cada componente usa APIs abstratas (pense nelas como padrões comuns para usar essa tecnologia), isso é conhecido como "[arquitetura orientada a serviços](https://en.wikipedia.org/wiki/Service_oriented_architecture)" (SOA) . Este é o mesmo conceito de "peças intercambiáveis" que tornou possível a revolução industrial. Os acoplamentos padronizados são o conceito subjacente à computação em nuvem, tomadas elétricas, USB, Legos, comboios e inúmeros outros produtos e práticas modernas.

Construir sistemas de TI usando partes fracamente acopladas, conectadas por APIs abertas e disponíveis, é a "solução mágica" que permite construit sistemas flexíveis e sustentáveis ​​que atendem às necessidades do utilizador e custam menos com o tempo.


### Contratação modular

Ao combinar o design centrado no utilizador, a agilidade, a propriedade do produto, DevOps e a construção com peças fracamente acopladas, é possível partir um contrato grande e arriscado num punhado de contratos menores. Um contrato deve ser pequeno o suficiente para que a agência não tenha escrúpulos em não dar mais trabalho a um fornecedor que não cumpre, substituindo-o por um novo fornecedor. Nesse caso os restantes fornecedores poderão continuar a trabalhar, e a perda total de velocidade será mínima. Um novo fornecedor não deveria ter dificuldade em substituir o antigo, já que o antigo estava entregando software completo, documentado e testado a cada duas semanas. Outro benefício é que pequenos contratos podem chegar abaixo do limite de aquisição simplificado da administração pública, o que significa que as organizações podem rapidamente escrever convite, publicá-la e conceder um contrato.

Essa abordagem exigirá coordenação e aceitação dos responsáveis pelas aquisições e contratações. Este pessoal costuma estar acostumado com a abordagem tradicional de terceirizar projetos de TI: uma grande aquisição baseada em longos documentos de RFP, solicitando dos fornecedores propostas longas, certificações e qualificações desatualizadas. Geralmente, os fornecedores que usam métodos ágeis e centrados no utilizador não têm ideia do que seja "CMMI" ou "ISO-9000" - tais padrões já não são mais considerados melhores práticas para a criação de sistemas de software flexíveis e económicos. Esta é uma barreira de entrada para muitos dos fornecedores que poderiam ser contratados pelo governo mas que não desejam gastar todos os recursos necessários para se qualificar e escrever uma proposta.

Os processos modernos de desenvolvimento de software são baseados no design centrado no utilizador, desenvolvimento ágil de software, propriedade do produto, DevOps, construção com peças fracamente acopladas e contratação modular. Ao compreender esses conceitos básicos, você está em uma ótima posição para entender como fazer um orçamento para software de forma mais eficaz e para entender o restante deste manual.



## Orçamentar e supervisionar projetos de tecnologia

### Pense sobre o risco de uma nova maneira

Nas últimas décadas, as agências governamentais deixaram de usar funcionários internos, contando com fornecedores externos para construir sua ferramentas de tecnologia digital. As decisões para fazer isso foram baseadas em trocas compensatórias que pareciam opções de menor risco - muitas vezes impulsionadas por capacidade limitada e promessas de ferramentas mais baratas "disponíveis no mercado" oferecidas por contratantes do governo.

No entanto, aprendemos com exemplos de vários projetos que, embora o governo possa facilmente terceirizar o trabalho de criação de novos sistemas digitais, ele não pode terceirizar o risco de falha. Projetos que correm mal refletem-se também nos departamentos do governo, não só em empreiteiros ou fornecedores de software.

O governo é, em última análise, responsável pela sua missão, e por consequência, as entidades governamentais precisam de ter controle e responsabilidade pelos projetos que suportam essa missão. O problema que uma convite a orçamento de TI visa resolver não é um problema técnico; é um problema relacionado ao cumprimento da missão do governo, e a tecnologia é simplesmente um meio para esse fim.

Isso não significa que os departamentos precisem de realizar todo o trabalho internamente; significa que os departamentos precisam de definir expectativas claras sobre os resultados humanos e padrões técnicos relacionados com a segurança de dados, uso, interoperabilidade, monitorização e avaliação.

O conhecimento técnico é acessível e abundante, mas saber como administrar uma agência estatal é uma habilidade rara e valiosa. O governo deve abraçar e assumir a sua responsabilidade e risco de falha, reconhecendo que os fornecedores de tecnologia são contratados apenas para ajudar e devem poder ser facilmente substituíveis se não cumprirem.


#### Lista de verificação

- O projeto tem um proprietário do produto dedicado e autorizado, que é funcionário do departamento - não é um contratado e não é funcionário da agência de TI do estado.
- As partes interessadas reconhecem que a abordagem existente (desenvolvimento em cascata) falha na maioria das vezes e que mudar para o desenvolvimento ágil e aquisição modular é, de fato, significativamente menos arriscado.
- As partes interessadas consideram os fornecedores externos como peças substituíveis para cumprir uma meta, em vez de como os "proprietários" de um projeto ou seu resultado.

#### Questões-chave

- Existem funcionários do governo identificados e treinados (não contratados) que servirão como donos de produtos dedicados e com poderes para definir a direção, priorizar e supervisionar o trabalho da equipa de desenvolvimento?
- Há uma cadeia de apoio para esta nova abordagem dentro do departamento e das suas chefias superiores, TI central, escritórios jurídicos e de compras, bem como o legislativo? Alguma dessas partes interessadas é capaz de bloquear a adoção desta nova abordagem? Em caso afirmativo, qual é o caminho para escalar os problemas, garantindo o alinhamento e evitando que esses bloqueadores internos coloquem o projeto em risco?
- Como o departamento está a assumir a responsabilidade por liderar o projeto e assumir os resultados, em vez de tentar terceirizar o risco para um fornecedor através de um processo de contratação?

