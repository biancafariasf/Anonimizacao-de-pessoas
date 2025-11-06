import pandas as pd
import hashlib
import random
from faker import Faker

# Inicializa gerador de dados fictícios
fake = Faker('pt_BR')

# Gera dados simulados
def gerar_dados(qtd=10):
    dados = []
    for _ in range(qtd):
        nome = fake.name()
        idade = random.randint(18, 80)
        imposto_renda = round(random.uniform(10000, 100000), 2)
        dados.append({'nome': nome, 'idade': idade, 'imposto_renda': imposto_renda})
    return pd.DataFrame(dados)

# Função para anonimizar nome com SHA-256
def hash_nome(nome):
    return hashlib.sha256(nome.encode()).hexdigest()

# Função para generalizar idade por faixa
def generalizar_idade(idade):
    return f"{(idade // 10) * 10}s"

# Função para perturbar imposto de renda
def perturbar_renda(renda):
    ruido = random.uniform(-500, 500)
    return round(renda + ruido, 2)

# Gera e exibe dados originais
df_original = gerar_dados(10)
print("🔍 Dados identificáveis:")
print(df_original)

# Aplica anonimização
df_anonimizado = df_original.copy()
df_anonimizado['nome'] = df_anonimizado['nome'].apply(hash_nome)
df_anonimizado['idade'] = df_anonimizado['idade'].apply(generalizar_idade)
df_anonimizado['imposto_renda'] = df_anonimizado['imposto_renda'].apply(perturbar_renda)

# Exibe dados anonimizados
print("\n✅ Dados anonimizados:")
print(df_anonimizado)

print(df)
