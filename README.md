# SALUT — Sistema Integral de Salut & Biometria 2026

Una aplicació web i mòbil nativa (PWA / Local-First / Google Apps Script) dissenyada per al seguiment complet de la salut, composició corporal, nutrició, tuppers i exercici físic.

---

## 🌟 Funcionalitats Principals

### 1. 🏠 Tauler d'Inici 100% Personalitzable (Bento Grid 2026)
- **13 ginys modulars** que pots activar o desactivar des del botó **`⚙️ Personalitzar`**:
  1. ⚖️ **Pes Tendència (EMA 7D)**: Amb corba SVG dinàmica.
  2. 🧬 **Edat Metabòlica**: Càlcul Katch-McArdle, BMR i diferència fisiològica.
  3. 🔬 **Composició Tanita**: Massa muscular, % greix i aigua.
  4. 📐 **Cintura-Altura (WHtR)**: Risc cardiovascular i greix visceral.
  5. 🥗 **Balanç Calòric**: Calories consumides vs. objectiu i dèficit.
  6. 🥩 **Macronutrients Diaris**: Barres de proteïnes, carbohidrats i greixos.
  7. 🍱 **Tuppers a la Nevera**: Racions preparades disponibles.
  8. 🚶 **Passos Health Connect**: Passos diaris i % de l'objectiu.
  9. 🏃 **Últim Entrenament Suunto**: Darrera activitat registrada.
  10. 🩺 **Tensió Arterial (ESH)**: Pressió sistòlica/diastòlica i pols en repòs.
  11. 💧 **Hidratació Interactiva**: Registre ràpid d'aigua amb un sol toc (+250 ml).
  12. 😴 **Son & Recuperació Suunto**: Hores de descans, bateria corporal i HRV.
  13. ✨ **Consell del Coach IA**: Píndola diària personalitzada.

---

### 2. ⚖️ Balança, Biometria & Gràfiques d'Evolució
- **Normalització dual de balança**:
  - *Tanita BC-730* (impedància tetrapolar als peus a casa, en dejú al matí).
  - *eGym Fitness* (bàscula professional del gimnàs).
- **Selector de data i hora arrodonida** amb calendari flotant personalitzat.
- **Gràfiques vectorials SVG natives**:
  - Evolució de Pes, % Greix, Massa Muscular, Aigua Corporal i Greix Visceral.
  - Filtres temporals de 7 dies, 30 dies, 90 dies i 1 any.
  - Gràfiques de mesures corporals (cintura, bíceps, cuixes, etc.).

---

### 3. 🥗 Nutrició, Despensa & Tuppers Cuinats
- **Cercador Unificat amb Assistent IA**:
  - Cerca directa d'aliments a la **Despensa**.
  - Si l'aliment no hi és, l'Assistent IA el busca, n'estima els macronutrients exactes, l'afegeix a l'àpat i el desa a la Despensa automàticament.
  - Escaneig de codis de barres amb cerca ràpida.
- **Sistema de Tuppers**:
  - Elaboració de receptes de tuppers casolans per a batch cooking.
  - Càlcul automàtic de calories i macros per gram cuinat i per ració.
  - Comptador de racions restants a la nevera.
- **Despensa en graella (Grid Menu)**:
  - Aliments classificats per categories (*Proteïnes, Carbohidrats, Greixos, Verdures, Làctics*) amb icones clares.

---

### 4. 🏃 Exercici, Roda Suunto & Health Connect
- **Connexió amb Health Connect & Suunto**:
  - Sincronització de passos diaris, calories actives i temps en moviment.
  - Importació directa de fitxers d'activitat (`.fit`, `.gpx`, `.json`).
- **Roda esportiva interactiva Suunto (Suunto Sports Wheel)**:
  - 16 modalitats esportives (Cursa, Trail Running, Ciclisme, BTT, Força, Natació, etc.) amb dial circular.
  - Desplegable clàssic sincronitzat per categoria.
- **Durada Dual (Minuts vs. Hores:Minuts)**:
  - Commutador directe amb conversió bidireccional automàtica.
- **Camps opcionals**:
  - Distància en quilòmetres (`km`).
  - Calories cremades (`kcal`) amb estimació automàtica basada en METs, pes corporal de la balança i durada.
  - Freqüència cardíaca mitjana (`ppm`) i notes.

---

## 🚀 Desplegament com a App Nativa & GitHub

### Opció A: Publicar a GitHub Pages (Web App & PWA)
1. Puja aquest repositori a GitHub:
   ```bash
   git add .
   git commit -m "feat: Versió completa de SALUT amb PWA, Exercici Suunto i tauler personalitzable"
   git branch -M main
   git remote add origin https://github.com/<el-teu-usuari>/<el-teu-repositori>.git
   git push -u origin main
   ```
2. A GitHub, vés a **Settings > Pages** i a **Source** tria la branca `main`.
3. Obre l'enllaç al mòbil (Safari a iPhone o Chrome a Android) i prem **«Afegir a la pantalla d'inici»** per tenir-la com una **aplicació nativa** a pantalla completa amb icona pròpia.

### Opció B: Google Apps Script (Connectada a Google Sheets)
1. Copia el contingut de `Index.html` (que ja està copiat al teu porta-retalls amb `pbcopy`).
2. Enganxa'l al fitxer `Index.html` del teu projecte de Google Apps Script.
3. El fitxer `Codi.gs` conté el servei backend per guardar les dades al teu Google Sheets i Google Drive.
4. Desplega com a aplicació web.

### Opció C: Empaquetar com a App Nativa iOS / Android (Capacitor)
Pots empaquetar directament aquest projecte com a binari d'iOS (Xcode) o Android (Android Studio):
```bash
npm init -y
npm install @capacitor/core @capacitor/cli
npx cap init SALUT com.didac.salut --web-dir .
npx cap add ios
npx cap add android
npx cap open ios # o npx cap open android
```

---

## 🔒 Privadesa & Local-First
- L'aplicació funciona de forma autònoma i sense dependències obligatòries d'un servidor central.
- Les teves dades es guarden al teu propi dispositiu (`localStorage`) i/o al teu compte privat de Google Workspace.
