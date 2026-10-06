# CAÇA AO DESASTRE

## Boeing 737 MAX e o sistema MCAS

**Disciplina:** Qualidade de Software
**Unidade:** I — Fundamentos da Qualidade de Software
**Caso analisado:** Boeing 737 MAX e o sistema MCAS
**Período:** 2018–2019

---

## 1. Resumo do caso

O Boeing 737 MAX foi desenvolvido como uma nova geração da família 737, incorporando alterações que buscavam melhorar seu desempenho e eficiência. Entre essas alterações estava o sistema **MCAS (Maneuvering Characteristics Augmentation System)**, um sistema automatizado de controle de voo criado para modificar o comportamento da aeronave em determinadas condições de voo.

O MCAS utilizava informações provenientes dos sensores de **ângulo de ataque (AOA)** para determinar quando deveria atuar. No projeto original, uma única leitura incorreta de AOA poderia fazer com que o sistema fosse ativado. Quando ativado, o MCAS comandava o estabilizador horizontal para produzir um movimento de nariz para baixo.

O problema tornou-se crítico quando dados incorretos de AOA provocaram ativações repetidas do sistema. Nos dois acidentes analisados, os pilotos receberam diversas indicações e alertas enquanto tentavam controlar a aeronave.

Em **29 de outubro de 2018**, o Lion Air JT610 caiu no Mar de Java aproximadamente 13 minutos após a decolagem de Jacarta, causando a morte de 189 pessoas.

Em **10 de março de 2019**, o Ethiopian Airlines ET302 caiu poucos minutos após a decolagem de Adis Abeba, causando a morte de 157 pessoas.

As investigações identificaram uma combinação de fatores relacionados ao sistema de controle de voo, aos dados incorretos de AOA, à atuação do MCAS, às informações disponibilizadas aos pilotos e às premissas utilizadas durante o processo de projeto e certificação.

Assim, o caso não pode ser reduzido simplesmente a "um erro de software". Ele envolve uma cadeia de decisões de engenharia, desenvolvimento, avaliação de segurança, certificação, comunicação e interação entre sistema e usuário.

---

## 2. Linha do tempo

| Data               | Acontecimento                                                                                                                            |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| **2011**           | A Boeing anuncia o desenvolvimento do 737 MAX como nova geração da família 737.                                                          |
| **2016**           | O primeiro 737 MAX realiza seu primeiro voo.                                                                                             |
| **2017**           | O 737 MAX recebe a certificação necessária para entrada em serviço.                                                                      |
| **29/10/2018**     | O Lion Air JT610 cai pouco depois da decolagem de Jacarta, na Indonésia.                                                                 |
| **2018–2019**      | A investigação do acidente do Lion Air identifica problemas relacionados aos dados de AOA, ao MCAS e a outros fatores.                   |
| **10/03/2019**     | O Ethiopian Airlines ET302 cai pouco depois da decolagem de Adis Abeba, na Etiópia.                                                      |
| **Março de 2019**  | O 737 MAX é retirado temporariamente de operação em diversos países.                                                                     |
| **2019**           | FAA, NTSB e outras autoridades analisam o projeto, a certificação e os fatores relacionados ao MCAS.                                     |
| **2019**           | O Joint Authorities Technical Review (JATR) publica sua análise do processo de certificação do sistema de controle de voo do 737 MAX.    |
| **2020**           | A FAA aprova alterações necessárias para o retorno do 737 MAX ao serviço.                                                                |
| **2020 em diante** | O caso continua sendo utilizado como referência para discussões sobre segurança, certificação, fatores humanos e engenharia de sistemas. |

---

## 3. Causa técnica

O problema técnico central estava relacionado à interação entre os **sensores de ângulo de ataque (AOA)**, o sistema **MCAS** e a resposta da aeronave aos comandos produzidos pelo sistema.

### 3.1 Funcionamento do MCAS

O MCAS foi projetado para atuar automaticamente em determinadas condições de voo. Para isso, utilizava informações de AOA.

No projeto original, o sistema podia utilizar a informação de **apenas um sensor de AOA por vez**. Dessa forma, uma leitura incorreta poderia ser interpretada pelo sistema como uma condição real de elevado ângulo de ataque.

Quando essa condição era identificada, o MCAS podia comandar o estabilizador horizontal no sentido de produzir **nariz para baixo**.

### 3.2 Ativações repetidas

Um dos problemas mais importantes foi que a atuação do MCAS não necessariamente ocorria apenas uma vez.

Depois que os pilotos utilizavam o comando elétrico de compensação para neutralizar o efeito, o sistema poderia voltar a ser ativado caso a condição que havia provocado sua atuação continuasse presente.

Isso criou um ciclo no qual:

**dado incorreto de AOA → ativação do MCAS → nariz para baixo → intervenção do piloto → nova ativação**

Esse comportamento aumentou significativamente a dificuldade enfrentada pelos pilotos.

### 3.3 AOA DISAGREE

Outro problema identificado esteve relacionado ao alerta **AOA DISAGREE**, que deveria indicar uma diferença entre as informações dos sensores de ângulo de ataque.

A questão não era simplesmente que o alerta fosse "opcional". O problema estava relacionado à sua implementação e à sua vinculação com a opção de **AOA Indicator**.

Como consequência, o alerta não estava disponível conforme deveria em determinadas aeronaves envolvidas nos acidentes.

Posteriormente, foram determinadas alterações para corrigir essa condição.

### 3.4 Informação disponível aos pilotos

Outro elemento importante foi a quantidade e a forma das informações fornecidas aos pilotos sobre o funcionamento do MCAS.

O sistema não foi apresentado aos pilotos de forma proporcional à importância que sua atuação poderia ter para o comportamento da aeronave.

Além disso, as situações enfrentadas nos acidentes envolveram múltiplas indicações e alertas simultaneamente, o que é relevante para compreender a resposta humana diante da falha.

### 3.5 A causa não foi um único erro

A análise dos relatórios oficiais mostra que os acidentes resultaram de uma **combinação de fatores**, e não de um único defeito isolado.

Entre os fatores envolvidos estão:

* dados incorretos provenientes do sistema de AOA;
* dependência do MCAS de uma única fonte de informação;
* atuação automática do MCAS;
* possibilidade de ativações repetidas;
* questões relacionadas aos alertas e às informações disponíveis;
* premissas utilizadas no processo de segurança e certificação;
* interação entre o sistema automatizado e os pilotos.

Por isso, o caso deve ser analisado como uma falha de um **sistema sociotécnico**, e não apenas como um bug de programação.

---

# 4. Análise com os conceitos da Unidade I

> **Esta seção é a análise do grupo/estudante sobre o caso. Ela deve demonstrar a aplicação dos conceitos estudados na Unidade I.**

## 4.1 Verificação e validação

O caso mostra que verificar se um sistema atende aos requisitos definidos não é necessariamente suficiente para garantir que ele seja seguro em uma situação real.

A **verificação** está relacionada à avaliação de se o sistema foi desenvolvido de acordo com os requisitos e especificações estabelecidos.

A **validação**, por outro lado, busca verificar se o sistema realmente atende à necessidade para a qual foi desenvolvido e se seu comportamento é adequado no contexto real de utilização.

No caso do 737 MAX, existiram processos de engenharia, testes e certificação. Entretanto, as investigações posteriores levantaram problemas relacionados às premissas utilizadas para representar a resposta dos pilotos diante de determinadas situações.

Isso mostra uma diferença importante: um sistema pode passar por processos formais de verificação e ainda apresentar problemas quando colocado diante de uma situação real que não foi adequadamente representada durante sua avaliação.

---

## 4.2 QA e QC

O caso também pode ser relacionado à diferença entre **Quality Assurance (QA)** e **Quality Control (QC)**.

O **QA** está relacionado aos processos utilizados para prevenir problemas e garantir que o desenvolvimento siga práticas adequadas.

O **QC** está mais relacionado à identificação de problemas no produto por meio de inspeções, testes e avaliações.

No caso analisado, não seria suficiente apenas encontrar um comportamento incorreto durante um teste. Era necessário que o próprio processo de desenvolvimento e certificação fosse capaz de identificar riscos relacionados à arquitetura do sistema, às premissas utilizadas e à interação entre o MCAS e os pilotos.

Dessa forma, o caso evidencia que qualidade não depende apenas de testar o produto no final. Ela também depende da qualidade dos processos utilizados para projetar, avaliar e certificar o sistema.

---

## 4.3 Custo da não qualidade

Os custos da não qualidade neste caso foram extremamente elevados.

Além das perdas humanas decorrentes dos dois acidentes, houve impactos financeiros, operacionais e institucionais para diversas organizações envolvidas.

Também ocorreram consequências para:

* companhias aéreas;
* passageiros;
* fabricantes;
* órgãos reguladores;
* profissionais envolvidos na operação;
* imagem e confiança na aeronave;
* processos de certificação.

O caso demonstra que investir na prevenção de falhas durante o desenvolvimento e na identificação de riscos pode representar um custo muito menor do que lidar posteriormente com as consequências de uma falha crítica.

---

## 4.4 As visões de Garvin

O caso pode ser relacionado principalmente às dimensões de qualidade associadas a **conformidade**, **desempenho**, **confiabilidade** e **segurança**.

A aeronave precisava não apenas cumprir requisitos técnicos, mas também apresentar comportamento confiável e seguro em condições reais de operação.

Uma interpretação limitada de qualidade poderia considerar apenas se o sistema atendia às especificações estabelecidas. Entretanto, uma visão mais ampla exige considerar também se o produto apresenta o comportamento esperado em situações reais e se os riscos foram adequadamente tratados.

Assim, o caso mostra que qualidade de software e de sistemas críticos não deve ser entendida somente como "funcionar conforme programado", mas como a capacidade de entregar o comportamento esperado de maneira segura e confiável.

---

## 4.5 Qualidade do produto ou qualidade do processo?

O caso envolve os dois aspectos.

Existe um problema relacionado ao **produto**, porque o comportamento do sistema MCAS podia contribuir para uma situação perigosa quando recebia dados incorretos de AOA.

Mas também existem questões relacionadas ao **processo**, envolvendo decisões de projeto, análise de segurança, testes, comunicação, certificação e avaliação das condições reais de operação.

Por isso, analisar o caso apenas como uma falha do produto seria insuficiente.

A principal conclusão desta análise é que **a qualidade do produto está diretamente relacionada à qualidade dos processos utilizados para desenvolvê-lo, avaliá-lo e validá-lo**.

---

# 5. O que poderia ter evitado a falha?

A partir dos relatórios analisados, é possível identificar diferentes medidas que poderiam ter reduzido o risco.

### 5.1 Redundância e tratamento dos dados de AOA

O sistema poderia ter utilizado mecanismos mais robustos para lidar com informações divergentes dos sensores antes de permitir que uma única leitura provocasse uma atuação automática significativa.

### 5.2 Avaliação de ativações repetidas

Os testes e análises de segurança deveriam considerar de maneira adequada o comportamento do sistema quando o MCAS fosse ativado repetidamente e o piloto tentasse neutralizar sua atuação.

### 5.3 Avaliação da interação humano-sistema

Era necessário considerar não apenas o comportamento isolado do sistema, mas também a situação completa enfrentada pelos pilotos, incluindo múltiplos alertas, informações disponíveis e carga de trabalho.

### 5.4 Melhor comunicação aos pilotos

Informações relevantes sobre o comportamento do sistema deveriam estar adequadamente disponíveis para os profissionais responsáveis pela operação da aeronave.

### 5.5 Maior atenção às premissas de certificação

As premissas utilizadas durante a análise de segurança deveriam representar de forma adequada as condições reais de operação.

### 5.6 Melhorias no processo de qualidade

De maneira geral, o caso poderia ter sido mitigado por um processo que integrasse melhor:

**requisitos → projeto → análise de riscos → testes → validação → fatores humanos → certificação → operação real**

Isso reforça que a qualidade precisa ser considerada durante todo o ciclo de desenvolvimento, e não apenas no momento em que o produto está pronto.

---

# 6. O que a IA errou ou não sabia?

A pesquisa com o LLM foi utilizada como ponto de partida. Posteriormente, suas afirmações foram confrontadas com documentos oficiais.

Esse processo mostrou que a IA apresentou informações corretas, mas também cometeu erros e apresentou algumas afirmações sem confirmação suficiente.

| Afirmação da IA                                                         | Resultado da verificação                | Problema identificado                                                                                |
| ----------------------------------------------------------------------- | --------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| O MCAS podia ser ativado a partir de uma única leitura incorreta de AOA | **Confirmada**                          | A informação é sustentada por documentos oficiais.                                                   |
| O MCAS podia ser ativado repetidamente                                  | **Confirmada**                          | A FAA descreve a possibilidade de novas ativações após a intervenção do piloto.                      |
| O AOA DISAGREE era simplesmente opcional                                | **Parcialmente confirmada / imprecisa** | O problema envolvia a implementação do alerta e sua vinculação à opção AOA Indicator.                |
| Os testes consideraram aproximadamente 0,6° e não 2,5°                  | **Incorreta**                           | A própria IA posteriormente reconheceu que sua afirmação sobre os testes estava incorreta.           |
| O MCAS operava na faixa de Mach 0,2–0,8                                 | **Não confirmada**                      | A IA não conseguiu confirmar diretamente esse intervalo numérico nas fontes primárias utilizadas.    |
| A causa do problema no ET302 poderia ser apresentada sem ressalvas      | **Limitada**                            | Existem diferenças entre as conclusões da autoridade etíope e do NTSB sobre a origem do erro de AOA. |

### O erro mais relevante encontrado

O erro considerado mais interessante foi a afirmação sobre os testes do MCAS.

Inicialmente, a IA apresentou a informação de maneira que indicava que a autoridade de aproximadamente **2,5°** não havia sido adequadamente considerada nos testes. Quando solicitada a revisar sua própria resposta, a IA reconheceu que essa afirmação estava incorreta.

Esse resultado foi importante porque mostrou que a resposta inicial parecia tecnicamente convincente, mas uma afirmação específica precisava ser confrontada com a documentação original.

### O que aprendemos com a checagem da IA?

A principal conclusão dessa etapa foi que uma resposta detalhada e aparentemente bem fundamentada não deve ser considerada automaticamente verdadeira.

A IA foi útil para:

* localizar conceitos;
* organizar o caso;
* identificar possíveis pontos técnicos;
* sugerir fontes;
* levantar hipóteses para investigação.

Entretanto, as informações mais importantes precisaram ser confrontadas com documentos oficiais.

---

# 7. Fontes

## Fontes primárias

**FEDERAL AVIATION ADMINISTRATION (FAA).** *Summary of the FAA's Review of the Boeing 737 MAX*. Washington, D.C.: FAA, 2020.

**FEDERAL AVIATION ADMINISTRATION (FAA).** *Boeing 737 MAX Flight Control System: Joint Authorities Technical Review*. Washington, D.C.: FAA, 2019.

**FEDERAL AVIATION ADMINISTRATION (FAA).** *737 Technical Advisory Board Final Report: Design Change to MCAS*. Washington, D.C.: FAA.

**NATIONAL TRANSPORTATION SAFETY BOARD (NTSB).** *Assumptions Used in the Safety Assessment Process and the Effects of Multiple Alerts and Indications on Pilot Performance*. Washington, D.C.: NTSB, 2019. Safety Report ASR-19/01.

**KOMITE NASIONAL KESELAMATAN TRANSPORTASI (KNKT).** *Aircraft Accident Investigation Report: PT. Lion Mentari Airlines Boeing 737-8 (MAX), PK-LQP, Tanjung Karawang, West Java, 29 October 2018*. Jakarta: KNKT.

**NATIONAL TRANSPORTATION SAFETY BOARD (NTSB).** *NTSB Comments on Ethiopian Accident Investigation Bureau Final Report*. Washington, D.C.: NTSB, 2023.

---

## Observação sobre as fontes

As fontes primárias foram priorizadas porque a atividade exige a conferência das informações fornecidas pela IA em documentos oficiais.

As principais instituições consultadas foram:

* FAA — Federal Aviation Administration;
* NTSB — National Transportation Safety Board;
* KNKT — Komite Nasional Keselamatan Transportasi;
* autoridades responsáveis pela investigação do acidente Ethiopian Airlines ET302.

---

## Conclusão

O caso do Boeing 737 MAX demonstra que problemas de qualidade em sistemas críticos não podem ser analisados apenas como erros de programação.

A falha envolveu a interação entre software, sensores, automação, fatores humanos, processos de engenharia, testes, certificação e operação.

A principal lição para a qualidade de software é que **um sistema pode atender a requisitos definidos e ainda assim apresentar riscos quando os requisitos, as premissas ou os cenários de validação não representam adequadamente a realidade de uso**.

Além disso, o caso demonstra a importância da verificação independente das informações produzidas por ferramentas de inteligência artificial. A IA pode acelerar a pesquisa, mas suas respostas precisam ser confrontadas com fontes confiáveis, principalmente quando tratam de sistemas críticos e decisões técnicas.
