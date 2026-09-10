# Secure Web Infrastructure & Pentest - From Scratch

## 📝 Contexte du Projet
Ce dépôt présente la conception, le déploiement et l'audit d'une infrastructure web sécurisée réalisée dans le cadre d'un déploiement en entreprise (PME du secteur de la logistique). L'objectif était de remplacer une infrastructure vieillissante en intégrant les principes de *Security by Design* dès la phase de modélisation.

## 🛠️ Stack Technique & Outils

| Catégorie | Technologies & Outils |
| :--- | :--- |
| **Système & Réseau** | Ubuntu 22.04 LTS, pfSense, Nginx, PostgreSQL, HAProxy |
| **Défense & Hardening**| ModSecurity (WAF), Fail2Ban, Ansible, Let's Encrypt |
| **Sécurité Offensive** | Burp Suite, Nmap, Nessus, OWASP ZAP[cite: 1] |
| **Normes & Standards** | CIS Benchmarks, OWASP Top 10, CVSS v3.1, STRIDE[cite: 1] |

## 🚀 Réalisations Clés

### 1. Architecture Sécurisée & Modélisation (STRIDE)
- Modélisation des menaces via le framework STRIDE (Spoofing, Tampering, Repudiation, Information Disclosure, DoS, Elevation of Privilege)[cite: 1].
- Conception d'une architecture cloisonnée en 3 zones (Internet, DMZ, Interne) appliquant le principe de défense en profondeur[cite: 1].

### 2. Hardening Système (CIS Benchmarks)
- Durcissement d'un serveur Ubuntu 22.04 selon les référentiels CIS Benchmarks (Niveaux 1 & 2)[cite: 1].
- Réduction de la surface d'attaque : désactivation des services inutiles, configuration de UFW (pare-feu), sécurisation SSH (clé RSA 4096 bits, port non standard)[cite: 1].
- **Résultat :** Augmentation du score de conformité CIS de 34% à 87%[cite: 1].

### 3. Security by Design & Cryptographie
- Protection contre l'OWASP Top 10 : utilisation de requêtes préparées (SQLi), échappement contextuel et CSP (XSS), tokens uniques (CSRF), et hachage bcrypt (facteur 12)[cite: 1].
- Déploiement d'une PKI avec Let's Encrypt, forçant le HTTPS via HSTS[cite: 1].
- Configuration TLS durcie (TLS 1.2/1.3 exclusif, Perfect Forward Secrecy) certifiée **A+** sur SSL Labs[cite: 1].

### 4. Tests d'Intrusion & SOC
- Conduite d'une campagne de pentest (boîtes noire et grise) identifiant des vulnérabilités (ex: absence de rate limiting, exposition d'en-têtes)[cite: 1].
- Déploiement et *tuning* du WAF ModSecurity (OWASP CRS v3.3), réduisant les faux positifs à moins de 1%[cite: 1].
- Implémentation de Fail2Ban pour contrer les attaques par force brute (SSH et applicatives)[cite: 1].
