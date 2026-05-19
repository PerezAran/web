 # 🔍 PRÀCTICA: Analitzador de Protocols Wireshark

Aquest repositori conté la memòria i resolució de la pràctica d'anàlisi de xarxes utilitzant **Wireshark** al sistema Kali Linux.

> ⚠️ **ATENCIÓ IMPORTANT:** Tots els noms d'equips hosts a VirtualBox, usuaris i sistemes reflecteixen l'autoria de l'estudiant (**Aran Perez**) per a la validació de les captures de pantalla.

---

## 🎯 Objectius de la Pràctica
* Configurar i utilitzar Wireshark en entorns reals i virtualitzats.
* Comprendre el flux de protocols fonamentals: **ICMP, DNS, ARP, FTP, Telnet i SSH**.
* Aplicar filtres de visualització (*Display Filters*) avançats per analitzar paquets específics.
* Realitzar tasques de forense de xarxa a partir de fitxers de captura `.pcapng`.

---

## 🛠️ Part 1: Anàlisi en Viu

### 🌐 Configuració Inicial de la Xarxa
* **SO:** Kali Linux (Adaptador Pont)
* **Adreça IP:** `192.168.4.X/24` *(On X és el número de llista)*
* **Porta d'enllaç:** `192.168.4.254`
* **DNS:** `8.8.8.8`

---

### 🏓 1. Protocol ICMP (Ping)
Filtre utilitzat: `icmp`

1. **Quin número de tipus de ICMP té la petició d'eco i quin la resposta d'eco? Com ho veus?**
   * **Echo Request (Petició):** Tipus `Type: 8`
   * **Echo Reply (Resposta):** Tipus `Type: 0`
   * *Es pot veure desglossant la capçalera del protocol ICMP dins de la secció de detalls del paquet a Wireshark.*

#### 📸 Captura de pantalla (Tipus ICMP):
<!-- Afegeix la teva captura aquí -->
![Tipus ICMP](ruta/a/la/teva/captura_icmp.png)

2. **Mode Promiscu (Permetre-ho tot):**
   * **Trànsit detectat des de la màquina física:** 
   * *(Aquí has d'explicar quin trànsit de la teva màquina real has enxampat, com ara peticions HTTP/HTTPS, trànsit de fons de Windows/Mac, broadcast, etc.)*

---

### 🌲 2. Protocol DNS
Filtre utilitzat: `dns && ip.addr == 192.168.4.X`

* **Petició de resolució del client:** *(Explica si veus el paquet `Standard query 0x... A www.xtec.cat`)*
* **Comprovació de la IP de `www.xtec.cat`:**
  ```bash
  nslookup www.xtec.cat
