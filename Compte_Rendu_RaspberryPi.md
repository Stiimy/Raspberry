
# 🚀 Compte Rendu : Installation et Administration d'un Raspberry Pi avec Linux Pi OS / Debian Bookworm

## **Prérequis**

Avant de commencer, j'ai préparé tout le nécessaire pour l'installation du Raspberry Pi. Cela a impliqué :
- Utiliser un **Raspberry Pi** modèle 4.
- Une **carte Micro SD** avec un adaptateur pour le connecter au PC.
- Un PC avec une connexion Internet et l'application **Raspberry Pi Imager** déjà installée.

J'avais également un accès réseau pour pouvoir connecter le Raspberry Pi en Wi-Fi.

---

### **1. Préparation de la carte Micro SD**

La première étape a été de télécharger et installer **Raspberry Pi Imager** sur le PC. Ensuite, j'ai sélectionné l'architecture pour mon Raspberry Pi (modèle 4) et j'ai choisi **Linux Pi OS** comme système d’exploitation. Après cela, l’image système a été écrite sur la carte Micro SD, prête à être insérée dans le Raspberry Pi.

---

### **2. Configuration initiale du Raspberry Pi**

Une fois la carte Micro SD insérée, j'ai allumé le Raspberry Pi. Lors du démarrage, il a demandé de se connecter à un réseau Wi-Fi, ce que j'ai fait. L'adresse IP attribuée a été notée pour pouvoir y accéder plus tard via SSH.

Ensuite, j'ai activé **SSH** avec la commande `raspi-config` afin de pouvoir administrer le Raspberry Pi à distance.

---

### **3. Gestion des utilisateurs**

J'ai configuré le compte utilisateur principal du Raspberry Pi en créant un **login** et un **mot de passe**. Ensuite, j'ai testé des commandes Linux essentielles pour gérer les fichiers et répertoires, comme `ls`, `cd`, `mkdir`, `mv`, `rm`, et `passwd` pour changer le mot de passe. Cela m’a permis de mieux comprendre la gestion des fichiers et des permissions sous Linux.

---

### **4. Accès distant via VNC**

J'ai installé **VNC Viewer** sur le PC et configuré le Raspberry Pi pour pouvoir y accéder à distance. J'ai entré l'adresse IP du Raspberry Pi dans l'application VNC et j'ai pu contrôler le Raspberry Pi via une interface graphique, ce qui m’a facilité les manipulations.

---

### **5. Manipulation d’une clé USB**

Pour tester la gestion de périphériques, j'ai inséré une clé USB dans le Raspberry Pi. J'ai utilisé la commande `cp` pour copier un fichier depuis le répertoire `/etc` vers la clé USB. Grâce à des commandes comme `lsblk`, j'ai pu identifier le périphérique USB et ensuite le monter avec la commande `mount`. Une fois les manipulations terminées, j'ai démonté la clé USB avec `umount`.

---

### **6. Gestion des permissions**

J'ai expérimenté avec les permissions de fichiers en utilisant la commande `chmod` pour modifier les droits d’accès à certains fichiers et répertoires. J'ai vérifié les changements à l'aide de la commande `ls -l` pour m'assurer que les permissions étaient bien appliquées.

---

### **7. Transfert de fichiers avec SCP**

Pour transférer des fichiers entre le Raspberry Pi et le PC, j'ai utilisé la commande `scp`. J'ai d'abord transféré un fichier depuis le PC vers le Raspberry Pi, puis j'ai effectué le transfert inverse pour m'assurer que tout fonctionnait correctement.

---

### **Défi rencontré**

Un problème fréquent avec certains modèles de Raspberry Pi est un lecteur de carte Micro SD défectueux, empêchant le boot. Heureusement, j'ai trouvé une solution simple : démarrer à partir d’un lecteur USB contenant l’image système. Cela a permis au Raspberry Pi de démarrer correctement, résolvant ainsi le problème.

---

## **Commandes utiles**

J'ai utilisé plusieurs commandes pour accomplir les tâches suivantes :
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

## Conclusion

L’installation et la configuration du Raspberry Pi se sont bien déroulées. J'ai pu accomplir des tâches basiques sous Linux, gérer les utilisateurs, manipuler des périphériques USB, et établir des connexions distantes via SSH et VNC. Le Raspberry Pi est maintenant pleinement fonctionnel pour divers projets.

---

Auteur : **[Ton Nom]**  
📧 Contact : **[Ton Email]**
