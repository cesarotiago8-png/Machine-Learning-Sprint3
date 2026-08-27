# 🚜 Prevenção de Sinistros em Equipamentos Agrícolas (Projeto SOMPO)

**Disciplina:** Machine Learning (Sprint 3)  
**Equipe Oasis:** Adalberto Alves Cruz, Bruno Henrique Ferreira Ambrosio, Gustavo da Silva Nascimento, Lucas Maximo dos Santos, Renan de Assis Rodrigues, Tiago Thomaz Cesaro.

---

## 🎯 Objetivo do Projeto
Este projeto visa desenvolver, validar e otimizar modelos de Machine Learning (Classificação) para prever o risco de sinistros em máquinas agrícolas. A solução foi desenhada para apoiar as decisões estratégicas da seguradora **SOMPO**, reduzindo prejuízos financeiros e operacionais causados por quebras e acidentes no campo.

## ⚙️ Metodologia e Preparação de Dados
A base de dados foi gerada simulando condições reais de operação no agronegócio e passou pelas seguintes etapas:
* **Engenharia de Regras:** Variável alvo (`risco_sinistro`) criada com base em temperatura, horas de uso contínuo, proximidade de água e tipo de terreno, incluindo 5% de ruído aleatório para evitar overfitting.
* **One-Hot Encoding (OHE):** Transformação de variáveis categóricas em numéricas binárias.
* **Scaling:** Padronização das variáveis contínuas (temperatura e horas) usando `StandardScaler`.
* **Holdout:** Divisão dos dados em 80% para treino e 20% para teste (estratificado).

## 🤖 Modelagem e Otimização (Tuning)
Foram treinados e comparados dois modelos de classificação, otimizados através de `GridSearchCV` com validação cruzada (cv=5):
1. **Random Forest (Modelo Escolhido):** Acurácia de 81% e AUC de 0.819 no teste.
2. **K-Nearest Neighbors (KNN):** Acurácia de 82% e AUC de 0.782 no teste.

## 📊 Principais Descobertas e Conclusão
* **Escolha do Modelo:** Apesar do empate técnico em acurácia, o **Random Forest** foi selecionado por apresentar maior *Recall* na classe de sinistro (0.40 vs 0.33) e maior AUC. Em seguros, minimizar falsos negativos (deixar passar um sinistro) é prioridade máxima.
* **Feature Importance:** A **Temperatura do Motor (65.3%)** e as **Horas de Uso Contínuo (20.1%)** foram identificadas como os maiores causadores de sinistros.
* **Recomendação:** Implementação de monitoramento IoT para temperatura e adoção de pausas programadas para o maquinário.

## 🛠️ Tecnologias Utilizadas
* Python 3
* Pandas & NumPy (Manipulação de Dados)
* Scikit-Learn (Machine Learning & Tuning)
* Matplotlib & Seaborn (Visualização de Dados)
