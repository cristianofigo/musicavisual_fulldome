---
layout: post
title: Blender e TouchDesigner na Música Visual
subtitle: Explorando as Possibilidades da Integração
comments: true
mathjax: true
author: Nala Quimera
---

Olá! Sabia que é possível combinar o Blender e o TouchDesigner? E que essa combinação abre possibilidades incríveis para a criação de experiências visuais interativas e dinâmicas? 

Ao unir as capacidades de **modelagem e animação 3D do Blender** com o poder de **processamento em tempo real do TouchDesigner**, é possível construir performances audiovisuais ricas, instalações interativas e experimentações generativas. 

Esse fluxo de trabalho é especialmente relevante para artistas visuais, VJs e desenvolvedores criativos interessados em explorações visuais dinâmicas.

## Usos comuns:
A interação entre Blender e TouchDesigner é muito flexível e permite diversas aplicações:

- **Performances Audiovisuais:** Uso de objetos 3D e shaders dinâmicos que respondem a áudio e controle ao vivo.
- **Instalações Interativas:** Projetos sensíveis a movimento, sensores de profundidade (Kinect/Lidar) e inputs de usuários.
- **Realidade Virtual e Fulldome:** Utilização de projeções 360º e renderização para ambientes imersivos.
- **Videomapping:** Projeção mapeada combinando geometrias criadas no Blender e manipuladas em tempo real no TouchDesigner.
  

## Fluxos de Trabalho e Integração:
### Modelagem e Animação no Blender
O Blender é uma ferramenta essencial na produção de elementos 3D, oferecendo:
- **Modelagem e texturização:** Desenvolvimento de objetos detalhados para aplicações interativas.
- **Animação baseada em física:** Simulação de partículas, fluidos e outras dinâmicas para efeitos realistas.
- **Geometry Nodes:** Criação procedural de formas complexas adaptáveis ao controle interativo.

### Processamento em Tempo Real no TouchDesigner
Já o TouchDesigner permite a manipulação interativa de visuais em tempo real por meio de:
- **Importação de modelos 3D:** Utilização de formatos como *FBX* e *Alembic* para visualização dinâmica.
- **Sincronização com áudio:** Manipulação de geometrias e efeitos baseados em frequências sonoras.
- **Shaders GLSL e PBR:** Renderização em tempo real para criação de efeitos visuais complexos.
- **Nós CHOPs e TOPs:** Controle avançado de parâmetros visuais e processamento de imagens e vídeos.

## Integração Entre os Softwares
A comunicação entre Blender e TouchDesigner ocorre de diversas formas:
1. **Exportação de malhas e animações** para controle em tempo real.
3. **Uso de Spout/Syphon** para transmissão de vídeos processados dinamicamente.
4. **Troca de dados via OSC/MIDI**, permitindo controle interativo de parâmetros visuais.
5. **Uso de Python API**, possibilitando a automação e personalização da interação entre os softwares.
6. **Uso de instâncias de geometrias**, otimizando a performance na renderização em tempo real.
7. **Comunicação via UDP/TCP/IP** para integração com outras plataformas e softwares externos.

## Fluxo Básico de Integração
Para demonstrar a integração prática entre Blender e TouchDesigner, siga os passos abaixo:
- Baixe um modelo 3D
- Acesse este link (https://sketchfab.com/) e baixe um modelo 3D no formato **.obj.**
- Alternativamente, crie um modelo simples no Blender (como um cubo deformado) e **exporte** como **.obj.**
    - Vá até File > Export > Wavefront (.obj).
    - Na janela de exportação, ative as seguintes configurações:
    - Scale: Defina um fator de escala adequado (1.0 se o modelo estiver em metros).
    - Apply Modifiers: Habilite para garantir que todas as transformações sejam aplicadas.
    - Include Normals: Certifique-se de que as normais estão ativadas para preservar a iluminação.
    - Triangulate Faces: Se necessário, ative para evitar problemas de topologia.
    - Export Selected Only: Ative se quiser exportar apenas o objeto selecionado.
    - Clique em Export OBJ.

### Importar o modelo no TouchDesigner:
- Abra o TouchDesigner e crie um operador **Geometry (Geo)**.
- No painel de parâmetros, clique em **"File"** e selecione o arquivo **.obj** exportado.
- Conecte um **Phong Material** ao **Geo** e um **Light** para iluminação básica.

### Configuração do Material no TouchDesigner:
- Crie um operador **Phong MAT**.
- No painel de parâmetros do Phong MAT, ajuste as seguintes opções:
      - Base Color: Defina a cor base do material.
      - Specular: Ajuste para controlar o brilho especular.
      - Roughness: Modifique para alterar a dispersão da luz no material.
      - Transparency: Ajuste se quiser um efeito translúcido.
      - Conecte o Phong MAT ao Geo COMP para aplicar o material.

### Adicione um efeito dinâmico:
- Adicione um operador **Noise SOP** e conecte ao **Geo** para criar distorção na malha.
- Ajuste os parâmetros de *Amplitude* e *Roughness* para modificar a animação.

### Sincronizar com áudio:
- Importe um arquivo de áudio para um **Audio Analysis CHOP**.
- Conecte os valores de *Amplitude* ao parâmetro do **Noise SOP** para sincronizar o efeito com o som.
- No Audio Analysis CHOP, ative a opção Frequency Bands para dividir o áudio em faixas de frequência.
- Adicione um operador Math CHOP para normalizar os valores das bandas.
- Conecte diferentes faixas de frequência a diferentes parâmetros do Geo COMP:
      - Baixas frequências (graves): Controle a escala ou posição do modelo.
      - Médias frequências: Ajuste distorções na malha com Noise SOP.
      - Altas frequências (agudos): Modifique a intensidade da luz ou efeitos visuais.
- Use um Lag CHOP para suavizar as transições entre os valores.

### Renderizar e visualizar o resultado:
- Adicione um **Camera COMP** e um **Render TOP** para visualizar a cena.
- Ajuste a posição da câmera e a iluminação para obter melhores resultados.

### Exportação de Malhas e Animações para Controle em Tempo Real
A exportação de modelos e animações entre os softwares pode ser feita por:
- FBX (.fbx): Melhor opção para manter hierarquia e animações.
- Alembic (.abc): Ideal para animações baseadas em vértices.
- OBJ (.obj): Apenas para geometria estática.
- GLTF (.gltf/.glb): Mantém materiais PBR e animações leves.
  
Para controle dinâmico, podemos usar:
- OSC/MIDI: Para manipular transformações de objetos em tempo real.
- Python API: Para envio de dados entre Blender e TouchDesigner via UDP/TCP.
- Spout/Syphon: Para transmissão de vídeo gerado no Blender para o TouchDesigner em tempo real.

#### Procedimento de Exportação
1. No Blender, selecione o objeto 3D que deseja exportar.
2. Vá até File → Export → (selecione o formato desejado) ex: *FBX (.fbx)*
**Configurações recomendadas:**
- **Scale:** Defina para 1.0 para evitar problemas de escala no TouchDesigner.
- **Apply Transform:** Marque essa opção para garantir que a rotação e a posição estejam corretas.
- **Animation:** Marque Bake Animation se quiser incluir keyframes de movimento.
- **Selected Objects** (selecione apenas os objetos desejados). **(Include)**
- **Apply Modifiers** (se desejar a geometria final aplicada). **(Include)**
- **Mesh e Armature** (caso tenha animações esqueléticas). **(Include)**

#### Importação no TouchDesigner
1. No TouchDesigner, adicione um **Geometry COMP**.
2. Dentro do Geometry COMP, insira um **File SOP**.
3. No File SOP, carregue o arquivo **.fbx** ou **.obj.**
4. Se precisar de animação, conecte um **Animation COMP** e configure os controles.


### Controle de Malhas e Animações com OSC/MIDI
Para **controlar animações externamente**, podemos usar **OSC (Open Sound Control)** ou **MIDI** para enviar comandos do Blender para o TouchDesigner.

#### Controle via OSC
- No Blender, use **Add-on OSC** Sender para transmitir dados de animação.
- No TouchDesigner, utilize um **OSC In CHOP** para receber os valores e aplicá-los a parâmetros.

#### Controle via MIDI
- No Blender, crie uma animação e exporte os keyframes para um arquivo **MIDI**.
- No TouchDesigner, use um **MIDI In CHOP** para mapear os valores MIDI para transformação de objetos.

### Comunicação em Tempo Real via Python API  
- No Blender, podemos utilizar a API do Python para enviar dados de posição, rotação e escala para o TouchDesigner via **UDP** ou **OSC**.
- No TouchDesigner, podemos receber os dados com um **OSC In CHOP** e aplicá-los à posição de um objeto.

### Melhor Formado 
A melhor forma de exportação depende do seu objetivo:
- **Para geometria estática: OBJ ou FBX.**
- **Para animações esqueléticas: FBX.**
- **Para animações de vértices: Alembic.**
- **Para controle externo: OSC/MIDI/Python API.**

### Referências de Aplicações
- **Performances Audiovisuais ao Vivo**: Artistas como **Max Cooper** e **Reeps One** utilizam TouchDesigner para sincronizar visuais 3D gerados no Blender com suas performances musicais.
- **Instalações Imersivas**: O coletivo **Obscura Digital** e **TeamLab** desenvolveram instalações projetivas interativas utilizando Blender para modelagem e TouchDesigner para processamento dinâmico.
- **Videomapping**: Projetos como o **Light Festival** em Praga e **Mutek** utilizaram Blender para modelar superfícies arquitetônicas e TouchDesigner para projetar conteúdo responsivo em tempo real.
- **Realidade Virtual e Aumentada**: A empresa **Moment Factory** e o **MIT Media Lab** integraram Blender e TouchDesigner em experiências de VR e AR para eventos e espaços públicos.
- **Exploração Científica e Educacional**: O **MIT Media Lab** tem utilizado essa combinação para simulação de fenômenos naturais e explorações educacionais interativas.
- **Cinema Experimental**: Artistas como Refik Anadol e Universal Everything combinam TouchDesigner e Blender para criar experiências visuais dinâmicas para cinema imersivo e exploração digital.


