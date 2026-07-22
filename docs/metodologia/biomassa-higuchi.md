# Estimativa de Biomassa — Protocolo Higuchi

O **Protocolo Higuchi** (Higuchi et al., 1998) estabelece equações alométricas calibradas especificamente para espécies da Amazônia central. É a base do módulo de estimativa de biomassa aérea (AGB — *Above-Ground Biomass*) da plataforma BIODATUM.

## A equação

$$
AGB = e^{-1{,}499 \;+\; 2{,}148 \cdot \ln(DAP) \;+\; 0{,}207 \cdot [\ln(DAP)]^2 \;-\; 0{,}0281 \cdot [\ln(DAP)]^3}
$$

Onde:

| Termo | Significado |
|---|---|
| **DAP** | Diâmetro à Altura do Peito (cm) |
| **AGB** | Biomassa aérea estimada (Mg/ha) |

> O DAP mínimo válido para esta equação é **10 cm** — o limiar padrão usado em inventários florestais.

## Implementação de referência

```python
def estimar_biomassa(dap):
    """
    Estima a biomassa aérea (AGB) utilizando a equação alométrica do Protocolo Higuchi.
    Referência: Higuchi et al. (1998) — equação calibrada para a Amazônia central.
    """
    dap = np.atleast_1d(np.array(dap, dtype=float))

    if np.any(dap < 10):
        raise ValueError("DAP deve ser ≥ 10 cm. Valores abaixo do limiar não são válidos para esta equação.")

    ln_dap = np.log(dap)

    agb = np.exp(
        -1.499
        + 2.148 * ln_dap
        + 0.207 * ln_dap**2
        - 0.0281 * ln_dap**3
    )

    return agb
```

## Classificação por porte

A plataforma classifica árvores em três faixas com base no DAP:

* **Pequeno** — DAP < 40 cm
* **Médio** — DAP entre 40 e 80 cm
* **Grande** — DAP > 80 cm

## Exemplo de saída

Para uma parcela simulada de 15 árvores (amostra de espécies amazônicas típicas — castanheira, mogno, sumaúma, jatobá, entre outras), o módulo retorna:

* Biomassa total e média da parcela (Mg/ha)
* DAP médio
* A árvore de maior biomassa estimada

Esses resultados alimentam diretamente o cálculo do [Índice de Resiliência Florestal Amazônica (IRFA)](indice-irfa.md).
