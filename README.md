Projeto: Cubo Mágico 3D Interativo

Este projeto foi desenvolvido como avaliação prática para a disciplina de Computação Gráfica na UNICAP, sob a orientação do professor Pedro Ximenes. A aplicação consiste em um protótipo tridimensional e totalmente interativo de um Cubo Mágico (Rubik's Cube) executado diretamente no navegador utilizando Three.js e WebGL.

O que o projeto faz
* Cubo Mágico Realista: Renderização completa da estrutura 3x3x3 (27 peças independentes) com frestas visuais entre os blocos (proporção 0.95).
* Controle de Câmera: Integração com OrbitControls, permitindo que o usuário rotacione a visualização, dê zoom e explore o cubo por qualquer ângulo usando o mouse.
* Movimentação de Faces: Interface interativa para girar três faces do cubo: Superior (eixo Y), Frontal (eixo Z) e Direita (eixo X).
* Sistema de Embaralhamento (Shuffle): Função automatizada que executa uma sequência rápida e aleatória de 15 giros consecutivos, travando a interface para evitar bugs na malha.

Organização do Grupo e Divisão de Tarefas
* Gerson Gomes: Ficou responsável pelo setup inicial do ambiente no Three.js (configuração da cena, câmera, iluminação de fundo e renderizador) e pelo desenho lógico da malha de 27 cubos através do laço triplo de repetição. Também estruturou e validou a lógica matemática do pivô (THREE.Group) para os giros iniciais do cubo.
* João da Fonte Queiroz: Desenvolveu a mecânica do Embaralhador (Shuffle). Foi o responsável por criar a lógica de enfileiramento dentro do encerramento das rotações, ganhando eficiência para que os giros rápidos aconteçam um de cada vez sem quebrar as matrizes das peças.
* João Gabriel Diniz Gastão: Responsável por expandir a interatividade do projeto para três dimensões. Mapeou o eixo X, implementou o comportamento e a renderização da Face Direita, e conectou o botão correspondente na interface do usuário.

Uso de ferramentas de IA
* Modelo: Sonnet 4.6
* Aplicação no projeto: O modelo foi utilizado no início do desenvolvimento para gerar a estrutura geométrica base do cubo 3x3x3 e fornecer um norte de como trabalhar com o agrupamento temporário (THREE.Group) limitando-se a duas faces, conforme a instrução dada no seguinte prompt de engenharia: "Atue como um Engenheiro de Software especialista em Three.js. Preciso criar um protótipo focado estritamente nos REQUISITOS de um Cubo Mágico 3D (Rubik's Cube) em um único arquivo index.html. O código deve ser o mais simples, enxuto e otimizado (...) ROTAÇÃO DE APENAS 2 FACES (...) Adicione apenas 2 botões simples na tela."
* Trabalho Humano / Adaptações: A equipe herdou essa estrutura inicial e realizou o refinamento manual. Ajustamos os cálculos de tempo (delta time) para suavizar a animação, corrigimos bugs de arredondamento de ponto flutuante nas coordenadas e expandimos o código por conta própria para criar o algoritmo de embaralhamento e a rotação da terceira face (Face Direita).
