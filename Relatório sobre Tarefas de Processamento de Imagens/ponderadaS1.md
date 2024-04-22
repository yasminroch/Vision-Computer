
## Classificação de imagem

O que é:
Em visão computacional, a classificação de imagem vai além do simples modo que a define como pegar uma imagem e classificar o que está presente nela. A classificação de imagem forma a base para outros problemas da visão computacional, sua tarefa é categorizar e atribuir rótulos a grupos de pixels numa imagem, ou seja, é dar poder ao computador de interpretar uma imagem e classificá-la como uma classe, dessa maneira, é possível rotular a partir desse enquadramento de classe, por exemplo, em determinadas imagens de vários animais, o animal x é um gato, o animal y é uma zebra enquanto o animal z é um cavalo.

Ao estar na etapa de classificação de imagens, facilmente se deparamos com alguns métodos comuns que são utilizados para classificar imagens por meio da extração de dados de treinamento. Tais métodos são “máxima verossimilhança(maximum likelihood estimation)” e “minimum distance(distância mínima)” e “spectral angle mapper(mapeador de ângulo espectral)”. Maximum likelihood usa as estatísticas dos dados em que o desvio padrão e valores médios de cada índice e espectro da imagem são analisados, após isso, é feita a distribuição normal para os pixels presentes a fim de separar classes por cada pixel e assim maximizar a probabilidade. Já o Minimum Distance baseia-se na distância entre o pixel e a média(centro) de uma classe, ou seja, o pixel é atribuído à classe em que o centro é mais próximo dele, sendo calculado através da distância euclidiana. Por fim, o Spectral Angle Mapper compara a semelhança entre os espectros calculando o ângulo cosseno entre os vetores de dados no espaço espectral, se há um ângulo pequeno entre os vetores, por exemplo, isso pode indicar alta semelhança.

A classificação de imagem pode ser definida em dois tipos, técnica supervisionada e não supervisionada.

Técnica não supervisionada:
É um método sem intervenção humana, ou seja, seria um método automatizado que não usa os dados de treinamento, aqui podem ser aplicados algoritmos de reinforcement learning para fazer o agrupamento de imagens e analisar dados que não são rotulados a fim de descobrir padrões.

Técnica supervisionada:
Faz uso de amostras já disponíveis e classificadas para treinar, seria treinar o que foi classificado para classificar novamente com dados novos e desconhecidos, semelhante a exploration e exploitation. Aqui o que é escolhido são amostras de treinamento dentro da imagem e essas imagens são classificadas em categorias pré-estabelecidas.


Como funciona:
A classificação de imagens funciona da seguinte forma, o computador considera a imagem como uma matriz de matrizes e o tamanho depende da resolução, visto que analisa a imagem no formato de pixels. Esses dados são analisados estatisticamente por algoritmos, o Spectral Angle Mapper citado aqui anteriormente é uma forma que pode ser adotada para auxiliar nessa análise, além disso, o YOLO é um popular algoritmo para detectar classes. Portanto, a classificação é executada a partir de agrupamentos de pixels em categorias ou “classes”, isso é feito automaticamente, para deixar mais compreensível, isso pode ser dividido em determinada forma:

- Um modelo de Deep Learning retorna classes com a probabilidade de detecção;
- Os algoritmos adotados separam a imagem em uma série de características consideravelmente importantes, ou seja, os atributos significativos como forma, textura, borda, cor, entre outros(isso é o que auxílio ao determinar o que a imagem representa e em qual classe possivelmente se encaixa).

A etapa de extração das características é uma das etapas mais importantes na classificação de uma imagem, visto que as etapas posteriores a essa são totalmente dependentes do que foi obtido na extração.


Mas afinal, o que a visão computacional, especificamente a classificação de imagens resolve na vida real?
Na área da medicina, por exemplo, pode ser utilizado em procedimentos envolvendo raio-X, tomografia e ressonância magnética. O trabalho intitulado “Classificação de imagens médicas em modalidades usando visão computacional”, trabalha com a classificação de imagem para extrair legendas associadas a imagens, isso porque ocorre casos em que a legenda não está presente ao decorrer das capturas ou não é uma legenda correta. Desse modo, qualquer problema relacionado a essas legendas impacta negativamente na detecção efetuada pelo profissional que busca por informações. Tal trabalho tem por finalidade buscar classificar automaticamente determinada imagem visualmente comparando o melhor descritor levando em consideração sua eficiência ao classificar diferentes imagens submetendo a vários algoritmos de classificação. Essa classificação automática de imagens médicas para gerar ou corrigir legendas ajuda a garantir que as imagens estejam corretamente anotadas com informações relevantes e auxilie no aumento da precisão diagnóstica

Outras aplicações:
É possível utilizar a classificação de imagem para classificar e fazer triagem de produtos agrícolas, nesse caso, seria uma automatização da separação de frutas e vegetais com base em características específicas, como cores, maturidade, tamanho, entre outros, para melhorar a eficiência da colheita e do processamento. O trabalho “Visão Computacional Aplicado na Agroindústria”, mostra um sistema de identificação de cores em relação a classificação de tomates levando em consideração sua maturidade, este trabalho foi desenvolvido com a biblioteca OpenCV no processamento e tal adoção evita erros e inconsistências causados pela classificação manual. As etapas para fazer essa classificação consiste em:
- Definição de classes: no contexto dos tomates, as classes são definidas por estágios de maturidade, como verde (imaturo), amarelo (amadurecendo), vermelho (maduro).
- Coleta e rotulação de dados: várias imagens de tomates em diferentes estágios é coletada e cada imagem é rotulada com sua categoria correspondente(esse conjunto de dados rotulados servirá como base para treinar o modelo de classificação).
- Pré-processamento de Dados: As imagens coletadas são submetidas a processos de normalização de cor e redução de ruído para melhorar a uniformidade e a qualidade das imagens, facilitando a extração de características significativas.
- Extração de Características: Nesta etapa, características relevantes que ajudam a diferenciar entre as classes são extraídas de cada imagem. No caso dos tomates, características como a intensidade de cor e distribuição de cor são particularmente úteis para determinar a maturidade(aqui há implementação de histogramas). 



Quais produtos comerciais estão relacionados à classificação?
- Google Cloud Vision AI:
Faz a detecção e análise de objetos classificando estes objetos em imagens e vídeos, como pessoas, animais, carros… além disso, é capaz de reconhecer e analisar rostos, identificando emoções, idade e gênero. A classificação é feita a partir do agrupamento de imagens de forma automática com base em seu conteúdo.

- Amazon Rekognition:
É um serviço semelhante ao Google Cloud Vision AI, o Amazon Rekognition detecta e classifica objetos em imagens e vídeos, ele pode por exemplo, reconhecer alguma atividade presente no vídeo analisado como correr ou andar, extraindo informações como movimentos, pessoas, locais e objetos inanimados.

- Tesla Autopilot:
Faz o reconhecimento e classifica objetos próximos ao veículo, como carros, pedestres, sinais do semáforo, além disso, faz o rastreamento, monitorando o movimento e a trajetória do que está entorno do veículo que influenciam na tomada de decisões de direção, acelerar, frear etc, assim como predizer se um pedestre é um potencial a atravessar a rua.


Os produtos citados aqui se deparam com desafios como variabilidade do que se é analisado, por exemplo, levando em consideração características de aparência que podem mudar conforme a iluminação e ângulo, também similaridades que podem ser apresentadas e dificultar o processo de distinção e o contexto, algo essencial para obter uma identificação precisa, visto que um objeto pode ter diversas interpretações dependendo do cenário o qual se encontra. Esses três produtos empregam técnicas como redes neurais convolucionais(CNNs) que aprendem a extrair características como cor, formato, movimentos, textura, contexto e metadado como data ou local da captura.

Quais os segmentos de mercado dos produtos comerciais relacionados?
- Google Cloud Vision AI é um serviço disponibilizado pelo Google Cloud Platform, seu segmento é desenvolvimento de software que se estende atendendo vários tipos de mercado com aplicações diferentes para atender necessidades específicas dos clientes;
- Amazon Rekognition assim como Google Cloud Vision AI também se encaixa no segmento enterprise de desenvolvimento de software como computação em nuvem, atendendo vários mercados;
- Tesla Autopilot faz parte do segmento da indústria automobilística, com sistemas avançados de assistência ao motorista(ADAS) com carros autônomos.

Teste com o produto Amazon Rekognition e resultados obtidos:

Primeiramente, foi acessado o serviço Amazon Rekognition no console AWS, o serviço é facilmente manipulável, sendo que na primeira tela após iniciar este serviço já é possível fazer o envio de uma imagem a sua escolha para ser analisada. Em questões não só éticas, mas de características físicas de pessoas reais, a visão computacional pode ter dificuldades de classificar precisamente, ao usar este serviço, é possível verificar que mesmo uma tecnologia de um dos serviços mais conhecidos pode estar vulnerável a vieses. A seguir será listada cada etapa deste processo:

1. Acesso ao console da AWS, especificamente ao serviço Amazon Rekognition, clique na opção iniciar serviço e ao ser direcionado a tela com uma imagem padrão do serviço, clique na opção de fazer upload de imagem, caso queira analisar uma foto específica.
2. No teste realizado neste trabalho, foi utilizado uma foto que mostra sete pessoas distintas, estas são de um grupo musical chamado BTS. O objetivo de escolher determinada imagem é verificar a precisão do serviço, principalmente em relação a problemas que esse tipo de tecnologia apresenta no momento de analisar pessoas e suas características que podem ser estereotipadas e influenciar na precisão do modelo, assim como o estudo da Universidade de Princeton apresenta.
3. Ao fazer upload da imagem, ela é automaticamente analisada, é possível verificar máscaras sobrepostas que identifica cada indivíduo, além disso, ao lado da imagem é possível verificar rótulos, ou seja, classificações diferentes para cada pessoa presente na imagem:
![BTS](https://imgur.com/1QCSF1l)
4. Além de verificar os rótulos que são gerados automaticamente após a análise da imagem, também é possível adicionar outros rótulos. Na base de pesquisa em “Pesquisar todos os rótulos” é possível escrever qualquer rótulo, este claramente precisa estar disponível na base. Nesta análise foi adicionado o rótulo “Clothing” que mostra claramente que todos estão vestidos.

Resultados:
Ao passar o cursor por cada pessoa presente na imagem, é possível visualizar os rótulos específicos atribuídos para cada um, cada um tem rótulos diferentes. Entretanto, houve alguns erros e as pessoas que estão mais próximas do centro foram capturadas com mais informações. Todos nas imagens são adultos, homens e estão vestindo roupas sociais, abaixo estão os resultados obtidos de cada um, numerando da esquerda para a direita:

Pessoa 1: foi identificado como um adolescente, porém, é um adulto que nesta foto apresenta 28 anos, aqui a vestimenta específica não foi identificada(se é terno, casaco, etc);
Pessoa 2: foi identificado como gênero feminino, sendo que este se apresenta como gênero masculino, o modelo apenas acertou a característica de estar usando terno;
Pessoa 3: foi mais um identificado como adolescente, sendo que na verdade é um adulto, aqui o modelo também acertou a característica de usar terno;
Pessoa 4: é a pessoa mais próxima do centro da imagem e também é a pessoa que o modelo acertou, caracterizando como homem adulto e estar vestido de terno;
Pessoa 5: foi mais um caracterizado como adolescente, o modelo caracterizou sua vestimenta utilizando casaco;
Pessoa 6: caracterizada apenas como pessoa;
Pessoa 7: caracterizado apenas como homem.

Portanto, claramente é visto que, levando em consideração os rótulos atribuídos e identificados, o modelo acertou totalmente apenas a pessoa 4. Lembrando que este modelo fez a detecção dos rostos, características faciais e detecção de emoções e as identificações dependem também da resolução da imagem, quanto melhor for a resolução e qualidade, melhor serão os resultados.


## Detecção de objetos
A detecção de objetos é uma tarefa que já foi mencionada em conjunto com a classificação, neste tópico, será abordado com mais especificidade.

O que é:
A detecção de objetos é a capacidade de fazer com que computadores identifiquem e localizem objetos presentes em imagens e vídeos. O teste realizado com o serviço Amazon Rekognition é um exemplo de classificação, mas também de detecção de objetos, visto que analisa imagens e automaticamente pode reconhecer carros, pessoas, animais e outros objetos relevantes. Além de classificar, para determinar a localização dos objetos verifica o que está ao redor desse objeto com uma caixa delimitadora(bouding box).

Para definir e ter conhecimento do seu funcionamento, foi utilizado como base o curso “Object detection with Python”.


Diferença entre classificação e detecção de objetos:
- O objetivo da classificação de objetos é atribuir classes ao objeto, enquanto a detecção visa identificar e localizar objetos de uma ou mais classes;
- O output da classificação é a própria classe, já da detecção, é a classe e a localização de cada objeto;
- Ambos possuem aplicações distintas, a classificação é utilizada para reconhecimento de imagens, análise e principalmente na categorização e filtragem do conteúdo. Por outro lado, a detecção de objetos faz o monitoramento e a complexidade é maior, pois ao contrário da classificação que lida com tarefas únicas, a detecção lida com múltiplas tarefas(localização e classificação);
- Classificação não requer características espaciais tão detalhadas, já a detecção requer essas informações, como posição e tamanho dos objetos;
- Há métodos empregados para cada, para classificação pode ser CNNs e para a detecção de objetos pode-se empregar YOLO ou R-CNN que combina CNNs com métodos de localização.

Como funciona:
Para detectar objetos, deve-se observar as seguintes etapas do seu funcionamento:
1. Pré-processamento: A imagem ou vídeo é preparada para ser analisada levando em consideração seu formato ou redimensionamento para que seja ajustado seu tamanho para uma resolução padrão; A imagem tem sua iluminação corrigida para melhor contraste; Há remoção de ruídos a fim de eliminar qualquer interferência; Apontar características relevantes como bordas e cores.
2. Extração de recursos: nessa etapa finalmente é extraída características relevantes da imagem, como identificar cores presentes, a textura dos objetos, reconhecimento de formas geométricas e das bordas e contornos.
3. Treinamento: aqui o modelo de machine learning é treinado usando todos os conjuntos de dados que foram rotulados, nessa etapa é necessário adotar algoritmos específicos como Redes Neurais Convolucionais(CNNs), K-Nearest Neighbors(KNN) ou Máquinas de Vetores(SVMs).
4. Identificação de objetos com imagens novas: após treinado, o modelo é utilizado para detectar objetos em imagens novas a partir de comparações. Desse modo, o modelo gera a probabilidade para cada classe de objeto, indicando o que pode ser.


Mas o que esse tipo de problema resolve na vida real?
A detecção de objetos é extremamente útil no controle de qualidade, ou seja, implementando essa técnica é possível ter um gerenciamento de alta qualidade. Aqui o deep learning atua com base na detecção de objetos em tempo real para oferecer resultados na automação industrial, podendo identificar peças defeituosas nas linhas de montagem ou diretamente no gerenciamento de estoque por meio do reconhecimento automático de produtos presentes nos armazéns. Em comparação com o processo de inspeção manual, a detecção de objetos se mostra muito mais promissora, visto que garante maior precisão, velocidade e também se apresenta como mais confiável. Por exemplo, na fabricação de aço, assim como no trabalho “Deep Learning para inspeção visual em peças fundidas”, é citado o uso da rede YOLO para detecção em tempo real de possíveis defeitos superficiais em tiras de aço

Outras aplicações:
Detecção de objetos em operações metroferroviárias:
O trabalho “Um Sistema de Visão Computacional para Otimização e Segurança Em Sistemas Sobre Trilhos” aplica a detecção de objetos com técnicas de segmentação para identificar objetos estranhos, como malas, objetos suspeitos e perigosos. Ao ser detectados, são gerados alertas para quem é responsável pelas inspeções e segurança do local para conferir qualquer incidente, perda ou risco a segurança. Este trabalho também aborda os principais desafios, como detecção em tempo real, precisão e confiabilidade, variações na iluminação, ambientes complexos ao redor dos trilhos e oclusões e distorções(obstáculos). Essa implementação funcionaria da seguinte forma:
1. Instalação de câmeras: essenciais para capturar imagens em pontos estratégicos;
2. Pré-processamento: as imagens já capturadas teria sua qualidade e visibilidade melhoradas com ajuste de iluminação, contraste e técnicas para reduzir ruídos;
3. Segmentação de objetos: o sistema identifica e isola objetos de forma individual na imagem, aqui utiliza-se máscaras para cada objeto detectado e pode-se aplicar métodos como Mask R-CNN.
4. Análise de contexto e classificação: o contexto em que os objetos são detectados é analisado, considerando localização, tamanho do objeto, etc. Aqui as malas esquecidas citada como exemplo, seriam classificadas como objeto suspeito. Cada objeto detectado seria então classificado, isto é, se o que foi detectado é realmente uma mala ou qualquer outro tipo de objeto, modelos de deep learning treinados seriam usados nessa etapa;
Sistema de alerta: quando o objeto é finalmente identificado, o sistema gera automaticamente um alerta envolvendo a localização exata, tipo do objeto ou até mesmo imagem, aqui depende das informações úteis a serem transmitidas quando o alarme é acionado.


Produtos comerciais relacionados com detecção de imagem:
- VIA Mobile360 AI Forklift Safety Kit: é uma solução oferecida pela Via Technologies que auxilia na prevenção de acidentes em estoques da área logística a fim de reduzir perdas, perigo à segurança e danos na cadeia de suprimentos. Esse produto é em tempo real e consegue identificar possíveis ameaças aos profissionais que trabalham nesse ambiente e aproximação/movimentos perigosos envolvendo o maquinário.
- Clarifai: é uma plataforma de IA que permite fazer análises envolvendo reconhecimento de marcas, produtos e categorias. . A partir do reconhecimento feito, o Clarifai extrai informações do contexto da imagem e este produto é voltado para quem trabalha com marketing e vendas
- Plantix: é um aplicativo que identifica pragas e doenças em plantações e atua como um “laboratório” de diagnóstico de plantas, a detecção é feita por meio de padrões visuais como manchas, deformações, descoloração, essas são características que indicam pragas e doenças. Sendo assim, é possível segmentar diferentes partes da planta, como folhas e caule.

Quais os segmentos de mercado dos produtos comerciais relacionados? 
- VIA Mobile360 AI Forklift Safety Kit: Logístico;
- Clarifai: pode-se dizer que se encaixa em desenvolvimento de software, visto que é aplicada no mercado geral, com foco no varejo, marketing e mídia, desenvolvimento de produtos, etc;
- Plantix: agricultura.

Teste com Plantix e resultados obtidos:
O aplicativo Plantix é gratuito, ao fazer a instalação, o usuário é direcionado para telas que podem ser puladas, o qual apenas pergunta por informações como culturas de interesse ou o que cultiva. Na tela “home”, ao deslizar para baixo, há a opção de tirar ou enviar foto a fim de detectar o estado da plantação



O teste efetuado foi com uma planta ornamental chamada Espada de São Jorge e com uma planta aleatória que apresenta um tipo de praga. O resultado obtido com a planta ornamental foi que, o aplicativo detectou que por ser uma planta desse tipo, não seria possível prosseguir, ou seja, ao detectar que é uma planta ornamental, nenhum relatório é gerado.


Já ao fazer o upload da planta aleatória que apresenta pragas e faz parte de uma cultura, o aplicativo detectou que o causador da praga é o inseto Cochonilha-pinta-vermelha e sugeriu produtos para combater esse tipo de praga, recomendando o inseticida Quinalphos 25.0 EC.

Portanto, é possível observar que esse tipo de detecção suporta apenas plantações que fazem parte do chamado “culturas”, sendo que não é possível fazer o upload de qualquer planta para obter diagnóstico, como foi o caso da planta ornamental. 






