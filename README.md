# 🏥 Odoo 19 Multi-Tenant Docker - Examen ERP

**Infrastructure multi-entreprises isolées avec Docker Compose**  
*Projet démontrant la maîtrise d'Odoo en mode SaaS pour 2 entreprises.*

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

Entreprise A : http://localhost:8069 (admin/password)

Entreprise B : http://localhost:9069 (admin/password)

🔒 Sécurité (15% note)
Réseaux isolés Docker personnalisés :

Isolation données : pgdata/ et odoo-data/ séparés

Sécurité réseau : Pas de ports exposés inutilement

Variables secrets : ${DB_PASSWORD} → jamais en clair GitHub

Conformité : RGPD-ready, parfait pour multi-clients

🛠️ Bonnes Pratiques
✅ .gitignore : Volumes exclus (Go de données)

✅ README structuré

✅ Variables d'environnement

✅ Réseaux nommés explicites

📊 Avantages Multi-Tenant
Entreprise	Réseau	Port Odoo	Base PG
A	network_a	8069	odoo_a
B	network_b	9069	odoo_b
Scalabilité : Ajouter entreprise_c = dupliquer le dossier !

👨‍💼 Contexte Professionnel
Chef d'unité recouvrement - Hôpital Duc de Tovar, Tanger
Adapté pour gestion multi-sites hospitaliers avec isolation stricte.

Abderrahim BELMOUFADAL - ERP Odoo | Février 2026
