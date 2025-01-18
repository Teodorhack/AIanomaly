# 🚀 Jupyter Notebook Docker Container

Acesta este un ghid **pas cu pas** pentru a descărca și rula mediul de dezvoltare Jupyter Notebook într-un **container Docker** pe un sistem **Linux**. Veți avea un mediu complet configurat, incluzând toate librăriile necesare, pentru a putea lucra cu caietul `AnomalyDet.ipynb`.

---

## 🛠️ 1. Instalarea Docker

Pentru a rula mediul de dezvoltare, trebuie să aveți **Docker** instalat pe sistemul vostru Linux. Dacă nu aveți Docker, urmați pașii de mai jos pentru a-l instala.

// **Pasul 1:** Deschideți terminalul și executați următoarele comenzi:

$sudo apt update  
$sudo apt install docker.io  
$sudo systemctl enable --now docker  
$sudo usermod -aG docker $USER  

// **Pasul 2:** După instalare, verificați dacă Docker este instalat corect cu comanda:

$docker --version  

---

## 📥 2. Descărcarea imaginii Docker

Pentru a descărca imaginea Docker ce conține **Jupyter Notebook** și toate librăriile necesare, executați următoarea comandă:

$docker pull teogiurgica/jupyter-notebook:latest

Acesta va descărca imaginea Docker denumită `jupyter-notebook` de pe Docker Hub.

---

## 🚀 3. Rularea containerului Docker

După ce imaginea este descărcată, porniți containerul Docker cu următoarea comandă:

$docker run -p 8888:8888 teogiurgica/jupyter-notebook:latest

Aceasta va porni un container Docker care va expune portul **8888** pentru a accesa Jupyter Notebook.

---

## 🌐 4. Accesarea Jupyter Notebook

După ce containerul a fost pornit, accesați **Jupyter Notebook** în browserul vostru la următoarea adresă:

http://localhost:8888

Vi se va cere să introduceți un **token**. Pentru a-l găsi, deschideți terminalul și căutați tokenul generat de Jupyter în logurile afișate.

---

## 📚 5. Obținerea caietului Jupyter (`AnomalyDet.ipynb`)

Caietul **`AnomalyDet.ipynb`** este disponibil în GitHub. Îl puteți descărca sau clona din depozitul GitHub:

👉 [GitHub - AnomalyDet.ipynb](https://github.com/<username>/<repo>/blob/main/AnomalyDet.ipynb)

După ce ați descărcat caietul, încărcați-l în **Jupyter Notebook**, iar acum puteți să-l rulați și să explorați mediul complet configurat!

---

## 🛠️ 6. Crearea unui mediu Docker personalizat (Opțional)

Dacă doriți să adăugați librării suplimentare la imaginea Docker, editați fișierul **`Dockerfile`** și adăugați comanda de instalare pentru librăriile dorite.

De exemplu, pentru a instala **`seaborn`** și **`matplotlib`**:

RUN pip install --no-cache-dir seaborn matplotlib

După ce ați modificat fișierul **`Dockerfile`**, reconstruiți imaginea Docker cu comanda:

$docker build -t teogiurgica/jupyter-notebook:latest .

Apoi, împingeți imaginea modificată pe **Docker Hub**:

$docker push teogiurgica/jupyter-notebook:latest

---

## 🐛 7. Depanare

Dacă întâmpinați probleme sau aveți întrebări, vă rugăm să consultați documentația oficială Docker sau să lăsați un comentariu pe GitHub.

---

## 🔄 Resurse

- 🖥️ [Documentația oficială Docker](https://docs.docker.com/)
- 📝 [GitHub - Repository pentru caietul `AnomalyDet.ipynb`](https://github.com/<username>/<repo>)
