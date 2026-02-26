
# Energy Chiller Dashboard (Eau glacée) — COP, dérives, coût & CO₂ (France)

Dashboard statique **HTML** (un seul fichier) pour analyser un système de froid à eau glacée :
- COP chiller vs **baseline conditionnelle** (par plages de température extérieure)
- **COP système** (chiller + pompe)
- Surconsommation kWh vs baseline (proxy)
- Alertes : low COP / charge de nuit / qualité des données
- Conversion **kWh → € → kgCO₂e** (paramétrable, cas France)

> ⚠️ Ce dépôt contient un CSV **démo** (données simulées) pour illustrer la méthode.
> Ne publie jamais de données réelles sensibles.

## 1) Ouvrir le dashboard
Deux façons :
- **Local** : ouvre `index.html` dans Chrome/Edge, puis charge un CSV via le bouton *CSV*.
- **En ligne (GitHub Pages)** : active Pages (Settings → Pages → Deploy from a branch → main → /root).

## 2) Format CSV recommandé
Le dashboard est compatible avec le CSV enrichi produit par le script Python, avec colonnes :
- timestamp (YYYY-MM-DD HH:MM:SS)
- T_out_C, T_supply_C, T_return_C, Flow_m3h, P_elec_kW
- (optionnel mais recommandé) COP_baseline_cond, COP_chiller, COP_system, kWh_excess_sys, dq_flag, flag_low_COP_cond, flag_night_load

Un exemple est fourni :
`data/chilled_water_audit_enhanced_demo.csv`

## 3) Paramètres France (dans l’UI)
- Prix €/kWh : à remplacer par le contrat du site
- Facteur kgCO₂e/kWh : à remplacer par le référentiel/méthode retenue (Base Carbone / RTE, etc.)

## 4) Fichiers
- `index.html` : dashboard
- `data/` : CSV démo
- `docs/` : rapports PDF (méthode + addendum France)
- `screens/` : captures/graphes de référence

## 5) Licence
Usage pédagogique / démonstration. Adapte selon tes besoins.
