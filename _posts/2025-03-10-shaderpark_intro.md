---
layout: post
title: Introdução ao Shader Park
subtitle: Linguagem GLSL e criação de shaders
comments: true
mathjax: true
author: Nala Quimera 
---

Olá, tudo bem? Nesse post faremos uma introdução a criação de shaders no Shader Park. 

### Mas o que são shaders? 
- Shaders são **pequenos programas que rodam na GPU (placa de vídeo)** que definem o comportamento da superfície dos objetos na tela. Eles são usados para criar efeitos visuais em videogames, animações, arte digital e simulações gráficas;
- Ao contrário do processamento pela CPU, shaders aproveitam o poder da **GPU**;
- Um shader recebe dados de entrada (como posição dos pixels, cor e iluminação) e calcula como cada elemento gráfico será desenhado, permitindo efeitos visuais avançados como **iluminação realista, reflexos, sombras dinâmicas, distorções e até arte generativa;** 
- Os Shaders processam milhões de pixels de forma simultanea, tornando efeitos visuais complexos rápidos e eficientes.

  
Pense em um jogo de videogame. Os Shaders são responsáveis por aplicar efeitos como os reflexo e movimento da água, definindo a qualidade das curvas da imagem.

![image](https://github.com/user-attachments/assets/30e21894-2bd3-4d47-83d0-5be624547c50)

Na imagem a cima do jogo Minecraft podemos reparar nos shaders em seu pleno funcionamento apenas olhando para a água, seu reflexo e nuancias.

Outro exemplo é esse vídeo do jogo "Crysis Beach", com um gráfico impressionante e bastante realista graças ao processamento realiado pelos shaders. 

[Assista ao vídeo](https://www.youtube.com/watch?v=JVujJyUx6HE)

### Exemplos práticos de uso de shaders:
- Jogos: Criam efeitos como explosões, água realista e iluminação dinâmica;
- Arte generativa: Produzem padrões, texturas e animações abstratas;
- Cinema/VFX: Simulam fogo, fumaça, partículas e pós-processamento;
- Ciência e Simulações: Usados para modelar fenômenos físicos e biológicos.

## Shader Park: Uma Biblioteca para Criar Shaders com JavaScript
### O que é Shader Park?
- Shader Park é uma biblioteca de código aberto que permite produzir arte generativa e gráficos interativos usando **JavaScript**, sem a necessidade de escrever código em GLSL (a linguagem tradicional para shaders). Ele facilita a criação de formas, cores e animações diretamente no navegador;
- Arquitetado por Christian Mio Loclair & Tim Rodenbröker com foco em criar shaders e arte generativa de forma mais acessível. Seu diferencial é permitir **usar JavaScript em vez de GLSL**, tornando o processo mais intuitivo.


### Principais características do Shader Park
- **Baseado em JavaScript**: No ShaderPark você escreve shaders sem precisar aprender GLSL;
- **Código mais intuitivo**: A biblioteca abstrai a complexidade dos shaders, permitindo que iniciantes criem gráficos gerativos rapidamente;
- **Interatividade**: Permite que você crie animações dinâmicas e interativas que respondem a inputs do usuário;
- **3D e 2D**: Você pode criar desde formas geométricas básicas até composições tridimensionais complexas.

### Por que usar Shader Park?
- **Fácil de aprender**: Você usa **JavaScript** e evita a complexidade do GLSL;
- **Interativo e dinâmico**: Ideal para arte generativa e visualizações ao vivo;
- **Ótimo para iniciantes**: Sem necessidade de conhecimento avançado em shaders;
- **Criação rápida**: Basta abrir o navegador e começar a experimentar.
  
### Vamos começar? 
1. Acesse o Shader Park pelo link https://shaderpark.com/;
2. Ao rolar a interface para baixo, verá os links de acesso para o discord e o github do próprio Shader Park, para sanar qualquer dúvida que possa ter;
3. Um pouco mais a baixo, o site possui um um vídeo inserido do youtube para "beginners", ou seja, iniciantes. Recomendo fortemente que assista. Segue o Link:
[Shader Park Beginner](https://www.youtube.com/watch?v=QvR4rDSKwvM&list=PLgfxkm9xFocbc6wiO3A8vXalP4K57yUKo)
4. Por último, mais a baixo ainda, o site diz que é possível combinar o Shader Park com outros softwares, como Touchdesginer e P5.js, o que é de grande interesse para nós da pesquisa em música visual com programação para Fulldome.
5. No canto superior direito do site, visualizamos seis possíveis acessos: Explore, Docs, Discord, New, About e Sign In.
   - Explore: Em "explorar" é possível ver obras de outros membros e seus códigos;
   - Docs: Em "documentos" temos acesso a biblioteca em GLSL e JS;
   - Discord: Link de acesso ao Discord;
   - New: Comece a escrever os códigos aqui;
   - About: Um pouco sobre o que é o Shader Park;
   - Sign In: Para criar ou entrar numa conta.





