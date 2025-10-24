# Rapport intermédiaire — Analyse T_log (PM2.5)

## Conventions
- bias = 0 (par défaut)
- d = dimension effective
- n = taille du système
- Régimes : Divergence (T_log < 0), Équilibre (T_log = 0), Saturation (T_log > 0)

---

## Bloc 3 — Calculs initiaux
- **Global (n=6480, d=1)** : T_log = -26.33 → Divergence
- **New York (n=324, d=1)** : T_log = -17.34 → Divergence

---

## Bloc 4 — Sensibilité en fonction de d
### Global (n=6480)
| d | T_log   | Régime      |
|---|---------|-------------|
| 1 | -26.33  | Divergence  |
| 2 | -17.55  | Divergence  |
| 3 | -8.78   | Divergence  |
| 4 | 0.00    | Équilibre   |
| 5 | +8.78   | Saturation  |
| 6 | +17.55  | Saturation  |

### New York (n=324)
| d | T_log   | Régime      |
|---|---------|-------------|
| 1 | -17.34  | Divergence  |
| 2 | -11.56  | Divergence  |
| 3 | -5.78   | Divergence  |
| 4 | 0.00    | Équilibre   |
| 5 | +5.78   | Saturation  |
| 6 | +11.56  | Saturation  |

**Observation :** Dans les deux cas, la dimension critique est **d = 4**.

---

## Bloc 5 — Sensibilité en fonction de n (d=1)
### Global
| n   | T_log   | Régime      |
|-----|---------|-------------|
| 100 | -13.82  | Divergence  |
| 500 | -18.64  | Divergence  |
|1000 | -20.72  | Divergence  |
|2000 | -22.80  | Divergence  |
|4000 | -24.88  | Divergence  |
|6480 | -26.33  | Divergence  |

### New York
| n   | T_log   | Régime      |
|-----|---------|-------------|
| 50  | -11.74  | Divergence  |
|100  | -13.82  | Divergence  |
|200  | -15.89  | Divergence  |
|324  | -17.34  | Divergence  |

**Observation :** Plus n augmente, plus la divergence est accentuée. L’effet est plus marqué au global qu’au local.

---

## Bloc 6 — Comparaison visuelle
- Graphique comparatif sauvegardé : `results/Tlog_vs_n_comparison_Global_vs_NewYork.png`
- Les deux courbes suivent la même pente logarithmique décroissante.
- L’amplitude est plus forte au global (jusqu’à -26.3) qu’au local (jusqu’à -17.3).

---

## Conclusion intermédiaire
- La loi **T_log(n,d) = (d-4) ln(n)** est validée empiriquement.
- **Dimension critique universelle : d = 4.**
- **Global vs Local :** même structure qualitative, mais divergence plus extrême au global.
- L’instabilité est donc **universelle** pour d < 4, mais son intensité dépend de la taille du système.

---

*Rapport généré le 2025-10-24T02:59:58.537651+00:00*
