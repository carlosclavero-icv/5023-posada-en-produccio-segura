---
tipus: exercici
codi: "LAB-XX"
titol: "Títol de la pràctica"
bloc: "02_Hacking_Web" # 01_Desenvolupament_Web | 02_Hacking_Web | 03_Hacking_Mobil | 04_Desplegament_Segur
ra:
  - "RA2"
  - "RA3"
dificultat: "Mitjana" # Fàcil | Mitjana | Avançada
entorn_requerit: "DVWA a Docker"
avaluable: true
pes_nota: "5%"
temps_estimat_min: 90
tags:
  - docencia/exercici
  - ra/ra3
---

# 🧪 {{title}}

> **Codi**: `LAB-XX` | **Dificultat**: Mitjana | **Temps estimat**: 90 minuts | **Avaluable**: Sí (5%)

---

## 🎯 Objectius
* Identificar...
* Explotar...
* Aplicar la mesura de mitigació adequada en codi font...

---

## 🛠️ Prerequisits i Entorn de Treball
Abans d'iniciar la pràctica, cal disposar de:
1. Màquina virtual o contenidor amb l'entorn: `nom_entorn`
2. Eines necessàries: `Burp Suite`, `Navegador Firefox`, `Terminal`
3. Credencials per defecte: `usuari / contrasenya`

---

## 📋 Tasques a Realitzar

### Tasca 1: Reconeixement i Identificació
1. Descripció del pas 1...
2. Què s'ha d'observar...

```bash
# Comanda d'exemple
curl -I http://localhost:8080
```

### Tasca 2: Explotació Controlada
1. Descripció del pas 2...
2. Demostració de la vulnerabilitat amb el payload:
```sql
' OR '1'='1
```

### Tasca 3: Mitigació i Defensa
1. Revisar el fitxer vulnerable `vulnerable.php`.
2. Substituir el codi vulnerable per una solució segura.

---

## 📤 Evidències i Format de Lliurament
L'alumnat haurà de lliurar a la tasca de Classroom un document en PDF que contingui:
- [ ] Captura de pantalla del resultat de la Tasca 1 amb la IP visible.
- [ ] Explicació tècnica de per què es produeix la vulnerabilitat a la Tasca 2.
- [ ] Codi corregit de la Tasca 3 i captura que demostri que el payload ja no funciona.

---

## 📊 Rúbrica d'Avaluació

| Criteri | Excel·lent (9-10) | Notable (7-8) | Suficient (5-6) | Insuficient (0-4) |
| :--- | :--- | :--- | :--- | :--- |
| **Identificació tècnica** | Identifica el vector amb precisió i explica la fallada d'arrel. | Identifica el vector correctament però l'explicació és superficial. | Identifica la fallada amb ajuda o proves i errors. | No identifica la vulnerabilitat. |
| **Mitigació en codi** | Aplica la millor pràctica estàndard de codi segur. | El pedaç funciona però no és òptim. | Pedaç parcial (bypassable). | No aporta codi segur o no funciona. |
| **Evidències i claredat** | Informe impecable, captures clares amb explicació pròpia. | Bones captures però falta detall explicatiu. | Captures incompletes o desordenades. | Informe deficient o copiat. |
