🛡️ My Secure Homelab

Bienvenue sur le dépôt de documentation de mon infrastructure personnelle de cybersécurité.
Ce projet a pour but de simuler un environnement d'entreprise réaliste pour expérimenter les techniques de Défense (Blue Team), d'Automatisation (IaC) et d'Architecture Zero Trust.

Il sert de terrain d'entraînement pour la mise en œuvre de politiques de sécurité strictes, la détection d'intrusions et la réponse aux incidents.

🏗️ Architecture Réseau

[Insérer ici le schéma d'architecture exporté depuis Draw.io]

L'infrastructure est virtualisée sous Proxmox VE et segmentée de manière stricte via un pare-feu pfSense. L'objectif est d'empêcher tout mouvement latéral non autorisé (principe du Assume Breach).

Zone ADMIN (VLAN 10) : Gestion de l'infrastructure, accès VPN Wireguard.

Zone TRUSTED (VLAN 20) : Services critiques (Vaultwarden, Homepage) isolés.

Zone DMZ (VLAN 30) : Services exposés via Tunnel (Nginx, Portfolio).

Zone IOT/LAB (VLAN 40) : Environnement non approuvé et sandboxing.

🚀 Fonctionnalités & Sécurité

🔒 Accès & Identité (Zero Trust)

Exposition sécurisée : Utilisation de Cloudflare Tunnel pour exposer les services web sans ouvrir aucun port entrant sur le pare-feu (Surface d'attaque réduite).

Politique d'accès : Les services administratifs sont protégés par une authentification multifacteur en amont (Cloudflare Access).

👁️ Détection & Surveillance (SOC)

SIEM : Déploiement de Wazuh pour la centralisation des logs et la détection d'intrusions (HIDS).

Surveillance Endpoint : Utilisation de Sysmon sur les machines Windows pour une télémétrie avancée (création de processus, injections).

Règles Custom : Développement de règles de détection spécifiques (ex: persistance registre MITRE T1547).

⚙️ Automatisation (DevSecOps)

Infrastructure as Code : Utilisation d'Ansible pour le déploiement et la configuration des agents de sécurité.

Hardening : Playbooks de durcissement automatique des serveurs Linux (SSH, Sysctl, Permissions).

🛠️ Stack Technique

Catégorie

Technologies

Virtualisation

Proxmox VE, Docker, LXC

Réseau & Sécurité

pfSense, Snort/Suricata, Cloudflare Zero Trust

SIEM & Logs

Wazuh, ELK Stack, Sysmon

Automatisation

Ansible, Bash, Python

DNS & Filtrage

AdGuard Home (DNS Sinkhole)

📅 Roadmap & Avancement

[x] Déploiement de l'hyperviseur et segmentation réseau (VLANs).

[x] Mise en place du Tunnel Cloudflare (Zero Trust).

[x] Installation du SIEM Wazuh et remontée des logs.

[ ] Création de dashboards de supervision (Kibana).

[ ] Automatisation du déploiement des agents via Ansible.

[ ] Simulation d'attaques (Purple Team) pour valider les détections.

Ce dépôt est maintenu par Aurélien Logeais - Analyste Cybersécurité Junior.
[Lien vers mon Portfolio / LinkedIn]
