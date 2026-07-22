# Índice de Resiliência Florestal Amazônica (IRFA)

O **IRFA** mede a capacidade de um ecossistema florestal se recuperar após uma perturbação, integrando três dimensões ecológicas complementares.

## A fórmula

$$
IRFA = \alpha \cdot TNR + \beta \cdot TRB + \gamma \cdot IEC
$$

| Componente | Descrição |
|---|---|
| **TNR** | Taxa de Regeneração Natural |
| **TRB** | Taxa de Recuperação de Biomassa |
| **IEC** | Índice de Estrutura Comunitária |
| **α, β, γ** | Pesos de cada componente (0,33 cada — distribuição equânime) |

Cada componente varia de 0 a 1, assim como o IRFA resultante.

## Classificação de resiliência

| Faixa de IRFA | Classificação |
|---|---|
| < 0,40 | Baixa resiliência |
| 0,40 – 0,70 | Média resiliência |
| > 0,70 | Alta resiliência |

## Implementação de referência

```python
def calcular_irfa(tnr, trb, iec, alpha=0.33, beta=0.33, gamma=0.33):
    """Calcula o Índice de Resiliência Florestal Amazônica (IRFA)."""
    tnr = np.atleast_1d(np.array(tnr, dtype=float))
    trb = np.atleast_1d(np.array(trb, dtype=float))
    iec = np.atleast_1d(np.array(iec, dtype=float))
    return alpha * tnr + beta * trb + gamma * iec


def classificar_irfa(valor):
    if valor < 0.40:
        return 'Baixa'
    elif valor <= 0.70:
        return 'Média'
    else:
        return 'Alta'
```

## Cenários de referência

O protótipo aplica o IRFA a três cenários ecológicos simulados, para ilustrar como o índice responde a diferentes níveis de impacto:

1. **Unidade de Conservação Integral** (baixo impacto) — TNR, TRB e IEC altos → resiliência alta
2. **Área de Uso Sustentável** (impacto moderado) — valores intermediários → resiliência média
3. **Área Desmatada** (alto impacto) — valores baixos em todos os componentes → resiliência baixa

Esse comportamento gradual valida o índice como ferramenta de comparação entre áreas com diferentes históricos de manejo e conservação.
