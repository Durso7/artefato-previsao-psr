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

🏛️ Metodologia e Fontes de Dados
Para a construção do painel, foram consolidadas informações operacionais do Serviço Especializado para Pessoas em Situação de Rua, dados de capacidade/infraestrutura dos Centros POP e variáveis de contexto socioeconômico:

1. Registro Mensal de Atendimento (RMA - 2017 a 2025)
Dados oficiais de atendimento coletados na página oficial da Vigilância Socioassistencial do Ministério do Desenvolvimento e Assistência Social, Família e Combate à Fome (MDS):

2017: https://aplicacoes.mds.gov.br/sagi/dicivip_datain/ckfinder/userfiles/files/RMA_Centro_POP_Criterios_2017_divulga%C3%A7%C3%A3o(1).xlsx

2018: https://aplicacoes.mds.gov.br/sagi/dicivip_datain/ckfinder/userfiles/files/RMA_Centro_POP_Criterios_2018_divulga%C3%A7%C3%A3o(1).xlsx

2019: https://aplicacoes.mds.gov.br/sagi/dicivip_datain/ckfinder/userfiles/files/RMA_Centro_POP_Criterios_2019_divulga%C3%A7%C3%A3o(1).xlsx

2020: https://aplicacoes.mds.gov.br/sagi/dicivip_datain/ckfinder/userfiles/files/RMA_Centro_POP_Criterios_2020_divulga%C3%A7%C3%A3o(1).xlsx

2021: https://aplicacoes.mds.gov.br/sagi/dicivip_datain/ckfinder/userfiles/files/RMA_Centro_POP_Criterios_2021_divulga%C3%A7%C3%A3o(1).xlsx

2022: https://aplicacoes.mds.gov.br/sagi/dicivip_datain/ckfinder/userfiles/files/RMA_Centro_POP_Criterios_2022_divulga%C3%A7%C3%A3o_24_03_23(2).xlsx

2023: https://aplicacoes.mds.gov.br/sagi/dicivip_datain/ckfinder/userfiles/files/RMA_Centro_POP_Criterios_2023_divulga%C3%A7%C3%A3o_130324(2).xlsx

2024: https://aplicacoes.mds.gov.br/sagi/dicivip_datain/ckfinder/userfiles/files/RMA_Centro_POP_Criterios_2024_divulga%C3%A7%C3%A3o_100325(1).xlsx

2025: https://aplicacoes.mds.gov.br/sagi/dicivip_datain/ckfinder/userfiles/files/RMA_Centro_POP_Criterios_2025_divulgacao_150526.xlsx

2. Informações dos Centros POP / Censo SUAS (2018 a 2024)
Dados de gestão, localização e infraestrutura física coletados no portal do MDS:

2018: https://aplicacoes.mds.gov.br/sagi/dicivip_datain/ckfinder/userfiles/files/4_Centro%20POP.zip

2019: https://aplicacoes.mds.gov.br/sagi/dicivip_datain/ckfinder/userfiles/files/Centro%20POP(2).zip

2020: https://aplicacoes.mds.gov.br/sagi/dicivip_datain/ckfinder/userfiles/files/3_CENTRO_POP_2020.zip

2021: https://aplicacoes.mds.gov.br/sagi/dicivip_datain/ckfinder/userfiles/files/3%20-%20CENTRO%20POP.zip

2022: https://aplicacoes.mds.gov.br/sagi/dicivip_datain/ckfinder/userfiles/files/3%20-%20CENTRO%20POP.rar

2023: https://aplicacoes.mds.gov.br/sagi/dicivip_datain/ckfinder/userfiles/files/3%20-%20CENTRO%20POP(1).rar

2024: https://aplicacoes.mds.gov.br/sagi/dicivip_datain/ckfinder/userfiles/files/3_CENTRO%20POP(5).rar

3. Indicadores Socioeconômicos e Conjunturais
Produto Interno Bruto Municipal (PIB): Tabela 5938 do IBGE. Fonte: https://sidra.ibge.gov.br/tabela/5938

Índice de Desenvolvimento Humano Municipal (IDHM): Atlas do Desenvolvimento Humano no Brasil (PNUD/IPEA/FJP - Censo 2010). Fonte: https://basedosdados.org/dataset/cbfc7253-089b-44e2-8825-755e1419efc8?table=ec5fb3d1-fa98-4ab3-8a02-4b9950048a83

Inflação (IPCA): Variação anual acumulada do IPCA (IBGE - Tabela 1737). Fonte: https://sidra.ibge.gov.br/tabela/1737

Taxa de Desocupação: Média anual por Unidade da Federação extraída da PNAD Contínua (IBGE - Tabela 4099). Fonte: https://sidra.ibge.gov.br/tabela/4099

🛠️ Processamento e Consolidação dos Dados
Tratamento do RMA: Utilizou-se a "Base tratada" dos relatórios anuais. O Bloco I manteve padrão de nomenclatura ao longo de toda a série (2017 a 2025). Do Bloco II, mantiveram-se apenas a População Total e o Porte Municipal, ajustando as variáveis para a transição entre o Censo 2010 (2017 a 2022) e o Censo 2022 (2023 a 2025).

Capacidade Física e Geolocalização: Na ausência de um indicador direto de capacidade nominal, estimou-se a capacidade física simultânea indireta multiplicando-se a quantidade de salas pelas faixas de lotação declaradas no Censo SUAS. As coordenadas geográficas (latitude e longitude) também foram anexadas.

Unificação Municipal: O código IBGE do município (codigo_ibge) e o ano (ano) conectam a base do RMA ao PIB e ao IDHM.

Unificação Estadual/Nacional: A sigla da Unidade da Federação (uf) e o ano (ano) conectam a Taxa de Desocupação e a Inflação.
