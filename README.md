# API-Hunter-CI

## Descrição

O **API-Hunter-CI** é um projeto de estudo que demonstra a automação de testes de API e integração contínua utilizando Postman, Newman e GitHub Actions. O objetivo é garantir a eficiência e precisão dos testes de API por meio de uma pipeline de CI que executa testes automaticamente e gera relatórios detalhados.

## Funcionalidades

- **Automatização de Testes de API:** Testes automatizados para criar, atualizar e excluir leads, utilizando Postman e Newman.
- **Integração Contínua:** Pipeline de CI configurada no GitHub Actions para executar testes automaticamente em cada commit ou pull request.
- **Relatórios HTML:** Relatórios detalhados gerados após o build, proporcionando uma visão clara dos resultados dos testes.

## Workflow do GitHub Actions

O workflow do GitHub Actions é configurado para realizar as seguintes etapas:

1. **Checkout do Repositório:** Clona o repositório no runner para acesso aos arquivos necessários.
2. **Verificação de Versão:** Confirma as versões do Newman e do Node para garantir compatibilidade.
3. **Instalação do Newman-Reporter-HTML:** Instala o reporter HTML do Newman para a geração de relatórios.
4. **Execução da Coleção de Testes:** Roda os testes da coleção do Postman e gera um relatório HTML com os resultados.
5. **Arquivo de Artefatos:** Faz upload do relatório HTML gerado como artefato do workflow.

## Como Usar

1. **Clone o Repositório:**
   ```bash
   git clone https://github.com/seu-usuario/API-Hunter-CI.git
   cd API-Hunter-CI
   
 2. **Instale Dependências:**
  *Certifique-se de ter o Newman instalado globalmente:*
    ```npm install -g newman newman-reporter-html```

**3. Execute os Testes Localmente:**
  ```newman run -d dados-leads.json ./api_hunter.json -e ./api_hunter-env.json --reporters cli,html --reporter-html-template ./htmlreqres.hbs --reporter-html-export ./result/report.html```

**4. Verifique os Relatórios:**
````O relatório HTML gerado estará disponível em ./result/report.html.````
