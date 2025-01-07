# 🚀 Installation et Administration d’un Raspberry Pi avec Linux Pi OS

Ce projet détaille les étapes d’installation et d’administration d’un système Linux Pi OS sur un Raspberry Pi, ainsi que des manipulations basiques sous Linux.

---

## 🌟 **Prérequis**

- 🖥️ Un Raspberry Pi (version 3, 4 ou 5).
- 💾 Une carte Micro SD (et un adaptateur Micro SD/USB si nécessaire).
- 💻 Un PC avec connexion internet.
- 🛠️ Application **Raspberry Pi Imager** installée.
- 🌐 Accès réseau pour connecter le Raspberry Pi via Wi-Fi ou Ethernet.

---

## 📋 **Étapes**

### **1. Préparation de la carte Micro SD**
1. ⬇️ Télécharger et installer **Raspberry Pi Imager** sur le PC :
   - Aller sur le site officiel : [https://www.raspberrypi.com/software/](https://www.raspberrypi.com/software/)
   - Télécharger et exécuter l'installateur.
2. 🛡️ Choisir l’architecture du Raspberry Pi : modèle 3, 4 ou 5.
3. 📥 Sélectionner une version du système d’exploitation (Linux Pi OS) via Raspberry Pi Imager :
   - Choisir **Raspberry Pi OS (32-bit)**.
4. 💽 Écrire l’image système sur la carte Micro SD à l’aide de Raspberry Pi Imager :
   - Insérer la carte Micro SD dans le lecteur.
   - Sélectionner la carte dans le logiciel.
   - Cliquer sur "Écrire" et attendre la fin de l’installation.

### **2. Configuration initiale du Raspberry Pi**
5. 🔌 Insérer la carte Micro SD dans le Raspberry Pi et démarrer le système.
   ⚠️ **Ne jamais manipuler la carte Micro SD lorsque le matériel est sous tension.**
6. 📡 Connecter le Raspberry Pi à un réseau Wi-Fi :
   - Suivre l’assistant de configuration ou utiliser un câble Ethernet.
   - Noter l’adresse IP avec la commande :
     ```bash
     hostname -I
     ```
   - Vérifier l’adresse IP détaillée avec :
     ```bash
     ip a
     ```
7. 🔒 Activer SSH avec `raspi-config` :
   ```bash
   sudo raspi-config
   ```
   - Aller dans **Interface Options** → **SSH** → **Enable**.

### **3. Gestion des utilisateurs**
8. 👤 Configurer un compte utilisateur principal :
   - Changer le mot de passe par défaut :
     ```bash
     passwd
     ```
9. 🛠️ Tester des commandes Linux essentielles :
   - 📂 Naviguer dans les répertoires :
     ```bash
     ls
     cd /chemin
     mkdir nouveau_dossier
     ```
   - ✂️ Gérer des fichiers :
     ```bash
     mv fichier.txt /destination/
     rm fichier.txt
     ```
   - 📜 Lire un fichier :
     ```bash
     cat fichier.txt
     ```

### **4. Installation d’un serveur web**
1. 🔒 Activer SSH et VNC dans les paramètres :
   ```bash
   sudo raspi-config
   ```
   - Aller dans **Interface Options** → **SSH/VNC** → **Enable**.
2. 📡 Vérifier l’adresse IP :
   ```bash
   ip a
   ```
3. 📦 Mettre à jour les paquets :
   ```bash
   sudo apt update
   sudo apt upgrade
   ```
4. 🌐 Installer Apache et PHP :
   ```bash
   sudo apt install apache2
   sudo apt install php
   ```
5. 🔄 Vérifier le statut d’Apache :
   ```bash
   sudo systemctl status apache2
   ```
   - Si le service est arrêté, le démarrer :
     ```bash
     sudo systemctl start apache2
     ```
6. 🖋️ Modifier la page d’accueil :
   ```bash
   cd /var/www/html/
   nano index.html
   ```
   - Remplacer à distance avec SCP :
     ```bash
     scp /chemin/fichier.html pi@172.31.0.8:/var/www/html/
     ```
7. 🛠️ Installer et configurer un proxy Squid :
   ```bash
   sudo apt install squid
   ```

### **5. Manipulation d’une clé USB**
12. 🔌 Insérer une clé USB dans le Raspberry Pi.
13. 📋 Copier un fichier sur la clé USB :
    - Identifier la clé USB :
      ```bash
      lsblk
      ```
    - Monter la clé :
      ```bash
      sudo mount /dev/sda1 /mnt
      ```
    - Copier un fichier :
      ```bash
      cp /etc/fichier.txt /mnt/
      ```
14. 🔍 Vérifier le contenu et démonter la clé USB :
    ```bash
    ls /mnt
    sudo umount /mnt
    ```

### **6. Gestion des permissions**
16. 🔐 Modifier les droits d’accès à un fichier :
    ```bash
    chmod 755 fichier.txt
    ```
17. ✅ Vérifier les droits d’accès :
    ```bash
    ls -l fichier.txt
    ```

### **7. Transfert de fichiers avec SCP**
18. 🔄 Copier des fichiers :
    - PC → Raspberry Pi :
      ```bash
      scp fichier.txt pi@172.31.0.8:/home/pi/
      ```
    - Raspberry Pi → PC :
      ```bash
      scp pi@172.31.0.8:/home/pi/fichier.txt ./
      ```



---

## ✍️ **Auteur**
- Documenté par : **[Keran]**  


