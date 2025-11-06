# Anonimizacao-de-pessoas
# 🔐 Projeto: Anonimização de Dados com Machine Learning

## 🧠 Visão Geral

Este projeto demonstra, de forma prática, como dados pessoais sensíveis podem ser utilizados para identificar indivíduos — e, mais importante ainda, como podemos **proteger essas informações** por meio de **técnicas de anonimização** e **aprendizado de máquina (ML)**.

---

## 🎯 Objetivo

1. **Parte 1 – Identificação**  
   Criar um modelo simples que, com base em dados como **nome**, **idade** e **imposto de renda**, consiga identificar pessoas.

2. **Parte 2 – Anonimização**  
   Aplicar técnicas como **hashing**, **generalização** e **perturbação de dados** para tornar impossível a reidentificação dos mesmos indivíduos.

---

## 🛠️ Tecnologias Utilizadas

- Python 3.10+
- Pandas
- Scikit-learn
- Faker (para gerar dados fictícios)
- hashlib (para anonimização via hash)

---

## 📦 Estrutura do Projeto


---

## 🧪 Etapa 1: Identificação

```python
# identificacao.py
import pandas as pd

# Carrega os dados
df = pd.read_csv('dados/base_simulada.csv')

# Exibe os dados sensíveis
print("🔍 Dados sensíveis identificáveis:")
print(df[['nome', 'idade', 'imposto_renda']])
# anonimiza.py
import pandas as pd
import hashlib

# Função para anonimizar nomes
def hash_nome(nome):
    return hashlib.sha256(nome.encode()).hexdigest()

# Carrega os dados
df = pd.read_csv('dados/base_simulada.csv')

# Aplica anonimização
df['nome'] = df['nome'].apply(hash_nome)
df['idade'] = df['idade'].apply(lambda x: f"{(x//10)*10}s")  # Generalização por faixa etária
df['imposto_renda'] = df['imposto_renda'] + 500 * (0.5 - pd.np.random.rand(len(df)))  # Perturbação

# Exibe dados anonimizados
print("✅ Dados anonimizados:")
print(df)
