# Prompts utilizados na pesquisa (Gerados po IA)

## Contexto

Este arquivo registra os prompts utilizados durante a pesquisa do caso **Boeing 737 MAX e o sistema MCAS**, realizada com auxílio de um modelo de inteligência artificial.

A IA foi utilizada como ferramenta de pesquisa e apoio à compreensão dos aspectos técnicos do caso. As informações obtidas foram posteriormente confrontadas com fontes primárias, conforme solicitado na atividade.

---

## Prompt 1 — Pesquisa inicial do caso

**Objetivo:** obter uma visão geral do caso, compreender o funcionamento do MCAS e identificar os principais pontos técnicos que precisariam ser conferidos posteriormente.

```text
Estou realizando uma atividade acadêmica da disciplina de Qualidade de Software chamada “Caça ao Desastre”. O caso que devo analisar é o Boeing 737 MAX e o sistema MCAS, relacionado aos acidentes do Lion Air JT610 (2018) e Ethiopian Airlines ET302 (2019).

Quero que você faça uma pesquisa inicial sobre o caso, mas NÃO faça ainda a análise com os conceitos de qualidade de software. Neste momento, quero apenas compreender e levantar os fatos técnicos e históricos que posteriormente serão conferidos em fontes primárias.

Explique:

1. O que é o Boeing 737 MAX e o que é o sistema MCAS.
2. Qual era a finalidade do MCAS.
3. Como o MCAS funcionava tecnicamente.
4. Qual era a relação entre os sensores de ângulo de ataque (AOA) e o MCAS.
5. O que aconteceu no voo Lion Air JT610.
6. O que aconteceu no voo Ethiopian Airlines ET302.
7. Qual foi a relação do MCAS com os dois acidentes.
8. Quais problemas técnicos foram identificados nas investigações.
9. Como questões relacionadas aos sensores de AOA, à lógica do MCAS, à autoridade do sistema, aos alertas e ao treinamento dos pilotos contribuíram para o problema.
10. Quais eram as características do MCAS originalmente projetado e como sua implementação se relacionava com o processo de certificação.
11. Quais decisões de engenharia, desenvolvimento, testes, certificação ou comunicação foram posteriormente questionadas.
12. O que as investigações oficiais concluíram sobre os acidentes.
13. Monte também uma linha do tempo dos principais acontecimentos.

IMPORTANTE:

- Para cada afirmação factual importante, indique de onde a informação foi obtida.
- Priorize fontes primárias e oficiais, como relatórios da KNKT, NTSB, FAA, autoridades de investigação da Etiópia, documentos oficiais da Boeing, documentos de certificação e órgãos reguladores.
- Não invente fontes, documentos, páginas, números de relatório ou links.
- Sempre que possível, informe o título completo do documento, instituição responsável, ano/data e link oficial.
- Diferencie claramente fatos comprovados de interpretações ou informações que ainda precisam ser verificadas.
- Se uma informação não puder ser confirmada diretamente em uma fonte confiável, diga isso.
- Não faça ainda a análise de Qualidade de Software da atividade.

Ao final, crie uma seção chamada “Pontos que precisam ser verificados”, listando as afirmações técnicas mais importantes que eu deveria conferir diretamente nas fontes primárias.
```

---

## Prompt 2 — Auditoria da resposta da IA

**Objetivo:** verificar se a própria IA havia apresentado informações incorretas, imprecisas ou não confirmadas.

```text
Agora faça uma auditoria da sua própria resposta anterior.

NÃO quero uma nova explicação geral sobre o Boeing 737 MAX. Quero verificar se as informações que você apresentou anteriormente estão realmente corretas.

Analise as principais afirmações factuais da sua resposta uma por uma e, para cada uma, informe:

- a afirmação feita anteriormente;
- a fonte utilizada;
- se a fonte é primária, secundária ou terciária;
- o documento exato utilizado;
- a página ou seção correspondente, quando for possível verificar;
- se a fonte realmente sustenta a afirmação;
- a classificação: CONFIRMADA, PARCIALMENTE CONFIRMADA, NÃO CONFIRMADA ou INCORRETA;
- uma correção, quando necessário.

Dê atenção especial às seguintes afirmações:

a) A autoridade do MCAS de aproximadamente 0,6° e posteriormente até aproximadamente 2,5°.

b) A faixa de Mach de operação atribuída ao MCAS, especialmente a afirmação de que estaria entre aproximadamente 0,2 e 0,8.

c) O fato de o MCAS utilizar apenas um sensor de AOA por vez.

d) O fato de uma única leitura incorreta de AOA poder provocar a ativação do MCAS.

e) A possibilidade de ativações repetidas do MCAS.

f) A questão do alerta AOA DISAGREE e sua relação com o AOA Indicator.

g) A afirmação de que o AOA DISAGREE era opcional.

h) A disponibilidade ou ausência do AOA DISAGREE nas aeronaves envolvidas no Lion Air JT610 e no Ethiopian Airlines ET302.

i) A afirmação de que a Boeing identificou algum problema relacionado ao AOA DISAGREE antes dos acidentes.

j) A afirmação de que a análise de segurança não considerou adequadamente a possibilidade de ativações repetidas do MCAS.

k) A afirmação de que os testes do MCAS utilizaram aproximadamente 0,6° e não consideraram adequadamente 2,5°.

l) A afirmação de que o MCAS foi omitido da documentação fornecida aos pilotos.

m) A afirmação de que o FCOM ou QRH não apresentavam informações adequadas sobre o MCAS antes dos acidentes.

n) As afirmações sobre as premissas utilizadas na certificação em relação à resposta dos pilotos diante de múltiplos alertas.

o) A afirmação de que o FAA tratou o 737 MAX como uma derivação do 737NG por meio de um certificado de tipo alterado.

p) A data ou período da certificação do 737 MAX.

q) As conclusões da investigação do Lion Air JT610 sobre a combinação de fatores que contribuiu para o acidente.

r) As diferenças entre as conclusões do NTSB e da autoridade etíope sobre a origem do erro de AOA no Ethiopian Airlines ET302.

Também verifique se existe alguma inconsistência nos dados bibliográficos apresentados anteriormente, especialmente no número de identificação do relatório da KNKT e no endereço utilizado para o documento.

No final, apresente:

1. AFIRMAÇÕES CONFIRMADAS
2. AFIRMAÇÕES PARCIALMENTE CONFIRMADAS
3. AFIRMAÇÕES NÃO CONFIRMADAS
4. ERROS COMETIDOS PELA IA
5. CORREÇÕES QUE A PRÓPRIA IA PRECISOU FAZER
6. Os 3 pontos mais importantes que precisam ser corrigidos na resposta original.

Não invente páginas, citações ou links. Se você não conseguir verificar diretamente uma informação em uma fonte primária, escreva claramente:

“Não consegui verificar diretamente esta informação na fonte primária.”

A finalidade desta etapa é identificar erros e limitações da própria resposta da IA, e não produzir uma nova análise de Qualidade de Software.
```

---

## Observação sobre a etapa seguinte

Depois desses dois prompts, a pesquisa com a IA foi encerrada. As informações foram então confrontadas com fontes primárias, incluindo documentos da **FAA, NTSB e KNKT**, para identificar quais afirmações poderiam ser utilizadas no trabalho.

A análise de Qualidade de Software foi realizada separadamente, pois a atividade determina que a análise da Unidade I seja desenvolvida pelo estudante.
