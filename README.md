# ⚡ Performance Testing with JMeter

Projeto de **testes de performance utilizando Apache JMeter**, desenvolvido durante minha formação em Quality Assurance pela EBAC.

O objetivo deste projeto é simular múltiplos usuários realizando buscas simultaneamente em uma aplicação Web, utilizando massa de dados externa e analisando o comportamento da aplicação durante a execução.

## 🎯 Objetivo

Construir e executar um cenário de teste de performance utilizando o JMeter, trabalhando conceitos como:

- Simulação de múltiplos usuários;
- Configuração de Thread Groups;
- Ramp-up de usuários;
- Requisições HTTP;
- Parametrização de dados;
- Massa de testes externa com CSV;
- Think Time entre requisições;
- Análise dos resultados da execução.

## 🧪 Cenário de teste

O plano de testes simula usuários realizando pesquisas no YouTube.

### Configuração utilizada

| Parâmetro | Configuração |
|---|---|
| Ferramenta | Apache JMeter 5.6.3 |
| Usuários simultâneos | 20 |
| Ramp-up | 60 segundos |
| Duração configurada | 180 segundos |
| Requisição | HTTP GET |
| Endpoint | `/results` |
| Massa de dados | CSV |
| Think Time | 1 a 3 segundos |

Os termos utilizados nas buscas são carregados dinamicamente através do arquivo `pesquisa.csv`, evitando a utilização de um único valor fixo durante a execução.

## 🔄 Fluxo do teste

```text
Thread Group
     ↓
20 usuários
     ↓
Ramp-up de 60 segundos
     ↓
Leitura da massa de dados CSV
     ↓
Requisição HTTP de busca
     ↓
Think Time aleatório
     ↓
Coleta e análise dos resultados
```

## 📊 Análise de resultados

O plano contém diferentes listeners para acompanhamento da execução:

- View Results Tree;
- View Results in Table;
- Summary Report;
- Transactions per Second.

Esses dados permitem observar métricas relacionadas ao comportamento das requisições durante a execução do teste.

## 📁 Estrutura do projeto

```text
qa-performance-testing-jmeter/
├── data/
│   ├── pesquisa.csv
│   └── pesquisa.xlsx
├── tests/
│   └── youtube-search-performance-test.jmx
└── README.md
```

### Arquivos

- `youtube-search-performance-test.jmx` — plano de testes de performance desenvolvido no JMeter;
- `pesquisa.csv` — massa de dados utilizada dinamicamente durante a execução;
- `pesquisa.xlsx` — versão da massa de dados utilizada para organização e conferência.

## 🚀 Executando o projeto

### Pré-requisitos

- Java
- Apache JMeter

### Clone o repositório

```bash
git clone https://github.com/LucasBaccin/qa-performance-testing-jmeter.git
cd qa-performance-testing-jmeter
```

### Execução pela interface do JMeter

1. Abra o Apache JMeter;
2. Acesse `File > Open`;
3. Selecione:

```text
tests/youtube-search-performance-test.jmx
```

4. Confira se o CSV Data Set Config está utilizando a massa de dados do projeto;
5. Execute o Test Plan;
6. Analise os resultados através dos listeners configurados.

## 📈 Métricas observadas

Durante a execução, o plano permite acompanhar informações relacionadas a:

- Quantidade de requisições executadas;
- Tempo de resposta;
- Throughput;
- Erros durante a execução;
- Transactions per Second;
- Comportamento da aplicação durante a carga simulada.

## 📚 Principais aprendizados

Este projeto permitiu trabalhar conceitos diferentes dos testes funcionais e automatizados presentes nos demais projetos do meu portfólio, incluindo:

- Fundamentos de testes de performance;
- Simulação de carga com múltiplos usuários;
- Configuração de ramp-up e duração dos testes;
- Parametrização de requisições;
- Utilização de massas de dados externas;
- Simulação de intervalos entre ações dos usuários;
- Interpretação de métricas de execução;
- Importância da portabilidade e organização dos arquivos de teste.

## 🔮 Próximas evoluções

- Adicionar assertions para definição de critérios de sucesso;
- Definir critérios objetivos de performance;
- Executar testes em modo não-GUI;
- Gerar relatórios HTML do JMeter;
- Comparar resultados entre diferentes cargas de usuários;
- Registrar resultados de execuções para comparação histórica.

---

### 👨‍💻 Autor

**Lucas Baccin**

Quality Assurance | Test Automation | API Testing | Performance Testing

**Lucas Baccin**

Quality Assurance | Test Automation | API Testing | Performance Testing
