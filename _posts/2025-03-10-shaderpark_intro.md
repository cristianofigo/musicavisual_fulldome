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
- Um shader recebe dados de entrada (como posição dos pixels, cor e iluminação) e calcula como cada elemento gráfico será desenhado, permitindo efeitos visuais avançados como **iluminação realista, reflexos, sombras dinâmicas, distorções e até arte generativa.** 
- Os Shaders processam milhões de pixels de forma simultanea, tornando efeitos visuais complexos rápidos e eficientes.

  
Pense em um jogo de videogame. Os Shaders são responsáveis por aplicar efeitos como os reflexo e movimento da água, definindo a qualidade das curvas da imagem.

![image](https://github.com/user-attachments/assets/30e21894-2bd3-4d47-83d0-5be624547c50)

Na imagem a cima do jogo Minecraft podemos reparar nos shaders em seu pleno funcionamento apenas olhando para a água, seu reflexo e nuancias.

Outro exemplo é esse vídeo do jogo "Crysis Beach", com um gráfico impressionante e bastante realista graças aos shaders. 
https://www.youtube.com/watch?v=JVujJyUx6HE

<iframe width="560" height="315" src="https://www.youtube.com/watch?v=JVujJyUx6HE" frameborder="0" allowfullscreen></iframe>






