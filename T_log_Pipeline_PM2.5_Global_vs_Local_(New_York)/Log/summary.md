# Session Log T_log V0.1

- Session started: 2025-10-24T02:21:01.010805+00:00
- Conventions: bias=0 by default, seeds fixed (42), outputs in results/

---
## Bloc 1 — Préparation
- Imports, seeds, dossiers et logger configurés.
- Env check plot: results/env_check_plot.png

- 2025-10-24T02:24:24.847251+00:00 [INFO] Fichier /content/data/Urban Air Quality & Climate Dataset (1958-2025).zip décompressé dans data/air_quality_raw
- 2025-10-24T02:31:26.580628+00:00 [INFO] Inspection du fichier data/air_quality_raw/air_quality_global.csv : 6480 lignes, 0 doublons
- 2025-10-24T02:35:35.607394+00:00 [INFO] Calcul T_log global (PM2.5): n=6480, d=1, T_log=-26.3294, régime=Divergence
- 2025-10-24T02:37:59.664026+00:00 [INFO] Calcul T_log (New York, PM2.5): n=324, d=1, T_log=-17.3422, régime=Divergence
- 2025-10-24T02:43:20.220265+00:00 [INFO] Sensibilité T_log(d) PM2.5 global : CSV=results/Tlog_vs_d_air_quality_global.csv, plot=results/Tlog_vs_d_air_quality_global.png
- 2025-10-24T02:46:29.179421+00:00 [INFO] Sensibilité T_log(d) PM2.5 New York : CSV=results/Tlog_vs_d_air_quality_NewYork.csv, plot=results/Tlog_vs_d_air_quality_NewYork.png
- 2025-10-24T02:49:27.736473+00:00 [INFO] Sensibilité T_log(n) PM2.5 global : CSV=results/Tlog_vs_n_air_quality_global.csv, plot=results/Tlog_vs_n_air_quality_global.png
- 2025-10-24T02:52:45.439580+00:00 [INFO] Sensibilité T_log(n) PM2.5 New York : CSV=results/Tlog_vs_n_air_quality_NewYork.csv, plot=results/Tlog_vs_n_air_quality_NewYork.png
- 2025-10-24T02:56:56.472854+00:00 [INFO] Comparaison T_log(n) Global vs New York : plot=results/Tlog_vs_n_comparison_Global_vs_NewYork.png
- 2025-10-24T02:59:58.542282+00:00 [INFO] Rapport intermédiaire sauvegardé: results/rapport_intermediaire_PM25.md
- 2025-10-24T03:05:34.324070+00:00 [INFO] Bootstrap T_log global : B=1000, mode=subsample, p=0.0000, IC=(-26.2832,-24.3240), plot=results/bootstrap_Tlog_global.png, CSV=results/bootstrap_Tlog_global.csv
- 2025-10-24T03:11:09.671624+00:00 [INFO] Bootstrap T_log New York : B=1000, p=0.0060, IC=(-17.2958,-15.3360), plot=results/bootstrap_Tlog_NewYork.png, CSV=results/bootstrap_Tlog_NewYork.csv
- 2025-10-24T03:22:01.132456+00:00 [INFO] Bootstrap multi-d (PM2.5) : CSV=results/bootstrap_multi_d_PM25_Global_NewYork.csv, plots=results/bootstrap_pvalues_vs_d_Global_NewYork.png, results/bootstrap_Tlog_distributions_multi_d.png
- 2025-10-24T03:47:45.476271+00:00 [INFO] Stress tests et diagnostics : rapport=results/stress_tests_diagnostics_PM25.md, figure=results/residuals_diagnostics_PM25.png
- 2025-10-24T03:57:20.248893+00:00 [INFO] Final consolidated report saved: results/final_report_PM25_en.md
