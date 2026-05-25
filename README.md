Modelo Utilizado: sonnet 4.6
* Parte do projeto: Geração da estrutura base do cubo 3x3x3 e implementação da lógica de agrupamento temporário (THREE.Group) restrita a duas faces.  
Prompt Utilizado: 
Atue como um Engenheiro de Software especialista em Three.js. Preciso criar um protótipo focado estritamente nos REQUISITOS de um Cubo Mágico 3D (Rubik's Cube) em um único arquivo `index.html`. O código deve ser o mais simples, enxuto e otimizado

O projeto deve seguir estes requisitos:

1. CONFIGURAÇÃO DA CENA (MÍNIMA):
- Inclua o Three.js e o OrbitControls via CDN (versão estável, ex: https://cdn.jsdelivr.net/npm/three@0.165.0/build/three.min.js).
- Configure Scene, PerspectiveCamera (posicionada de frente/diagonal) e WebGLRenderer com fundo escuro.
- Ative o OrbitControls para permitir rotacionar a câmera com o mouse.

2. CONSTRUÇÃO DO CUBO (3x3x3):
- Gere o cubo com 27 cubinhos individuais (THREE.Mesh) usando um laço triplo simples (X, Y, Z variando de -1 a 1).
- Use THREE.BoxGeometry(0.95, 0.95, 0.95) — o tamanho levemente menor cria um espaçamento (gap) natural que dispensa outlines complexos.
- Use materiais básicos (THREE.MeshBasicMaterial) com as cores padrão nas faces externas (Frente: Vermelho, Atrás: Laranja, Topo: Branco, Base: Amarelo, Direita: Verde, Esquerda: Azul) e as faces internas pretas.

3. ROTAÇÃO DE APENAS 2 FACES:
- Crie funções separadas e simples para girar apenas a Face Superior (Up) e a Face Frontal (Front).
- A lógica deve usar um THREE.Group temporário:
  a. Identifique os cubinhos da face por sua posição (ex: se for a face superior, filtre os cubinhos onde `position.y > 0.5`).
  b. Adicione esses cubinhos a um `THREE.Group` temporário.
  c. Anime a rotação desse grupo em 90 graus (PI / 2 radianos) de forma visível no loop de animação.
  d. Ao terminar a animação, atualize a matriz de cada cubinho com `.updateMatrixWorld()`, remova-os do grupo, devolva-os para a `scene` e limpe o grupo.

4. INTERFACE:
- Adicione apenas 2 botões simples na tela via HTML/CSS: "Girar Face Superior" e "Girar Face Frontal".

Gere um código direto, sem funções extras, apenas o pedido priorizando a clareza e comentários explicando o passo a passo de forma funcional e humana do ciclo de vida do THREE.Group temporário.
Ajustes Humanos: Ajustamos o tempo da animação para que o giro não fosse rápido demais, facilitando a visualização dos cubos entrando e saindo do escopo do grupo.

Ajustes Humanos: Ajustamos o tempo da animação para que o giro não fosse rápido demais, facilitando a visualização dos cubos entrando e saindo do escopo do grupo, alem de algumas funcoes extras.
