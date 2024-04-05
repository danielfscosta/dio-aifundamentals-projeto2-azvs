# Desafio de Projeto 2 - Reconhecimento Facial e transformação de imagens em Dados no Azure ML

O processo de reconhecimento ou extração de texto em imagens é conhecido como *Optical Character Recognition* ou OCR. Técnicas de OCR baseadas em aprendizado de máquina e compostas por vários modelos avançados, como a utilizada neste projeto, potencializam essa capacidade, permitindo que digitalizações de textos manuscritos, documentos impressos, imagens de pôsteres, fotos de placas de ruas e outras fontes sejam intepretadas e suportadas em inúmeros idiomas globais.

Os benefícios associados ao uso desta tecnologia são diversos e estendem-se desde a facilitação do acesso à versão digital do texto de documentos digitalizados, eliminação ou redução significativa da necessidade de entrada manual de dados, possibilidade de integração com aplicações de processamento inteligente de documentos (IDP) para extração de informações úteis, tradução em tempo real de textos em imagens que estejam em idiomas desconhecidos, até promover a acessibilidade e inclusão de pessoas com deficiência visual.

Este desafio de projeto foi proposto no *Bootcamp AI Fundamentals da DIO* com objetivo de explorar as capacidades de reconhecimento de texto em imagens do Azure Vision Studio. Neste laboratório em específico utilizou-se unicamente a interface do portal do Vision Studio para a análise das imagens e obtenção dos resultados, não sendo escritos códigos para integração em aplicações. Este projeto utiliza materiais disponibilizados pelo Microsoft Learn neste [link](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/05-ocr.html), além de imagens obtidas no site [Pixabay](https://pixabay.com) sob a licença Creative Commons Zero (CC0).

## Passo-a-Passo

### Criação de um recurso *Azure AI services*

Os *Azure AI services* são recursos que objetivam ajudar desenvolvedores e organizações na criação rápida de aplicações inteligentes, responsivas, prontas para o mercado, que acompanham o que existe de mais avançado em tecnologias relacionadas, disponibilizando modelos e APIs pré-criadas e configuráveis.

Neste projeto será utilizado o serviço *Vision*, que embora não seja explorado aqui em sua total extensão com o uso das APIs e integração com aplicações reais, permite o acesso de desenvolvedores a algoritmos avançados para o processamento de imagens.

1. Para criação deste recurso é possível selecionar ***+ Create a resource*** na página inicial do [***Azure portal***](https://portal.azure.com). Na tela ***Create a resource***, procurar por *Azure AI services* e selecionar ***Create***.

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/assets/69484807/90b8b86c-5427-4d82-a10f-3314b99695e3)

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/assets/69484807/15cd87c8-bdc1-439d-89a4-70ea18cd18b6)

2. Na página ***Create Azure AI services***, realizar as configurações conforme sugerido abaixo, selecionar ***Review + Create*** e então, após revisar as configirações na próxima página, selecionar ***Create***. Esperar que os recursos sejam completamente provisionados.

- ***Subscription***: Escolher a assinatura a ser utilizada na criação do recurso;
- ***Resource Group***: Grupo de recursos onde será alocado. Caso não exista um grupo de recursos definido, um novo poderá ser criado neste passo através do link *Create New*;
- ***Region***: Selecionar a região em que serão provisionados os recursos, atentando-se para a diferença de precificação dos recursos em cada região;
- ***Name***: Escolher um nome único para o recurso;
- ***Princing tier***: Standard S0;
- ***By checking this box I acknowledge that I have read and understood all the terms below***: Selecionar.

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/assets/69484807/01022fdf-c2c9-45cf-be1f-16a550cb3258)

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/assets/69484807/f6ff4685-5cf1-43f3-a566-e28de345fea8)

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/assets/69484807/c0e8fa04-39c7-4f4d-bc01-362ab2e46d05)

### Conexão do *Azure AI service* criado ao *Vision Studio*

1. Acessar a página do ***Vision Studio*** à partir do portal ou através deste [link](https://portal.vision.cognitive.azure.com) e efetuar a devida autenticação.

2. Na página inicial do *Vision Studio*, selecionar ***View all resources***, na seção ***Getting started with vision***.

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/assets/69484807/1f656026-268d-44ed-b744-9cf7f2482ad1)

3. Na página ***Select a resource to work with***, selecionar da lista o recurso criado anteriormente, selecionar ***Select as default resource*** e sair dessa página através do ***X*** na porção superior direita da tela.

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/assets/69484807/2dd7badb-8c34-4f86-afbb-c4464cbb3f64)

### Extração de texto em imagens no Vision Studio

1. Na página inicial do ***Vision Studio***, selecionar ***Optical character recognition*** e em seguida no bloco intitulado ***Extract text from images***.

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/assets/69484807/13f1d56d-9ad5-4ae0-8834-5b6809a4b5e3)

2. Na página ***Extract text from images***, reconheça a política de uso do recurso lendo-a e selecionando a *checkbox*.

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/assets/69484807/5d79bd2c-4d31-4215-8f3d-bea15b96b1aa)

3. Separar uma imagem que possua textos ou caracteres a serem extraídos pelo serviço e então adicioná-la selecionando ***Browse for a file*** ou escolher ***Take a photo*** para que seja possível tirar uma foto. É possível utilizar as amostras de imagens disponibilizadas na página, caso o utilizador não deseje buscar por imagens externas.

4. Após carregada e processada a imagem, serão apresentados os resultados do texto extraído. Na guia ***Detected attributes***, o texto encontrado fica organizado em uma estrutura hierárquica de regiões, linhas e palavras. Na guia ao lado é possível visualizar o resultado estruturado em formato *JSON*, que possui maior grau de detalhamento ao apresentar parâmetros como a localização do polígono que envolve determinada porção do texto e o grau de confiança na previsão desta porção. Na imagem à esquerda, os polígonos são demonstrados visualmente, envolvendo as referidas porções de texto.

## Resultados obtidos

Foram realizados testes com sete imagens obtidas no site [Pixabay](https://pixabay.com) sob a licença Creative Commons Zero (CC0). As imagens originais utilizadas podem ser encontradas no diretório [inputs](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/tree/main/inputs) e os resultados em formato *.json* podem ser acessados no diretório [output](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/tree/main/output).

Seguem os links para os arquivos utilizados e obtidos, além de capturas de tela dos resultados mostrados após o processamento de cada imagem:

1.
    * Imagem: [coffee-4014708_1920.jpg](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/blob/main/inputs/coffee-4014708_1920.jpg)
    
    * Resultados:
      
        * JSON: [coffee-4014708_1920.json](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/blob/main/output/coffee-4014708_1920.json)
          
        * ![image](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/assets/69484807/16344949-f0d9-47f7-be86-eff410281a44)

2.
    * Imagem: [mug-2667959_1920.jpg](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/blob/main/inputs/mug-2667959_1920.jpg)
  
    * Resultados:
      
        * JSON: [mug-2667959_1920.json](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/blob/main/output/mug-2667959_1920.json)
          
        * ![image](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/assets/69484807/0ba78f84-9450-4c27-af9a-7a94e5eb4fa9)

3. 
    * Imagem: [terms-7010195_1920.jpg](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/blob/main/inputs/terms-7010195_1920.jpg)
  
    * Resultados:
      
        * JSON: [terms-7010195_1920.json](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/blob/main/output/terms-7010195_1920.json)
          
        * ![image](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/assets/69484807/eb71a8e8-3f08-4296-b050-ee14c675da62)


4. 
    * Imagem: [terms-7010195_1920.jpg](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/blob/main/inputs/terms-7010195_1920.jpg)
      
    * Resultados:
      
        * JSON: [terms-7010195_1920.json](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/blob/main/output/terms-7010195_1920.json)
          
        * ![image](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/assets/69484807/88365c8f-70f8-4cf3-8808-b140431773c0)


5. 
    * Imagem: [niagara-992735_1280.jpg](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/blob/main/inputs/niagara-992735_1280.jpg)
  
    * Resultados:
      
        * JSON: [niagara-992735_1280.json](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/blob/main/output/niagara-992735_1280.json)
     
        * ![image](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/assets/69484807/1a325889-a17b-4ef1-af98-4cd0842350d2)

6. 
    * Imagem: [letter-1825055_1280.jpg](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/blob/main/inputs/letter-1825055_1280.jpg)
  
    * Resultados:
      
        * JSON: [letter-1825055_1280.json](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/blob/main/output/letter-1825055_1280.json)
          
        * ![image](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/assets/69484807/9405f822-f08d-4ad5-ade7-723e83598b19)


7. 
    * Imagem: [to-do-2607082_1920.jpg](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/blob/main/inputs/to-do-2607082_1920.jpg)
  
    * Resultados:
  
        * JSON: [to-do-2607082_1920.json](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/blob/main/output/to-do-2607082_1920.json)
     
        * ![image](https://github.com/danielfscosta/dio-aifundamentals-projeto2-azvs/assets/69484807/ae83a473-8e98-49aa-ae81-71520a8fd07d)
