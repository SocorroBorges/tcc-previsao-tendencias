# 📊 Previsão de Tendências com Análise de Dados – Amazon Sales 2025  

![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15-blue?logo=postgresql)
![Metabase](https://img.shields.io/badge/Metabase-Analytics-green?logo=metabase)
![VSCode](https://img.shields.io/badge/VS_Code-IDE-blueviolet?logo=visualstudiocode)
![License](https://img.shields.io/badge/License-Acadêmico-lightgrey)

---

## 🌟 Sobre o Projeto  

Este projeto faz parte do meu **Trabalho de Conclusão de Curso (TCC)** em Ciência da Computação 🌙.  
O objetivo é desenvolver um sistema automatizado de **análise e previsão de tendências de vendas**, utilizando dados reais da **Amazon Sales 2025 (Kaggle)**.  

O protótipo integra **Python, PostgreSQL e Metabase**, criando uma pipeline completa de coleta, transformação e visualização de dados — tudo em um só fluxo automatizado.  

---

## 🚀 Objetivos Principais  

- 📥 Importar dados de vendas do arquivo `sales.csv` (Amazon Sales 2025)  
- 🧮 Realizar tratamento, conversão e limpeza automatizada com **Pandas**  
- 🗃️ Armazenar os dados em um banco **PostgreSQL 15**  
- 📊 Gerar consultas SQL analíticas para identificar tendências  
- 📈 Criar **dashboards interativos no Metabase** com insights em tempo real  

---

## 🧩 Tecnologias Utilizadas  

| Ferramenta | Função |
|-------------|--------|
| 🐍 **Python 3.12** | Automação e tratamento de dados |
| 🐘 **PostgreSQL 15** | Banco de dados relacional |
| 📦 **Pandas / SQLAlchemy** | Processamento e integração com SQL |
| 📊 **Metabase** | Visualização e análise interativa |
| 🧠 **VS Code** | Desenvolvimento e controle de versão |
| 🔗 **Git / GitHub** | Versionamento e portfólio |

---

## ⚙️ Estrutura do Projeto  
```makefile
📂 C:\meu_tcc
│
├── import_csv.py # Script de importação automatizada (Python)
├── consultas_tcc.sql # Consultas SQL usadas no Metabase
├── sales.csv # Dataset (Amazon Sales 2025)
├── imagens
│ ├── figura6_1_receita_mensal.png
│ ├── figura6_2_cancelamentos_regiao.png
│ ├── figura6_3_produtos_vendidos.png
│ ├── figura6_4_metodos_pagamento.png
│ └── figura6_6_dashboard_final.png
```
---

## 🧠 Consultas SQL  

### Receita mensal:
```sql
SELECT DATE_TRUNC('month', date)::date AS mes,
       SUM(total_sales) AS receita_mensal
FROM sales
GROUP BY mes
ORDER BY mes;
```

---

### Cancelamentos por região:
```sql
SELECT customer_location AS regiao,
       COUNT(CASE WHEN status ILIKE 'Cancelled' THEN 1 END) AS cancelados,
       COUNT(CASE WHEN status ILIKE 'Completed' THEN 1 END) AS concluidos,
       ROUND(COUNT(CASE WHEN status ILIKE 'Cancelled' THEN 1 END)::decimal /
             NULLIF(COUNT(*),0) * 100, 2) AS perc_cancelamento
FROM sales
GROUP BY regiao
ORDER BY perc_cancelamento DESC;
```
---

📸 Visualizações
Figura	Descrição
🟣 Figura 6.1	Receita mensal (linha)
🔵 Figura 6.2	Cancelamentos por região (barras)
🟢 Figura 6.3	Produtos mais vendidos (colunas)
🟡 Figura 6.4	Métodos de pagamento (pizza)
🟠 Figura 6.6	Dashboard interativo no Metabase

(As imagens estão na pasta /imagens)

---

🌙 Resultados Parciais

O protótipo mostrou:

Eficiência na limpeza e análise de dados CSV

Dashboards dinâmicos e insights automatizados

Aplicação prática de Python, SQL e ferramentas BI

Integração fluida entre back-end e visualização

---

💫 Próximos Passos

🔮 Adicionar previsão de vendas com Regressão Linear

⚙️ Implementar alertas automáticos no Metabase

📚 Finalizar documentação ABNT e relatório técnico completo

---

👩‍💻 Autora

Maria do Socorro Borges

🎓 Estudante de Ciência da Computação

💻 Apaixonada por dados, tecnologia e criatividade

🌙 “Entre códigos e estrelas, eu analiso o universo dos dados.”

---

 ## 🔗 Meus Perfis

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](www.linkedin.com/in/maria-do-socorro-vieira-borges)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/SocorroBorges)
[![Kaggle](https://img.shields.io/badge/Kaggle-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/mariadosocorroborges)
[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:m.socorro.borges.cc@gmail.com)


⭐ Se este projeto te inspirou, não esquece de deixar uma estrela no repositório!
