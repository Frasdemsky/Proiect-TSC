# Proiect-TSC - ceas

am tras trase printre pini in loc de via pentru ca nu stiam la acel moment ca pot pune via pe pin si sa fie in regula

Extras din BOM
<img width="1254" height="845" alt="image" src="https://github.com/user-attachments/assets/7fab895f-16fe-4b85-9a77-49155864037c" />

Descrierea Funcționalității Hardware

Smartwatch-ul InkTime este construit în jurul microcontroller-ului nRF52840, ideal pentru aplicații open-source și comunicație eficientă energetic.

  Sistemul de Alimentare: Încărcarea se face prin mufa USB-C, care beneficiază de protecție ESD prin dioda USBLC6-2SC6Y. Integratul BQ25180YBGR încarcă bateria LiPo. Deoarece tensiunea bateriei variază pe măsură ce se descarcă, un convertor de tip Buck-Boost (RT6160AWSC) menține tensiunea sistemului stabilă la 3.3V. Circuitul integrat MAX17048G+T10 funcționează ca Fuel Gauge pe I2C pentru a raporta precis nivelul bateriei către microcontroller.
  Afișaj E-Paper: Este conectat la placă printr-un port dedicat (E-Paper Display Connector). Pentru o eficiență energetică maximă, alimentarea ecranului trece printr-un tranzistor MOSFET (DMG2305UX), permițând oprirea completă a curentului către display prin semnalul R_PWR_EPD atunci când imaginea nu se actualizează.
  Senzori și Interacțiune: Detecția orientării și a pașilor se face prin senzorul IMU BMA421, conectat prin interfața I2C (TP_SCL și TP_SDA). Pentru feedback la notificări sau apăsări de butoane, sistemul folosește un motor haptic controlat de driver-ul DRV2605YZFR. Interacțiunea manuală se face prin 3 butoane fizice (Up, Enter, Down) decuplate capacitiv.


Alocarea Pinilor nRF52840

  Magistrala I2C: Pinii de pe MCU asociați cu net-urile TP_SCL și TP_SDA conectează senzorul IMU BMA421, circuitul Fuel Gauge MAX17048 și driver-ul haptic DRV2605YZFR.
  Butoane: Butoanele SW_UP, SW_ENT și SW_DN sunt direcționate către pini GPIO ai nRF52840.
  Interfața SWD: Programarea și debugging-ul se realizează exclusiv prin pad-urile de test TP_SWDIO, TP_SWDCLK și TP_RESET.
  Control E-Paper: Comunicarea cu display-ul se face printr-o magistrală ce ajunge la conectorul E-Paper (include pini SPI și semnale de control). Controlul alimentării se realizează prin pinul conectat la R_PWR_EPD.

Am decis sa accept erorile de via pe pini pentru ca asa a spus Dan pe teams ca putem face. poze cu pcb-ul in carcasa se afla in folderul de images.
Puteam sa pun mai central acel MCU si sa am o organizare mai buna.
