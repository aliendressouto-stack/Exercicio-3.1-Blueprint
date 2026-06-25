# Diagrama AS-IS — Concessão de Ajuda de Custo (Terracap)

```mermaid
flowchart TD
    %% Estilos de Nós
    classDef ator fill:#2b5c8f,stroke:#1a365d,stroke-width:2px,color:#fff;
    classDef sistema fill:#f4f5f7,stroke:#cbd5e1,stroke-width:1px,color:#334155;
    classDef fail fill:#fee2e2,stroke:#ef4444,stroke-width:2px,color:#991b1b;
    classDef artefato fill:#fef08a,stroke:#eab308,stroke-width:1px,color:#713f12;

    %% Atores e Componentes
    Emp([Empregado / Executor]):::ator
    NUPAG[Analista do NUPAG]:::ator
    SEI[(Sistema SEI)]:::sistema
    ERP[(ERP de Folha - Cego)]:::sistema
    Planilha{Planilha Excel de Controle}:::artefato
    PreFolha[Consulta Prévia do Contracheque]:::artefato

    %% Fluxo Cronológico - Etapa 1 e 2
    Emp -->|1. Identifica Designação| SEI
    Emp -->|2. Compila Lista de Contratos| Emp
    Emp -->|3. Protocolar Requerimento < 30 dias| SEI
    SEI -->|4. Envia Processo| NUPAG

    %% Etapa 3: Backstage Analítico (Caixa-Preta)
    subgraph Backstage [Processamento e Análise Analítica - NUPAG]
        NUPAG -->|5. Executa Triagem Documental| SEI
        NUPAG -.->|6. Consulta manual de vigência| Planilha
        NUPAG -.->|7. Aplica Trava do 4º Contrato| Planilha
        Planilha -.->|⚠ Falha de Baixa de Contrato Encerrado| FP2[/Fail Point 2: Erro manual infla carência/]:::fail
    end

    %% Etapa 4: Homologação e Pré-Folha
    NUPAG -->|8. Emite Despacho de Resposta| SEI
    NUPAG -->|9. Lança comandos manuais| ERP
    ERP -->|10. Gera fotografia de competência| PreFolha
    PreFolha -->|11. Abre janela visual| Emp

    %% Validação e Assimetria do Erário (Fail Point 6)
    subgraph Auditoria [Mecânica da Linha de Defesa]
        Emp -->|12. Audita Consulta Prévia| PreFolha
        PreFolha -->|Identifica Subpagamento| Reclama[Empregado reclama via e-mail]
        Reclama -->|Gera Retrabalho| NUPAG
        PreFolha -->|Identifica Superpagamento| Silencio[Silêncio Administrativo]
        Silencio -.->|Protege o bolso / Cego ao Erário| FP6[/Fail Point 6: Desproteção do Erário/]:::fail
    end

    %% Etapa 5: Fechamento e Suporte
    NUPAG -->|13. Consolida e fecha folha| ERP
    ERP -->|14. Emite Contracheque Definitivo| Emp
    Emp -.->|15. Em caso de dúvidas residuais| Atendimento[Atendimento Presencial no NUPAG]
    Atendimento -.->|16. Abre na tela para auditoria direta| Planilha

    %% Relação com a AUDIT
    AUDIT([Controladoria Interna]):::ator
    AUDIT -.->|Ausente há 10 anos| Atendimento