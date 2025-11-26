# Simulação de Epidemias: Dinâmica SIS em Redes Complexas

---

### Integrantes:
- João Gabriel
- Vinicius Nascimento
- Guilherme Buss

### Curso:
- Ciência de Redes - Prof. Moacyr Silva

---

## Introdução e Objetivos

Este trabalho tem como objetivo explorar a dinâmica de propagação de doenças em redes complexas através de simulações numéricas do modelo **SIS (Suscetível-Infectado-Suscetível)**, onde nosso código tenta observar como a topologia da rede de contatos influencia a sobrevivência ou extinção de uma epidemia.

## Metodologia Experimental

As simulações foram realizadas utilizando a biblioteca `NetworkX` para modelagem dos grafos. Para cada cenário, executamos múltiplas iterações para obter o comportamento médio da epidemia e mitigar flutuações estocásticas.

### Questão 1: Redes Aleatórias
Nesta etapa, utilizamos uma rede **Erdős-Rényi (ER)** com $N=10.000$ vértices e grau médio $\langle k \rangle = 20$. 

O foco é validar a teoria de campo médio, verificando se a doença se fixa na rede ou é extinta com base no **Número Básico de Reprodução** ($R_0$). Variamos a taxa de recuperação ($\mu$) mantendo a infecciosidade ($\beta$) fixa para observar três regimes distintos:
* **Regime Supercrítico ($R_0 > 1$):** Espera-se um estado endêmico.
* **Regime Crítico ($R_0 \approx 1$):** Transição de fase.
* **Regime Subcrítico ($R_0 < 1$):** Extinção da doença.

### Questão 2: Redes Livres de Escala
Aqui, substituímos a topologia por uma rede **Livre de Escala (Scale-Free)**, caracterizada por uma distribuição de graus lei de potência.

O objetivo é analisar como a presença de nós extremamente conectados altera a dinâmica de propagação em comparação com a rede aleatória do experimento anterior. Investigamos se a heterogeneidade da rede facilita a persistência da doença mesmo sob parâmetros de cura mais agressivos.

### Questão 3: Estratégias de Imunização
Na etapa final, exploramos métodos para impedir a fixação do estado endêmico através da imunização prévia (vacinação) de uma fração da rede. Comparamos três estratégias distintas:

1.  **Imunização Aleatória:** Vacinação de nós ao acaso.
2.  **Imunização Direcionada (Targeted):** Vacinação focada nos nós de maior grau (hubs).
3.  **Imunização de Vizinhos:** Vacinação baseada na exploração da rede (vizinhos de nós aleatórios).

---
