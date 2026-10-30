# OFFGRID – Seznam delov (BOM)

**Namen:** seznam delov za projekt OFFGRID za prijavo Fallen  
**Posodobljeno:** 30. 10. 2026

Cene so informativne in so bile preverjene na spletnih straneh ob pripravi dokumenta. Pred naročilom preveri še zalogo, končno ceno in poštnino. Kjer cena ali izdelek še ni izbran, je to jasno označeno.

## Kaj že imam

- **SC001 kovček** – glavno ohišje za OFFGRID.
- **2 ESP32 razvojni ploščici** – točen model še ni znan. Za zdaj ju ne štejem kot končni LoRa napravi.
- **Tipkovnica** – za glavno OFFGRID postajo.
- **3D tiskalnik** – z njim bom izdelal nosilce in pritrdilne dele.
- Nekaj kablov, stikal in elektronskega materiala – zalogo moram še pregledati.

## Kaj moram še kupiti

### 1. Farnell – glavno naročilo

Poskusil bom čim več glavne elektronike naročiti skupaj pri Farnellu, da zmanjšam število poštnin.

- **Raspberry Pi 5, 8 GB – 1 kos**  
  Cena: **155,11 € brez DDV** (približno **189,23 € z 22 % DDV**).  
  [Kupi pri Farnellu](https://si.farnell.com/raspberry-pi/rpi5-8gb-single/raspberry-pi-5-model-b-8gb-2-4ghz/dp/4256000)

- **Raspberry Pi 512 GB NVMe SSD + M.2 HAT+ – 1 komplet**  
  Cena: **112,67 € brez DDV** (približno **137,46 € z DDV**).  
  To je komplet, zato dodatnega M.2 HAT+ ne potrebujem kupiti posebej.  
  [Kupi pri Farnellu](https://si.farnell.com/raspberry-pi/sc1676/ssd-kit-nvme-512gb-rpi-5-board/dp/4550994)

- **Raspberry Pi Active Cooler – 1 kos**  
  Cena: **4,30 € brez DDV** (približno **5,25 € z DDV**).  
  [Kupi pri Farnellu](https://si.farnell.com/raspberry-pi/sc1148/cooling-fan-raspberry-pi-5-model/dp/4263049)

**Skupaj Farnell:** približno **272,08 € brez DDV oziroma 331,94 € z DDV**, brez poštnine.  
Pri SSD kompletu preveri dobavni rok – na strani je lahko drugačen kot pri Raspberry Pi in hladilniku.

### 2. Zaslon – Grobotronics

- **Waveshare 8DP-CAPLCD, 8-palčni zaslon na dotik – 1 kos**  
  Ločljivost 1280 × 800, IPS, HDMI in kapacitivni dotik.  
  Cena na strani: **86,80 €**.  
  [Kupi pri Grobotronics](https://grobotronics.com/lcd-display-8-1280x800-ips-hdmi-interface-with-touch.html?sl=en)

Zaslon ima v kompletu HDMI in USB kable ter nekaj adapterjev, zato jih ne kupujem še enkrat.

### 3. LoRa komunikacija

Za LoRa želim dve napravi: eno povezano z Raspberry Pi in eno ročno napravo. Obe bosta uporabljali frekvenčni pas 868 MHz.

- **Heltec ESP32-S3 + SX1262 LoRa ploščica – 2 kosa**  
  Ena bo za ročni terminal, druga pa kot LoRa radijska povezava z glavno postajo.  
  Trenutna kandidatka: Heltec ploščica z OLED zaslonom.  
  Cena na Hestore: približno **21,20 € brez DDV na kos** (približno **25,86 € z DDV**).  
  Za dve: približno **42,40 € brez DDV oziroma 51,72 € z DDV**.  
  [Poglej pri Hestore](https://www.hestore.eu/en/prod_10044569.html)

- **Anteni za 868 MHz – 2 kosa**  
  Cena: še ni izbrana. Anteni morata ustrezati priključkoma na izbranih ploščicah. Ne naročim ju, dokler ne potrdim točnega modela ploščice in priključka.

- **Vnos besedila na ročnem terminalu**  
  Potrebujem način za pisanje poljubnih sporočil, ne samo vnaprej določenih ukazov. Še odločiti se moram, ali bom uporabil majhno tipkovnico ali drug način vnosa. Cena še ni določena.

### 4. Navigacija

- **GNSS sprejemnik z anteno – 1 kos**  
  Potreben za določanje položaja pri offline navigaciji. Izbrati moram še točen USB ali UART model.  
  Cena in povezava: še nista določeni.

### 5. Napajanje

- **LiFePO4 baterija z zaščito/BMS – 1 kos**  
  Baterija mora ustrezati prostoru v kovčku. Najprej moram izmeriti največjo dovoljeno dolžino, širino in debelino. Cilj je približno 10 ur delovanja, vendar moram to še preveriti z izračunom porabe.

- **Polnilnik za izbrano LiFePO4 baterijo – 1 kos**  
  Kupim ga šele, ko izberem baterijo, da bo ustrezal njeni napetosti in načinu polnjenja.

- **DC-DC pretvornik na stabilnih 5 V – 1 kos**  
  Za napajanje Raspberry Pi in zaslona. Izbrati ga moram glede na dejansko porabo; za Raspberry Pi 5 je treba zagotoviti dovolj toka tudi ob največji obremenitvi.

- **Varovalka, glavno stikalo, konektorji in žice**  
  Del teh stvari mogoče že imam. Končne vrednosti in količine določim po načrtu napajanja.

- **Lastna PCB za upravljanje napajanja – 1 kos**  
  Načrtoval jo bom sam. Izdelava in elektronske komponente bodo dodane v seznam, ko bo načrt vezja končan.

## Trenutni seštevek znanih cen

- Farnell: približno **331,94 € z DDV**.
- Zaslon Grobotronics: **86,80 €** po prikazani ceni.
- Dve Heltec LoRa ploščici: približno **51,72 € z DDV**.

**Skupaj znani deli: približno 470,46 €**, brez poštnine in brez še neizbranih delov (baterija, GNSS, anteni, tipkovnica za ročni terminal, napajalni pretvornik in drobni material).

To še ni končna cena projekta. Ko izberem baterijo, GNSS in ostale dele, bom seznam dopolnil s točnimi povezavami in cenami.

## Kaj bom izdelal sam

- 3D natisnjene nosilce in pritrdilne elemente za kovček.
- PCB za upravljanje napajanja.
- Programsko opremo za offline navigacijo, lokalnega AI pomočnika in LoRa sporočanje.
- Ohišje oziroma nosilec za ročni LoRa terminal, če bo potreben.

## Opomba

V različico OFFGRID v1 **ne spadajo** RTL-SDR sprejemnik in GPS/LoRa sledilniki. To so ideje za morebitno različico v2, zato jih v tem seznamu ne kupujem.
