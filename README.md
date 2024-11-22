
# 📊 Extração de Dados com do Siconfi com Python

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python) ![Siconfi](https://img.shields.io/badge/Siconfi-Data_Transparency-blue?style=for-the-badge)

## 📋 Descrição do Projeto

Este projeto utiliza a biblioteca **Siconfipy** para extrair dados diretamente do **Tesouro Nacional - Siconfi**  com Python, facilitando o processo de coleta e manipulação de dados para análises mais rápidas e eficazes. Com ele, você poderá acessar dados do tesouro diretamente da API através da biblioteca **Siconfipy** e integrá-los ao **Pandas** para análises de dados.

---

## 📦 Requisitos de Instalação

Para rodar o projeto, você precisará ter **Python 3.x** instalado. Instale as bibliotecas necessárias com:

```bash
pip install siconfipy pandas git+https://github.com/pedrocastroo/siconfipy.git
```

---

## 🛠️ Uso

Para verificar a documentação completa da API do SICONFI, acesse: [API-SICONFI](https://apidatalake.tesouro.gov.br/docs/siconfi/).

E para verificar o projeto completo do Sidrapy, acesse: [PROJETO-SICONFIPY](https://github.com/aspeddro/siconfipy).

### Exemplo de extração de tabela

```python
import pandas as pd
from siconfipy import get_fiscal, get_budget, br_cods

Iremos extraír básicamentes duas bases do tesouro: Relatório de Gestão Fiscal (RGF) e o Relatório Resumido da Execução Orçamentária (RREO)

Caso haja alguma dúvida referente aos parâmetros, utilize:

- help(get_fiscal) # Para verificar os parâmetros do RGF
- help(get_budget) # Para verificar os parâmetros do RREO


Um exemplo de extração do RGF

df_fiscal = get_fiscal(year=2023, # Ano de escolha 
                       period=[1,2,3], # Os períodos
                       cod=27) # Código do Estado

agora um exemplo de extração do RREO

df_orcamentario = get_budget(year=2023, # Ano de escolha
                       period=[1,2,3,4,5,6], # Os períodos
                       cod=27) # Código do IBGE


*Referemte ao parâmetro "period"*: O RGF possuí uma periodicidade quadrimestral, então a escolha será realizada entre um dos três ou os três quadrimestres do ano correspondente. Já o RREO, possuí sua periocidade bimestral, podendo optar entre um dos bimestres, ou todos.

Um exemplo da visualização atual:

print(df_fiscal.head())
print(df_orcamentario.head())
```


### Parâmetros Principais

Ainda é possível realizar mais filtros:

- **annex**: Qual anexo do relatório será filtrado.
- **power**: Qual poder será filtrado.

---

## 📈 Análise e Manipulação com Pandas

Com os dados extraídos no DataFrame, você pode realizar várias operações de análise e visualização.
Caso precise de um tutorial, acesse meu Medium, escrevi uma matéria lá.

- [Documentação Sidrapy](https://medium.com/@falkzera/extra%C3%A7%C3%A3o-de-dados-do-sidra-com-python-40fd7d3a0ff5)

---

## 🤝 Contribuições

Contribuições são bem-vindas! Para reportar problemas ou sugerir melhorias, por favor, abra uma _issue_ ou envie um _pull request_.

---

## 📝 Licença

Este projeto é distribuído sob a licença MIT.
