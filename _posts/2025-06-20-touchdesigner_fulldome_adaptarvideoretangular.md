---
layout: post
title: Adaptar um vídeo retangular para o formato fulldome no TouchDesigner
comments: true
mathjax: true
author: Nala Quimera
---

## INTRODUÇÃO - ENTENDENDO O FORMATO FULLOME
### O que é fulldome?
- Um sistema de projeção em cúpula hemisférica.
- O público está no centro ou ao redor do centro visual.
- A imagem final deve estar em formato circular dentro de um frame quadrado (ex: 2048x2048, 4096x4096).
- É necessário um mapeamento específico (fisheye) para que o conteúdo "abrace" o domo de forma correta.

## Método 1 - MÁSCARA CIRCULAR (Solução Simples)
### Quando usar:
- Testes rápidos
- Conteúdo abstrato, não espacializado
- Sem distorção espacial realista

### Passo a passo:
1. Importe o vídeo
- No Touchdesigner, aperte a tecla "Tab" e adicione o node 'Movie File In" (TOP)
![1](https://github.com/user-attachments/assets/3a7eb5ca-7acf-468d-bd0e-ded1bf2641c9)
- Nos parâmetros, adicione seu vídeo em "File"
- ![2](https://github.com/user-attachments/assets/312fb8b1-f594-4b33-af1b-13f764b3fda9)

 
2. Centralize e redimensione
- Aperte "Tab" e adicione o node "Fit" conectado a "Movie File In"
![3](https://github.com/user-attachments/assets/0696b8a3-5cac-4c7d-a14e-cc8d87f86ca7)

- Nos parâmetros, mude a resolução em "Common" para 2048x2048 e em "Fit" mude a escala "Scale" para 2 e 2 
![4](https://github.com/user-attachments/assets/051fa9d0-2b65-4766-ab61-66e6ef878643)
![5](https://github.com/user-attachments/assets/00cccd53-20ec-4e7b-84ba-851990555043)

3. Crie uma máscara circular
- Adicione um "Circle" (TOP) sem conectar (ainda) a nenhum node
- Mude a resolução para Resolution: 2048x2048
- Em "Radius" altere para 0.499 e 0.499
- Mude "Fill Alpha" para 0 e "Background Alpha" para 1  

4. Componha a máscara
- Adicione o node "Over" (TOP) e conecte o node "Circle" em cima e 'Fit" em baixo

5. Resultado
- Adicione o node "Null" (TOP) e veja o resultado


## Método 2 - DISTORÇÃO POLAR (Sem 3D, com deformação real)
### Quando usar:
- Vídeo plano que precisa ser adaptado com distorção espacial hemisférica
- Simulação de deformação radial para domo
- Sem trabalhar com geometria 3D, apenas vídeos 2D (recomendado)

### Passo a passo:
1. Importe o vídeo
- No Touchdesigner, aperte a tecla "Tab" e adicione o node 'Movie File In" (TOP)
- Nos parâmetros, adicione seu vídeo em "File"

2. Centralize e redimensione
- Aperte "Tab" e adicione o node "Fit" conectado a "Movie File In"
- Nos parâmetros, mude a resolução em "Common" para 2048x2048 e em "Fit" mude a escala "Scale" para 2 e 2

3. Converter para circular
- Adicione o node "Pojection" (TOP) conectado ao node "Fit"
- Mude os parâmetros: "Input" - Equirectangular e "Output" - Fish-Eye

4. Resultado
- Adicione o node "Null" (TOP) e veja o resultado


## Método 3 - CÂMERA FISHEYE
### Quando usar:
- Performances em domos reais
- Mapeamento espacial correto

### Passo a passo:
1. Importe o vídeo
- No Touchdesigner, aperte a tecla "Tab" e adicione o node 'Movie File In" (TOP)
- Nos parâmetros, adicione seu vídeo em "File"

2. Centralize e redimensione
- Aperte "Tab" e adicione o node "Fit" conectado a "Movie File In"
- Nos parâmetros, mude a resolução em "Common" para 2048x2048 e em "Fit" mude a escala "Scale" para 2 e 2

3. Câmera com lente olho de peixe
- Adicione o node "Lens Distort" (TOP) conectando a "Fit"
- Nos parâmetros do node, mude: K1 - 1; K2 - 1; K3 - 1
- Ainda nos parâmetros de Lens Distort, altere "Focal Lengths" para 1.1 e 1.1
- Na aba "Layout" de Lens Distort, ponha "Extend Mode" em "Mirror" e "Post Transform" em "New Camera Matrix"

4. Máscara Circular
- Adicione um "Circle" (TOP) sem conectar (ainda) a nenhum node
- Mude a resolução para Resolution: 2048x2048
- Em "Radius" altere para 0.499 e 0.499
- Mude "Fill Alpha" para 0 e "Background Alpha" para 1  

5. Componha a máscara
- Adicione o node "Over" (TOP) e conecte o node "Lens Distort" em cima e "Fit" em baixo

6. Resultado
- Adicione o node "Null" (TOP) e veja o resultado


