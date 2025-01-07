# 🚀 Installation et Administration d’un Raspberry Pi avec Linux Pi OS / Debian Bookworm

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
1. ⬇️ Télécharger et installer **Raspberry Pi Imager** sur le PC.
2. 🛡️ Choisir l’architecture du Raspberry Pi : modèle 3, 4 ou 5.
3. 📥 Sélectionner une version du système d’exploitation (Linux Pi OS ou Debian Bookworm) via Raspberry Pi Imager.
4. 💽 Écrire l’image système sur la carte Micro SD à l’aide de Raspberry Pi Imager.

### **2. Configuration initiale du Raspberry Pi**
5. 🔌 Insérer la carte Micro SD dans le Raspberry Pi et démarrer le système.  
   ⚠️ **Ne jamais manipuler la carte Micro SD lorsque le matériel est sous tension.**
6. 📡 Connecter le Raspberry Pi à un réseau Wi-Fi et noter l’adresse IP attribuée.
7. 🔒 Utiliser `raspi-config` pour activer l’autorisation SSH.

### **3. Gestion des utilisateurs**
8. 👤 Configurer un compte utilisateur principal (login et mot de passe).
9. 🛠️ Tester des commandes Linux essentielles :  
   - 📂 `ls`, `cd`, `mkdir` (naviguer/créer des répertoires).  
   - ✂️ `mv`, `rm` (déplacer/supprimer des fichiers).  
   - 🔑 `passwd` (changer le mot de passe).  
   - 📜 `cat` (afficher le contenu d’un fichier).

### **4. Accès distant via VNC**
10. 🖥️ Installer **VNC Viewer** sur le PC.
11. 🌐 Configurer VNC pour se connecter à l’adresse IP du Raspberry Pi et contrôler l’appareil à distance.

### **5. Manipulation d’une clé USB**
12. 🔌 Insérer une clé USB dans le Raspberry Pi.
13. 📋 Utiliser la commande `cp` pour copier un fichier depuis le répertoire `/etc` vers la clé USB.
14. 🔍 Identifier le device USB associé à l’aide des commandes Linux.
15. 📂 Monter et démonter la clé USB avec `mount` et `umount`.

### **6. Gestion des permissions**
16. 🔐 Modifier les droits d’accès à un fichier ou un répertoire avec la commande `chmod`.
17. ✅ Vérifier les effets des modifications sur les autorisations.

### **7. Transfert de fichiers avec SCP**
18. 🔄 Utiliser la commande `scp` pour copier un fichier entre le PC et le Raspberry Pi (dans les deux sens).

---

## 🎯 **Défi**
**Problème :**  
Certains Raspberry Pi peuvent avoir un problème de lecteur de carte Micro SD, empêchant le boot.

**Solution :**  
Configurer le boot à partir d’un **lecteur USB** contenant l’image système, permettant au Raspberry Pi de démarrer correctement.

---

## 🛠️ **Commandes utiles**

- **Connexion SSH :**
  ```bash
  ssh pi@[adresse_IP_du_Raspberry_Pi]
  ```
- **Monter une clé USB :**
  ```bash
  sudo mount /dev/[device_USB] /mnt
  ```
- **Démonter une clé USB :**
  ```bash
  sudo umount /mnt
  ```
- **Modifier les permissions avec chmod :**
  ```bash
  chmod [options] [fichier]
  ```
- **Transfert de fichiers avec SCP :**
  - Du PC vers le Raspberry Pi :  
    ```bash
    scp fichier.txt pi@[adresse_IP_du_Raspberry_Pi]:/chemin/destination/
    ```
  - Du Raspberry Pi vers le PC :  
    ```bash
    scp pi@[adresse_IP_du_Raspberry_Pi]:/chemin/fichier.txt /chemin/local/
    ```

---

## ✍️ **Auteur**
- Documenté par : **[Ton Nom]**  
- 📧 Contact : **[Ton Email]**
