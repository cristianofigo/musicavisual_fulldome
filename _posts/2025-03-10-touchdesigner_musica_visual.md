---
layout: post
title: TouchDesigner para Música Visual
subtitle: Criando Visuais Reativos ao Som
comments: true
mathjax: true
author: Nala Quimera
---

## Introdução
- O TouchDesigner é um software de desenvolvimento visual em tempo real amplamente utilizado na criação de obras audiovisuais interativas ao som ou movimento. Sua flexibilidade permite que artistas e desenvolvedores transformem dados de áudio em composições visuais dinâmicas, sincronizadas e altamente personalizáveis. 
- Nesse post exploraremos como o TouchDesigner pode ser empregado na música visual, destacando técnicas, ferramentas e exemplos práticos para a criação de performances audiovisuais reativas.

## Requisitos
Antes de começar, certifique-se de ter instalado:
- TouchDesigner
- Um arquivo de áudio ou entrada de áudio ativa

## Fundamentos Técnicos
### Análise de Áudio e Conversão para Elementos Visuais:
- O TouchDesigner permite extrair informações de áudio em tempo real e utilizá-las para controlar elementos visuais. Isso é feito através dos operadores CHOP (Channel Operators), que processam sinais numéricos e são essenciais para mapear dados de áudio em elementos visuais.
- Antes de continuarmos, se você é completamente novo/a/e no Touchdesigner, é importante que saiba que para abrir a tabela dos diferentes tipos operatores divididos por cores basta clicar na tecla **Tab** 
![Screenshot-2020-04-03-17 06 52](https://github.com/user-attachments/assets/04929801-2861-4a9f-a142-421ca662b6ca)

## 1. Capturando e Processando o Áudio
O primeiro passo é garantir que o áudio esteja pronto para análise. Para isso:

- Adicione um **Audio File In** para adicionar um áudio desejado;
- Adicione um **Audio Devie Out**  para que possamos ouvi-lo; 
- Use um **Math CHOP** para combinar os canais em um único canal;
- Alternativa: Selecione Mono, mas isso pode afetar a saída para dispositivos de áudio.
- Melhor abordagem: Em **Math** combine os canais em **Combine Channels** > **Average** para manter um sinal equilibrado.
- Adicione um **Audio Spectrum** e um **Analyze CHOP** para visualizar a frequência e amplitude do áudio.

## 2. Normalizando os Dados
Para garantir que os valores extraídos sejam utilizáveis:
- Adicione um **Envelope CHOP** e um **Math CHOP**.
- Conecte a saída do **Envelope CHOP** ao **Math CHOP**.
- Nos parâmetros do **Envelope**, altere **Envelope With** para 10 para normalizar os valores entre 0 e 1;
- Em **Math** altere **Combine Chops**, em **OP8**, para **Divide**;
- Use um **Trail CHOP** para visualizar os dados normalizados.

## 3. Criando um Sinal de On/Off (Trigger)
Se quisermos extrair um sinal binário baseado na presença de uma batida:
- Adicione um **Trigger CHOP**.
- Ajuste:
   - **Sustain** > **Min Sustain Length** e **Releate Length** para 0 e **Sustain Level** para 1.
   - **Attack** > **Delay Length**, **Attack Length** e **Peak Length** para 0
   - **Threshold** para 0.7 (ou 0.9 para detectar apenas batidas fortes).
- Depois conecte um **Null** ao **Trigger** e renomeie como *HUB*
  
Agora, o sinal será ativado apenas quando a amplitude do áudio ultrapassar o limite definido.

## 4. Alternativa: Beat Detection com Filtros
Outra abordagem para detecção de batidas: Utilize filtros de áudio para separar faixas de frequência.
- Use um **Audio Analysis CHOP** para extrair canais específicos como Kick, Snare e Hats.
  - Baixas frequências (Kick)
  - Médias frequências (Snare)
  - Altas frequências (Hi-Hats)



