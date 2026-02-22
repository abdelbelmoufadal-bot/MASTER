# 🏥 Odoo 19 Multi-Tenant Docker - Examen ERP

**Infrastructure multi-entreprises isolées avec Docker Compose**  
*Projet démontrant la maîtrise d'Odoo.*

## 📋 Architecture

entreprise_a/ entreprise_b/
├── docker-compose.yml ├── docker-compose.yml
├── odoo-data/ ├── odoo-data/


text

- **2 réseaux Docker isolés** : `network_a` et `network_b`
- **Odoo 19 + PostgreSQL 15** par entreprise
- **Isolation totale** : Zéro communication entre A et B

## 🚀 Déploiement

### Prérequis
- Docker & Docker Compose
- Variables d'environnement (.env)

### Lancement
```bash
# Entreprise A
cd entreprise_a
docker-compose up -d

# Entreprise B (nouvelle fenêtre)
cd entreprise_b  
docker-compose up -d
Accès :

   Service	             Entreprise A	     Entreprise B
Odoo ERP (v19)	        http://localhost:8069	http://localhost:9069
pgAdmin 4 (Gestion DB)	http://localhost:5050	http://localhost:5051

🔒 Sécurité (15% note)
Réseaux isolés Docker personnalisés :

Isolation données : pgdata/ et odoo-data/ séparés

Sécurité réseau : Pas de ports exposés inutilement

Variables secrets : ${DB_PASSWORD} → jamais en clair GitHub

Conformité : RGPD-ready, parfait pour multi-clients

Chaque environnement inclut une instance pgAdmin isolée pour la maintenance.

Email de connexion : abdel.belmoufadal@gmail.com

Mot de passe : 19451010

📊 Avantages Multi-Tenant
Entreprise	Réseau	Port Odoo	Base PG
A	network_a	8069	odoo_a
B	network_b	9069	odoo_b
Scalabilité : Ajouter entreprise_c = dupliquer le dossier !

👨‍💼 Contexte Professionnel
Chef d'unité recouvrement - Hôpital Duc de Tovar, Tanger
Adapté pour gestion multi-sites hospitaliers avec isolation stricte.
Abderrahim BELMOUFADAL - ERP Odoo | Février 2026



