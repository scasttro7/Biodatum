# 🌿 Caderno de Exercícios — Do zero ao avançado

Aprenda Python fazendo ciência florestal, usando os mesmos conceitos que sustentam a plataforma BIODATUM.

**Como usar este guia:**

* Leia a explicação antes de tentar cada exercício
* Tente **modificar** os valores e ver o que muda
* Cada exercício tem uma tarefa pra você completar sozinha
* Não existe resposta errada — existe aprendizado 🌱

## 📘 Nível 1 — Python Básico

### Variáveis e cálculos simples

Em Python, você guarda um valor numa **variável** assim: `nome = valor`. É como dar um nome a um número pra usar depois.

**🎯 Exercício 1** — Crie uma variável chamada `altura` com o valor `32` (metros) e imprima uma frase dizendo a altura da árvore.

### Listas — vários valores juntos

Uma **lista** guarda vários valores de uma vez. Pense nela como uma coluna de planilha.

**🎯 Exercício 2** — Crie uma lista chamada `especies` com os nomes de 4 espécies amazônicas que você conhece. Depois imprima quantas espécies estão na lista.

### Funções — seu bloco de cálculo reutilizável

Uma **função** é um bloco de código que você escreve uma vez e usa quantas vezes quiser. No BIODATUM, `estimar_biomassa()` e `calcular_irfa()` são funções.

**🎯 Exercício 3** — Crie uma função chamada `metros_para_cm` que converte altura de metros para centímetros. Teste com `32` metros.

## 📗 Nível 2 — NumPy

### Cálculos científicos rápidos

**NumPy** é a biblioteca de matemática do Python. Ela faz cálculos em listas inteiras de uma vez — como aplicar uma fórmula pra uma coluna inteira de planilha.

**🎯 Exercício 4 — A equação de Higuchi na mão**

Calcule a biomassa de uma árvore passo a passo:

```
AGB = exp(-1.499 + 2.148*ln(DAP) + 0.207*ln(DAP)² - 0.0281*ln(DAP)³)
```

Use `dap = 100` e preencha cada etapa. Veja a fórmula completa em [Estimativa de Biomassa — Protocolo Higuchi](../metodologia/biomassa-higuchi.md).

## 📙 Nível 3 — Pandas

### Trabalhando com tabelas

**Pandas** é o Excel do Python. Você cria tabelas (chamadas de `DataFrame`) e faz filtros, cálculos e agrupamentos.

**🎯 Exercício 5** — Adicione mais 3 árvores à tabela `parcela` e calcule qual espécie tem a **maior biomassa média** entre todas.

## 📒 Nível 4 — Matplotlib

### Criando seus próprios gráficos

**🎯 Exercício 6** — Crie um gráfico de **dispersão** (scatter plot) mostrando a relação entre `altura_m` e `dap_cm` das árvores da parcela. Adicione título e rótulos nos eixos.

## 🔴 Nível 5 — IRFA na prática

### Mexendo nos pesos e cenários

**🎯 Exercício Final — Crie sua própria parcela**

Monte uma parcela florestal com dados que você imaginar (ou pesquisar). Calcule:

1. Biomassa de cada árvore
2. IRFA da parcela (invente valores de TNR, TRB, IEC — veja [Índice de Resiliência Florestal Amazônica (IRFA)](../metodologia/indice-irfa.md))
3. Um gráfico mostrando os resultados

Não precisa estar "certo" — o objetivo é você criar do zero!

## 🏁 Parabéns!

Se você chegou até aqui, você já sabe:

* ✅ Criar variáveis e listas em Python
* ✅ Escrever funções reutilizáveis
* ✅ Usar NumPy para cálculos científicos
* ✅ Criar e filtrar tabelas com Pandas
* ✅ Fazer gráficos com Matplotlib
* ✅ Aplicar e modificar as equações do BIODATUM

**Próximos passos sugeridos:**

* Importar dados reais de campo (CSV) com `pd.read_csv()`
* Conectar com dados do PRODES/INPE
* Explorar mapas com a biblioteca `geopandas`

*BIODATUM — PPGCASA/UFAM, 2026* 🌿
