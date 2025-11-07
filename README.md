# 🔐 Projeto: Anonimização de Dados com Machine Learning

## 🧠 Visão Geral

Este projeto demonstra como dados pessoais sensíveis — como nome, idade e imposto de renda — podem ser utilizados para identificar indivíduos. Em seguida, aplicamos técnicas de **anonimização** para garantir que essas pessoas não possam mais ser reidentificadas, mesmo com os mesmos dados. Tudo isso é feito com apoio de **Machine Learning** e boas práticas de privacidade.

---

## 🎯 Objetivos

- **Etapa 1 – Identificação:**  
  Criar um código que, com base em dados como nome, idade e imposto de renda, consegue identificar pessoas.

- **Etapa 2 – Anonimização:**  
  Desenvolver um segundo código que transforma esses dados, aplicando técnicas como **hashing**, **generalização** e **perturbação**, tornando impossível identificar os mesmos indivíduos.

---

## 🛠️ Tecnologias Utilizadas

Este projeto foi pensado para funcionar com o mínimo de dependências externas. A versão simples usa apenas recursos nativos do Python. A versão completa pode incluir:

- Python 3.10+
- Pandas
- Faker (para gerar dados fictícios)
- hashlib
- Scikit-learn (opcional para modelos de ML)

---

## 📦 Estrutura do Projeto

anonimizacao-ml/ ├── dados/ │ └── base_simulada.csv ├── identificacao.py ├── anonimiza.py ├── README.md


---

## 📚 Conceitos Aplicados

- **Identificação de indivíduos com dados sensíveis**
- **Anonimização via hash e generalização**
- **Perturbação de dados para evitar reidentificação**
- **Privacidade e ética em ciência de dados**
- **Preparação para uso de Machine Learning com dados protegidos**

---

## 💡 Próximos Passos

- Treinar modelos de ML com dados anonimizados
- Avaliar impacto da anonimização na acurácia dos modelos
- Explorar técnicas avançadas como **differential privacy**

---

## 👩‍💻 Autoria

Projeto desenvolvido por Bianca, com apoio de inteligência artificial para documentação e estruturação.

