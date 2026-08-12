# Artefato Preditivo para Estimativa Mensal de Atendimentos da PSR nos Centros POP

Artefato preditivo para a estimativa mensal de atendimentos da População em Situação de Rua (PSR) nos Centros POP, incorporando indicadores socioeconômicos e conjunturais (PIB, IDHM, IPCA e Desemprego).

---

## 📌 Visão Geral do Projeto

Este repositório contém a base de dados em painel, os scripts de tratamento/modelagem e a documentação técnica para a criação de um artefato preditivo voltado à gestão socioassistencial. O objetivo é estimar a demanda mensal de atendimentos da População em Situação de Rua (PSR) nos Centros POP de todo o Brasil para a série temporal de **2017 a 2025**.

---

## 📂 Estrutura do Repositório

```text
artefato-previsao-psr/
│
├── README.md                  <- Documentação e apresentação do projeto
│
└── data/
    ├── raw/                   <- Bases de dados brutas e originais (MDS, IBGE, IPEA)
    └── processed/             <- Base de dados master unificada para modelagem
