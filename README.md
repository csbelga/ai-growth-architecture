Sistema de IA para growth: arquitetura conceitual (2ª geração)

Sistema proprietário em produção que executa growth de ponta a ponta para negócios high-ticket: diagnóstico de conta e funil, arquitetura de funil, estratégia de conteúdo, copy, tracking e preparação de decisão de investimento. Este repositório documenta a arquitetura conceitual e as decisões de engenharia. O código é fechado por operar clientes reais.

Por que uma segunda geração

A primeira geração, documentada anteriormente aqui, era um agente 24/7 em VPS: orquestração de três modelos, memória vetorial, pipelines agendados. Uma auditoria interna de resultados concluiu que boa parte do pipeline rodava sem produzir decisão melhor. Infraestrutura ocupada não é inteligência. O sistema foi desativado e reconstruído do zero sobre um princípio diferente: menos infraestrutura, mais verificação.

Princípios da arquitetura atual

Capacidades versionadas. Cada capacidade de growth (arquitetura de funil, conteúdo, copy, tracking, auditoria) é um método explícito, versionado em Git, com fronteiras definidas contra as capacidades vizinhas. O sistema não é um prompt gigante: é uma malha de capacidades com roteamento entre elas.

Qualidade por gates binários. Nenhum entregável sai sem passar por um gate de verificação binário, específico da capacidade. Critério de qualidade vira item objetivo que passa ou reprova, não opinião.

Execução e auditoria independentes. Quem constrói não é quem verifica. Mudanças relevantes passam por um executor cego aos critérios de aceite e um auditor independente que valida contra a especificação. Inconsistência bloqueia a entrega.

Conhecimento de domínio é dado, não código. O método é agnóstico de setor. O que muda por nicho e por cliente entra como configuração. Trocar o setor não muda a arquitetura.

Procedência epistêmica obrigatória. Toda afirmação sobre jornada ou comportamento de cliente carrega marcador de hipótese ou de dado medido. O sistema não afirma o que não mediu.

Autonomia calibrada por reversibilidade. O sistema pesquisa, constrói e se autoverifica sozinho no que é interno e reversível. Ações externas irreversíveis (gastar verba, publicar, contatar terceiros) exigem aprovação humana, com transparência de processo, achados e custo em cada entrega.

Validação contra o real. Nenhuma capacidade é considerada estável até ser validada em cliente real. Método que só funciona em teoria é hipótese, não capacidade.

Stack

Claude (Anthropic) via Claude Code · MCP (Model Context Protocol) para integrações com Meta, Google, Drive e ferramentas de SEO · Git como registro de decisão · PowerShell e Python na infraestrutura local.

Status

Em produção, operando clientes pagantes em verticais high-ticket, com cada cliente novo validando e refinando capacidades existentes.

Contato: csbelga@gmail.com · LinkedIn
