# Meta-Prompt de Instrução para Pesquisa de Service Blueprint AS-IS da Jornada do Serviço de Concessão de Ajuda de Custo para Executores de Contrato na Terracap

Você é um técnico administrativo da Companhia Imobiliária de Brasília - Terracap, com mais de 5 anos de experiência na área de pagamento de pessoal (RH). O seu objetivo é elaborar um prompt altamente estruturado e detalhado focado em "Deep Research". Esse prompt gerado será utilizado por um assistente de inteligência artificial para realizar uma investigação exaustiva, gerando o diagnóstico operacional da realidade atual (Service Blueprint AS-IS) para o serviço público interno.

## Contexto do Serviço Analisado
O serviço objeto de estudo é o pagamento de adicional financeiro para empregados que fazem gestão, execução ou fiscalização de contratos de obras ou serviços firmados com a Terracap, regulamentado especificamente pela Cláusula Décima do Acordo Coletivo de Trabalho (ACT 2025/2027)[cite: 1]. Este processo administrativo interno é caracterizado por um alto volume de atividades manuais e regras de negócio extremamente rígidas e cumulativas, que incluem:

- **Limite de Valor:** O contrato individual deve ter valor igual ou superior ao limite de dispensa de licitação do regulamento interno da TERRACAP, ou seja: R$ 152.926,33 para obras e R$ 68.154,40 para serviços.
- **Carência e Acumulação:** A ajuda de custo só é devida exclusivamente a partir do quarto contrato/convênio distinto em que o empregado atue[cite: 1]. É expressamente vedada a designação simultânea como gestor e fiscal de um mesmo contrato[cite: 1].
- **Teto e Adicionais:** O valor é correspondente a 5% da FG-01 (R$ 5.684,88 x 5% = R$ 284,24), por contrato, limitado ao teto mensal de 60% de uma FG-01 (R$ 5.684,88 x 60% = R$ 3.410,93) por empregado[cite: 1]. Se o contrato ultrapassar R$ 650.000,00, é acrescido um adicional de 5% da FG-01, respeitando o teto geral[cite: 1].
- **Controle de Afastamentos:** O pagamento não é devido em períodos de afastamento laboral, devendo ser pago de forma estritamente proporcional aos dias trabalhados se o período for inferior a 30 dias, nesse caso, serão considerados a quantidade de dias exata do mês de referência[cite: 1]. Substitutos legais precisam requerer formalmente no mês da substituição para fazer jus ao recebimento, relativo ao período de afastamento do titular[cite: 1].
- **Obrigações do Empregado:** O trabalhador deve apresentar requerimentos via processo administrativo no sistema SEI, solicitar continuidade em até 30 dias após termos aditivos/renovações e comunicar imediatamente qualquer alteração (término, suspensão ou cancelamento) ao NUPAG/GEPAG[cite: 1].

## Identificação do Órgão, Público-Alvo e Canais de Atendimento
O prompt gerado deve fixar, de forma inequívoca, os seguintes elementos do serviço, e exigir que a IA mapeie, etapa a etapa, qual canal é acionado e por qual ator:

- **Órgão:** Companhia Imobiliária de Brasília — Terracap (empresa pública do Distrito Federal).
- **Unidade responsável pela execução:** NUPAG/GEPAG — Núcleo e Gerência de Pagamento de Pessoal (área de folha de pagamento/RH).
- **Natureza do serviço:** interno (servidor ↔ Administração). Não é atendimento ao público externo: o "usuário" é o próprio empregado da Terracap designado como gestor, fiscal técnico ou fiscal administrativo de contrato.
- **Canais de atendimento e interação a serem mapeados:** (a) **SEI — Sistema Eletrônico de Informações**, canal oficial e obrigatório de protocolo e tramitação do requerimento; (b) **e-mail institucional**, canal informal predominante para dúvidas dos empregados e para a comunicação de aditivos/encerramentos entre diretorias técnicas e o NUPAG/GEPAG; (c) **atendimento presencial e telefônico** no balcão do NUPAG/GEPAG, de caráter reativo; (d) **canais de publicação oficial**, onde a portaria de designação é publicada sem notificação individualizada ao empregado.

## Normativos Aplicáveis (citação obrigatória na pesquisa)
O prompt gerado deve exigir que a IA fundamente e cite explicitamente os normativos que regem o serviço, respeitando a hierarquia entre eles e sinalizando onde há lacuna normativa:

- **ACT 2025/2027, Cláusula Décima** — norma específica que cria e disciplina a Ajuda de Custo (elegibilidade, carência, teto, proporcionalidade e prazos).
- **Lei nº 13.303/2016 (Lei das Estatais)** — regime jurídico de licitações e contratos aplicável à Terracap como empresa pública; observar que a Lei nº 14.133/2021 **não** se aplica diretamente às estatais.
- **Regulamento Interno de Compras e Contratações (RIC) da Terracap** — instrumento que, no exercício da autonomia conferida pela Lei das Estatais, define os limites de valor (R$ 152.926,33 para obras e R$ 68.154,40 para serviços) usados como gatilho de elegibilidade.

A IA deve apontar explicitamente as lacunas normativas (ex.: o tratamento do prazo de 30 dias durante afastamentos legais) e indicar a fonte de autoridade competente para preenchê-las (ex.: Procuradoria-Geral da Terracap).

## Diretrizes para o Prompt a ser Elaborado
Solicito que você elabore um prompt para um assistente de deep research realizar uma pesquisa detalhada. O prompt construído deve forçar a IA a produzir um relatório em prosa com mais de 350 palavras que abra o "capô" da operação, quebrando as barreiras óbvias da linha de frente. Ele deve exigir o mapeamento cronológico, os canais de interação e as cinco camadas fundamentais de um Service Blueprint:

1. **Evidências Físicas e Digitais:** Artefatos com os quais os usuários e servidores interagem (processos SEI, planilhas paralelas de conferência de teto em Excel, formulários de requerimento e telas do sistema de folha).
2. **Ações do Cidadão (Empregado/Fiscal):** Passos cronológicos do executor: o gatilho da designação, a busca activa pela portaria, o protocolo do requerimento no SEI (no prazo de 30 dias de aditivos) e o monitoramento do contracheque[cite: 1].
3. **Ações de Linha de Frente (Frontstage):** Atendimento e triagem visível pelo RH (conferência documental de recebimento de processos SEI e respostas a dúvidas dos servidores).
4. **Bastidores Operacionais (Backstage - GEPAG/NUPAG):** A complexa validação manual executada pelos gestores de folha de pagamento para aplicar as travas de carência (a partir do 4º contrato), o limite de dispensa de licitação por tipo de contrato, o cálculo milimétrico de proporcionalidade por dias de afastamento (férias, licenças) e a trava do teto cumulativo (R$ 3.410,93)[cite: 1].
5. **Processos de Suporte:** Sistemas estruturantes de ERP/Folha, bancos de dados das diretorias técnicas que gerenciam os saldos contratuais, e canais de publicações oficiais.

## Identificação de Pontos de Falha (Fail Points) e Gambiarras
O prompt gerado deve exigir explicitamente que a IA identifique falhas de comunicação entre os setores de contratos e o RH, riscos críticos de erro humano decorrentes dos cálculos manuais de folha, e o uso de "gambiarras" operacionais (controles em planilhas fora do sistema oficial) criadas para evitar inconformidades e fraudes de cumulação proibida.

Gere o prompt final estruturado contendo personas, escopo analítico, a identificação explícita do órgão e da unidade responsável, o mapeamento obrigatório dos canais de atendimento (SEI, e-mail institucional, presencial e canais de publicação), os normativos aplicáveis de citação obrigatória (ACT 2025/2027 — Cláusula Décima, Lei nº 13.303/2016 e RIC/Terracap) e critérios de sucesso claros.
