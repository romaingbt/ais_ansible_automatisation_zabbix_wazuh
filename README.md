# ais_ansible_automatisation_zabbix_wazuh
Déploiement automatisé des solutions Zabbix, Wazuh et Semaphore UI via Ansible et Docker.

# 🤖 Automatisation du Déploiement de Zabbix et Wazuh avec Ansible & Semaphore UI

## 📋 Présentation du projet
Ce projet réalisé dans le cadre de ma formation consiste à automatiser la préparation et le déploiement de solutions d'infrastructure, de supervision (Zabbix) et de sécurité (SIEM Wazuh) à l'aide d'**Ansible**.

Afin de faciliter la gestion des déploiements au quotidien pour les équipes, une interface graphique **Semaphore UI** a également été déployée sous Docker.

## 🏗️ Architecture & Environnement technique
* **Serveur d'automatisation :** Debian 13 avec Ansible & OpenSSH.
* **Interface Graphique :** Semaphore UI (déployé via Docker).
* **Serveurs cibles :** Machines Debian 13 (IP statiques, accès SSH par clé publique/privée sans mot de passe).
* **Services déployés :** Server Zabbix 7.0 & Manager SIEM/XDR Wazuh.

## ⚙️ Étapes de mise en œuvre

1. **Préparation de l'environnement Ansible :**
   * Configuration de la résolution d'hôtes et attribution d'adresses IP statiques.
   * Génération de paires de clés SSH et déploiement des clés publiques sur les serveurs cibles pour permettre l'exécution automatisée sans mot de passe.

2. **Rédaction et exécution des Playbooks :**
   * Rédaction de playbooks YAML pour la mise à jour des dépôts, l'installation des dépendances (`curl`, `wget`, `vim`) et le déploiement automatique de Zabbix 7.0.
   * Lancement des déploiements via inventaire Ansible.

3. **Mise en place de l'interface graphique Semaphore UI :**
   * Création d'un playbook dédié à l'installation de Semaphore UI sous Docker.
   * Configuration du magasin de clés SSH et connexion au dépôt de playbooks.
   * Création de modèles de tâches (*Templates*) dans l'interface graphique pour déclencher les déploiements de Wazuh en un clic.

---
📁 *Retrouvez les playbooks YAML d'exemple directement dans ce dépôt.*
