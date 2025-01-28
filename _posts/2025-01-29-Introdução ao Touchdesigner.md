# **Introdução ao Touchdesigner**
## **O que é o TouchDesigner?**
  - É um software de criação de conteúdos visuais e interativos em tempo real, desenvolvido pela empresa canadense Derivative

## **Usos comuns:**
- **Performances Audiovisuais:** Sincronização de som e imagem em tempo real.
- **Instalações Interativas:** Respostas a estímulos externos (toque, movimento, som).
- **Mapeamento de Projeção:** Criação de conteúdos visuais projetados em superfícies irregulares.
- **Design Visual:** Produção de gráficos generativos, animações e efeitos especiais.

## **Características principais:**
- **Interface Nodal:**
  - Todo o projeto é construído através de nós/nodes, chamados de operadores. Esses operadores representam funções específicas (como gerar imagens, processar áudio ou controlar dispositivos) e podem ser conectados uns aos outros para criar fluxos complexos.
- **Processamento em Tempo Real:**
  - O TouchDesigner é projetado para gerar conteúdo visual e interativo de maneira instantânea, sem necessidade de renderização, permitindo ajustes e testes imediatos. Tornando-o ideal para aplicações ao vivo, como performances audiovisuais e projeções.
- **Versatilidade:**
  - Ele suporta várias entradas e saídas de dados, incluindo áudio, vídeo, sensores, controladores MIDI, DMX, OSC, entre outros. É possível integrar o software a dispositivos externos, como câmeras, sistemas de projeção e placas de vídeo avançadas.
- **Integração com Hardware e Protocolos:**
  - O TouchDesigner é projetado para gerar conteúdo visual e interativo de maneira instantânea, sem necessidade de renderização, permitindo ajustes e testes imediatos. Tornando-o ideal para aplicações ao vivo, como performances audiovisuais e projeções.

## **Por que usar o TouchDesigner?**
1. **Acessibilidade:** 
  - Possui uma versão gratuita com recursos avançados (limitada a 1280x1280 de resolução).
2. **Flexibilidade:** 
  - Permite desde experimentos artísticos simples até produções comerciais complexas.
3. **Comunidade ativa:** 
  - Existe uma vasta comunidade de artistas e desenvolvedores que compartilham projetos, tutoriais e ideias.

⚠️ **Atenção:** O Touchdesigner é atualizado com frequência, geralmente a cada quatro/cinco semanas. Dessa forma, certifique-se a versão na qual estamos trabalhando.

## **Explorando a Interface Básica**
1. **Para navegar pela interface:** Botão direito do mouse, clica, segura e arrasta.
2. **Para dar zoom:** Botão de rolagem/”bolinha” do mouse (scroll).
(IMAGEM)
3. **Para criar OP's (operadores):** botão “Tab”
(IMAGEM)

##**Tipos de Operadores (OPs): **
- **COMP** (Componentes): Organização de projetos e interação.
- **TOP** (Texture Operators): Imagem, vídeo, composição, texturas e efeitos.
- **CHOP** (Channel Operators): Controle de dados/ondas/sinais em tempo real (áudio, interatividade).
- **SOP** (Surface Operators): Geometria 3D.
- **MAT** (Material Operators): Materiais para 3D.
- **DAT** (Data Operators): Dados tabulares e texto.
(imagem)

## **Fluxo Nodal** (A base do TouchDesigner)
# **O que é:** Conexão de nós (ou operadores) que processam dados visuais, sonoros ou interativos;
# **Tipos de Conexões entre Operadores:** 
1. Porta de Saída:
  - Localizada no lado direito de um operador.
  - Representa o dado processado que será enviado para outro operador.
  - Tipicamente aparece como um círculo ou seta.
2. Porta de Entrada:
  - Localizada no lado esquerdo de um operador.
  - Recebe o dado processado por um operador anterior no fluxo.
3. Conexões entre Operadores:
  - Feitas arrastando o mouse da saída de um operador para a entrada de outro.
  - As linhas que conectam os operadores visualizam o fluxo de dados.

# **Regras das Conexões**
1. **Compatibilidade de Tipos:**
  - Apenas operadores do mesmo tipo podem ser conectados diretamente (por exemplo, TOP para TOP, CHOP para CHOP).
  - Exceção: É possível converter tipos diferentes usando operadores intermediários (ex.: um CHOP pode controlar parâmetros de um TOP).
2. **Múltiplas Conexões:**
  - Um operador pode ter múltiplas conexões de saída, alimentando vários operadores subsequentes.
  - Da mesma forma, um operador pode ter múltiplas entradas, recebendo dados de diferentes fontes.
3. **Ordem das Entradas:**
  - Alguns operadores com múltiplas entradas (ex.: Composite TOP) interpretam a ordem das conexões para determinar como os dados serão processados.

# **Modificando Conexões**
1. **Desconectar Operadores:**
  - Clique com o botão direito na linha de conexão e escolha "Disconnect".
  - Ou arraste a linha de conexão para longe e solte.

2. **Substituir Conexões:**
  - Conecte um novo operador à entrada/saída desejada. O TouchDesigner automaticamente reconfigura o fluxo.

# **Vantagens do Fluxo Nodal:
1. **Visualização Imediata:** Cada operador exibe seu resultado diretamente na interface, permitindo entender o impacto de cada etapa no fluxo.
2. **Modularidade:** Projetos são criados de forma modular, facilitando alterações e ajustes.
3. **Escalabilidade:** Fluxos podem começar simples e se tornar complexos à medida que novos operadores são adicionados.
4. **Organização Visual:** Use alinhamento e grupos lógicos de operadores para manter o projeto legível.



 




