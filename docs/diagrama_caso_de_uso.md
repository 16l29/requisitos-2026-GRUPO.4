graph LR
    %% Atores Principais (Usuários)
    subgraph Atores ["Usuários"]
        Estudante["Estudante"]
        Professor["Professor do ENADE"]
        Coordenação["Coordenação do Curso"]
    end

    %% Fronteira do Sistema (Casos de Uso)
    subgraph Sistema ["Fronteira do Sistema: Aplicativo Auxiliar ENADE"]
        UC1([UC1: Buscar Questões com Busca Avançada])
        UC2([UC2: Visualizar Resoluções via Mapas Mentais])
        UC3([UC3: Realizar Simulados Cronometrados])
        UC4([UC4: Participar do Fórum de Debate por Questão])
        UC5([UC5: Acessar Painel de Gerenciamento e Análise])
    end

    %% Atores Secundários (Sistemas Externos / Integrações)
    subgraph Externo ["Sistemas Externos"]
        INEP["INEP (Base Histórica ENADE)"]
        SisAcad["Sistema Acadêmico (Universidade)"]
    end

    %% Associações do Estudante
    Estudante --> UC1
    Estudante --> UC2
    Estudante --> UC3
    Estudante --> UC4

    %% Associações do Professor
    Professor --> UC4
    Professor --> UC5

    %% Associações da Coordenação
    Coordenação --> UC5

    %% Associações com Sistemas Externos (Inclusões/Dependências de Dados)
    UC1 -. Ingestão de Dados .-> INEP
    UC5 -. Autenticação e Vínculo .-> SisAcad