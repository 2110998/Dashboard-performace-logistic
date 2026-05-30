# Dashboard de Performance Logística (SLA)

Análise de dados corporativa desenvolvida no Power BI integrada a uma base de dados em nuvem, focada no monitoramento de prazos de entrega (SLA) e volumetria por região.

## 📊 O Dashboard

<img width="961" height="509" alt="Dashboard-log 1" src="https://github.com/user-attachments/assets/c3c4e28e-9157-4426-8203-d5daade3d840" />

---

## 🛠️ Tecnologias e Ferramentas Utilizadas
* **Power BI Desktop** (Construção dos visuais e relatórios)
* **Power Query** (Processo de ETL, tratamento e modelagem de dados)
* **M Language** (Criação de colunas personalizadas e conversão de tipos)
* **Google Sheets API** (Integração de dados direto da nuvem via Web)

---

## ⚙️ Processo de Desenvolvimento (ETL)

1. **Extração:** Conexão direta via protocolo Web com uma base de dados dinâmica hospedada no Google Sheets.
2. **Transformação e Tratamento:** 
   * Resolução de erros de conexão HTTP (404) e ajuste de níveis de privacidade/credenciais para acesso à API pública.
   * Tratamento de tipos de dados de tempo/duração para formato Inteiro no Power Query.
   * Criação de coluna calculada personalizada utilizando a lógica de negócio: `[Data_Entrega] - [Data_Pedido]` para metrificar o tempo real de tráfego.
3. **Carga e Modelagem:** Estruturação dos dados limpos para consumo direto na interface do Power BI.

---

## 📈 Insights Gerados de Negócio

O painel foi estruturado para cruzar a volumetria de entregas com o tempo médio de SLA, gerando as seguintes conclusões gerenciais:
* **Média Geral de Entrega:** O indicador macro (cartão) aponta um SLA estável de **3,50 dias** para a operação geral.
* **Concentração de Mercado:** O gráfico de rosca identificou que **São Paulo (SP)** detém o maior volume da operação, correspondendo a **35% dos pedidos (7 entregas)**, operando com eficiência dentro da média (3,71 dias).
* **Gargalo Crítico Detectado:** O **Rio de Janeiro (RJ)** foi identificado como o principal ponto de atenção. A região representa **25% do volume total da empresa (5 pedidos)**, porém opera com um tempo de tráfego de **9,00 dias** (quase o dobro da média geral).

> **Ação Recomendada:** Direcionar esforços operacionais e auditoria de transportadoras especificamente na rota do Rio de Janeiro, visto que o gargalo impacta diretamente 1/4 dos clientes da empresa.
