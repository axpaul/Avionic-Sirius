# Avionic-Sirius
*Sirius experimental rocket avionic (On-board electronics), Version 2024 launched at C'space*

*CC BY-NC-SA 4.0, Copyright 2023 Miailhe Paul, all rights reserved*

![alt tag](https://github.com/axpaul/Avionic-Sirius/blob/fbac212ad1ce0674ffe152965baaea898059b677/Image/Fus%C3%A9e%20exp%C3%A9rimentale%20pour%20le%20C%E2%80%99Space%202024%20(1).png)

# MotorShield Controller

Le **MotorShield Controller** est une carte d'actionneur conçue pour piloter deux moteurs DC. Elle intègre des circuits en pont en H et des capteurs de courant basés sur des résistances shunt, permettant la détection d'événements, la protection contre les surintensités, le contrôle PWM, ainsi que l'indication visuelle de la direction de rotation des moteurs.

---

## Composants principaux

### 1. **Hex Schmitt-Trigger Inverter (74HC14)**
- **Description** : Inverseur logique avec seuils Schmitt pour améliorer l'immunité aux bruits.  
- **Caractéristiques** :
  - Fonctionne avec des signaux LSTTL, CMOS, NMOS, et TTL.
  - Plage de tension de fonctionnement : 2.0V à 6.0V.
  - Immunité élevée au bruit et faible courant d'entrée.

---

### 2. **Optocoupleurs (ACPL-214)**
- **Description** : Optocoupleurs à gain élevé pour une isolation électrique optimale.  
- **Caractéristiques** :
  - Isolation de tension jusqu’à 3000 VRMS.

---

### 3. **Data Converter Isolator (ADuM1281)**
- **Description** : Isolateur numérique double canal pour la transmission de données.  
- **Caractéristiques** :
  - Fonctionne avec une alimentation de 3.3V.
  - Débit de données jusqu'à 100 Mbps.
  - Faible délai de propagation (23 ns).

---

### 4. **INA381A et INA381B – Détection de surintensité**
- **Description** : Amplificateurs de détection de courant avec comparateurs intégrés.  
- **Caractéristiques** :
  - Détection de courants d’entrée entre 10 mA et 3 A.
  - Seuils configurables pour les surintensités (par ex. : 1A).
  - Fonctionnement avec une tension de 3.3V.
  - Intègre une résistance de shunt de 22 mΩ pour la détection.

---

### 5. **DRV8872 – Pilote de moteur DC brossé avec rapport d’erreurs**
- **Description** : Pilote pour moteurs DC avec contrôle PWM.  
- **Caractéristiques** :
  - Plage de tension : 6.5V à 45V.
  - Courant supporté jusqu’à 3.6A.
  - Intègre des protections (UVLO, OCP, TSD) et un rapport d'état des erreurs.
  - Supporte les modes veille et actif avec contrôle de la direction et de la vitesse via PWM.

---

### 6. **Indicateurs LED de direction du moteur**
- **Description** : Circuit simple avec LEDs et résistances pour indiquer la direction de rotation du moteur.  
- **Caractéristiques** :
  - Confirmation visuelle de la rotation du moteur sans connexion supplémentaire.
  - Permet de tester et de vérifier facilement la logique de contrôle.

---

### 7. **Configuration en pont (JP5)**
- **Description** : Jumper configurable pour définir les fonctionnalités d'entrée ou de sortie.  
- **Caractéristiques** :
  - Évite les conflits d’assignation en définissant clairement les modes de fonctionnement.
