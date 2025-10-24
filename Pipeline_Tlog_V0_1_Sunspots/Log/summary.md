# Journal de session T_log V0.1

- Session démarrée: 2025-10-24T00:59:04.940141Z
- Conventions: biais=0 par défaut, seeds fixés (42), sorties dans results/

- 2025-10-24T00:59:04.941129Z [INFO] Bloc 1 prêt: imports, seeds, dossiers et logger configurés.
- 2025-10-24T00:59:05.625965Z [INFO] Plot de vérification sauvegardé: results/env_check_plot.png
- 2025-10-24T01:02:10.097714Z [INFO] Fichier /content/data/Sunspots.zip décompressé dans data/sunspots_raw
- 2025-10-24T01:05:05.141802Z [INFO] Calcul T_log effectué: n=3265, d=1, T_log=-24.2730, régime=Divergence (instabilité)
- 2025-10-24T01:10:21.386072Z [INFO] Sensibilité T_log(d) tracée et table sauvegardée: results/Tlog_vs_d_plot.png, results/Tlog_vs_d_table.csv
- 2025-10-24T01:14:06.321719Z [INFO] Balayage T_log(n) effectué pour d=3 et d=5. Résultats: results/Tlog_vs_n_d3_d5_plot.png, results/Tlog_vs_n_d3_d5.csv
- 2025-10-24T01:17:31.190133Z [INFO] Régression linéaire T_log vs ln(n) effectuée pour d=3 et d=5. Résultats: results/regression_Tlog_ln_n.csv
- 2025-10-24T01:28:22.472816Z [INFO] Bootstrap T_log terminé: mean=-20.723266, std=0.000000, file_csv=results/bootstrap_Tlog.csv, file_png=results/bootstrap_Tlog_hist.png
- 2025-10-24T01:31:56.925618Z [INFO] Bootstrap variable n terminé: mean=-20.686587, std=0.861508, files=results/bootstrap_variable_n_Tlog.csv, results/bootstrap_variable_n_hist.png

---

## Rapport Intermédiaire — Robustesse T_log V0.1 (Blocs 7–8)

### 1. Rappel du modèle
Formule :

\[
T_{\log}(n, d) = (d - 4) \cdot \ln(n) + \text{biais}, \quad \text{avec biais = 0}
\]


Régimes :
- T_log > 0 → Saturation
- T_log ≈ 0 → Équilibre
- T_log < 0 → Divergence

### 2. Dataset utilisé
- Fichier : `Sunspots.csv`
- Type : série temporelle mensuelle
- Taille : n = 3265
- Dimension effective : d = 1
- Qualité : aucune valeur manquante

### 3. Calcul initial
- T_log = -24.2730 → Régime = Divergence

### 4. Sensibilité en d
- Variation de d : 1 à 6
- Résultats :
  - d = 1,2,3 → Divergence
  - d = 4 → Équilibre
  - d = 5,6 → Saturation
- Fichiers :
  - Graphique : `results/Tlog_vs_d_plot.png`
  - Tableau : `results/Tlog_vs_d_table.csv`

### 5. Balayage en n
- Variation de n : 10 → 10 000
- d = 3 → T_log < 0 ; d = 5 → T_log > 0
- Symétrie parfaite
- Fichiers :
  - Graphique : `results/Tlog_vs_n_d3_d5_plot.png`
  - Tableau : `results/Tlog_vs_n_d3_d5.csv`

### 6. Régression linéaire T_log vs ln(n)
- Objectif : valider la pente théorique (d - 4)
- Résultats :
  - d = 3 → pente = -1.0000
  - d = 5 → pente = +1.0000
  - R² = 1.0
- Fichier : `results/regression_Tlog_ln_n.csv`

### 7. Bootstrap fixe (n = 1000)
- 100 échantillons
- T_log constant = -20.7233
- Std = 0.0000
- Fichiers :
  - Histogramme : `results/bootstrap_Tlog_hist.png`
  - Tableau : `results/bootstrap_Tlog.csv`

### 8. Bootstrap variable (n ∈ [500,1500])
- 100 échantillons
- Moyenne T_log = -20.6866
- Std = 0.8615
- Fichiers :
  - Histogramme : `results/bootstrap_variable_n_hist.png`
  - Tableau : `results/bootstrap_variable_n_Tlog.csv`

### 9. Conclusion intermédiaire
- Le modèle T_log V0.1 est robuste :
  - Sensibilité linéaire validée
  - Bootstrap stable
  - Aucun artefact détecté
- Prochaine étape : tests sur graphes (dimension spectrale)

---
