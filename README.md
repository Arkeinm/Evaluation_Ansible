# 📦 Rôle Ansible – Déploiement automatisé de WordPress

## 🧾 Présentation

Ce rôle Ansible permet de mettre en place automatiquement un site WordPress accompagné de sa base de données MariaDB sur des systèmes Linux.  
Il est conçu pour fonctionner aussi bien sur des machines virtuelles que dans des environnements conteneurisés (Docker).

---

## ⚙️ Ce que fait ce rôle

- Installation complète d’une stack web (Apache, PHP, MariaDB)
- Prise en charge de plusieurs distributions :
  - Ubuntu / Debian
  - Rocky Linux / systèmes basés RedHat
- Exécution possible sur :
  - VM classiques
  - Conteneurs Docker
- Fonctionnement idempotent (exécutable plusieurs fois sans casser l’existant)
- Paramétrage flexible via variables
- Utilisation de handlers pour redémarrer les services uniquement si nécessaire
- Sécurisation initiale de MariaDB :
  - Suppression des comptes anonymes
  - Suppression de la base de test
- Création automatique des clés de sécurité WordPress

---

## ▶️ Mise en œuvre

### Exemple de playbook

```yaml
---
- name: Installation WordPress automatisée
  hosts: webservers
  become: true

  roles:
    - ansible-role-wordpress
```

## Exécution 

### Accéder au projet 
```bash
cd /root/projet
```

### Lancement du déploiement
```bash
ansible-playbook -i inventaire.ini playbooks/deploy-wordpress.yaml -v
```