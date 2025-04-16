# OpenBook – Cititor de Cărți Electronice Open-Source

OpenBook este un dispozitiv de tip e-book reader cu sursă deschisă, proiectat să fie accesibil și eficient. Creat în cadrul inițiativei TSC, dispozitivul este construit în jurul microcontrolerului ESP32-C6, oferind funcții avansate de afișare, conectivitate și consum energetic redus. Designul său este pregătit pentru producția de serie.

# Diagrama
![diagramaReadme](https://github.com/user-attachments/assets/b3b2bf74-13f5-4443-afec-7220b29a054a)

# [BOM] - Bill of Materials

| Componentă             | Descriere                            | Link |
|------------------------|--------------------------------------|------|
| ESP32-C6-WROOM-1-N8    | Wi-Fi, BLE, Zigbee SoC Module        | [Link](https://www.snapeda.com/parts/ESP32-C6-WROOM-1-N8/Espressif+Systems/view-part/) |
| BME680                 | Environmental Sensor                 | [Link](https://www.snapeda.com/parts/BME680/Bosch/view-part/?welcome=home) |
| MCP73831               | Li-Po Battery Charging Controller    | [Link](https://www.digikey.com/en/products/detail/microchip-technology/MCP73831T-2ACI-OT/1874108) |
| DS3231SN               | Real-Time Clock                      | [Link](https://www.snapeda.com/parts/DS3231SN%23/Analog+Devices/view-part/) |
| MAX17048G+T10          | Battery Fuel Gauge                   | [Link](https://www.digikey.com/en/products/detail/analog-devices-inc-maxim-integrated/MAX17048G-T10/9357632) |
| W25Q512JVEIQ           | 512Mb Flash Memory                   | [Link](https://www.snapeda.com/parts/W25Q512JVEIQ/Winbond/view-part/) |
| USB4110-GF-A           | USB Type-C Connector                 | [Link](https://www.digikey.com/en/products/detail/amphenol-commercial-products/USB4110-GF-A/6039334) |
| 112A-TAAR-R03          | Micro SD Card Connector              | [Link](https://store.comet.bg/en/Catalogue/Product/43497/) |
| XC6220A331MR-G         | LDO Voltage Regulator                | [Link](https://www.lcsc.com/product-detail/LDO-Voltage-Regulators_Torex-Semicon-XC6220A331MR-G_C35154.html) |
| SI1308EDL-T1-GE3       | N-Channel MOSFET                     | [Link](https://www.digikey.com/en/products/detail/vishay-siliconix/SI1308EDL-T1-GE3/770967) |
| DMG2305UX-7            | P-Channel MOSFET                     | [Link](https://www.digikey.com/en/products/detail/diodes-incorporated/DMG2305UX-7/2713557) |
| USBLC6-2SC6Y           | USB ESD Protection                   | [Link](https://www.digikey.com/en/products/detail/stmicroelectronics/USBLC6-2SC6Y/458756) |
| MBR0530                | Schottky Diode                       | [Link](https://www.digikey.com/en/products/detail/onsemi/MBR0530T1G/965411) |
| CPH3225                | 11mF Supercapacitor                  | [Link](https://www.snapeda.com/parts/CPH3225A/Seiko+Instruments/view-part/) |
| CC0402                 | Capacitor                            | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO) |
| RR0402                 | Resistor                             | [Link](https://www.snapeda.com/parts/RC0402FR-07226RL/Yageo/view-part/) |

Dispozitivul suportă mai multe surse de alimentare:

- **USB-C**: Alimentare și comunicare prin conectorul `USB4110-GF-A`, cu protecție ESD (`USBLC6-2SC6Y`)
- **Baterie Li-Po**: Încărcată prin controlerul `MCP73831`, cu indicator de stare LED
- **Backup cu supercondensator**: `CPH3225A` menține alimentarea ceasului RTC în caz de pierdere de curent

**Calea de alimentare include:**

- `XC6220A331MR-G` – LDO care furnizează 3.3V stabil pentru sistem
- `MAX17048G+T10` – Fuel gauge pentru monitorizarea capacității bateriei
- `DMG2305UX-7` – MOSFET P-Channel pentru selecția automată a sursei de alimentare
- `MBR0530` – Diodă Schottky pentru protecție la tensiuni inverse

---

## Procesare & Memorie

- `ESP32-C6-WROOM-1-N8` – Microcontroller principal cu suport pentru Wi-Fi 6, Bluetooth 5 și Zigbee 3.0
- `W25Q512JVEIQ` – Memorie Flash SPI externă de 512Mb pentru stocare extinsă
- **Slot microSD** – Permite extinderea stocării pentru datele utilizatorului

---

## Senzori & Ceas

- `BME680` – Senzor ambiental I²C ce măsoară:
  - Temperatură: -40°C până la +85°C  
  - Umiditate: 0–100% RH  
  - Presiune: 300–1100 hPa  
  - Calitatea aerului (rezistență la gaze)
- `DS3231SN` – Ceas în timp real I²C cu compensare termică, foarte precis

---

## Conectivitate & Interfețe

- **USB-C** – Pentru alimentare, încărcare și comunicare de date
- **Qwiic / STEMMA QT** – Conector I²C rapid pentru extensii externe (senzori, periferice)
- **I²C & SPI** – Utilizate pentru senzori și memorie
- **Mod Deep Sleep** – ESP32 intră în standby (~20 µA) pentru autonomie crescută

---

## Interfață Utilizator

- **Buton Reset** – Repornește dispozitivul
- **Buton Boot** – Permite accesul în modul bootloader pentru programare
- **Buton Change** – Poate fi folosit pentru interacțiuni cu conținutul afișat

# 🧷 Pini ESP32-C6

| GPIO  | Componentă       |
|-------|------------------|
| IO9   | Boot Button      |
| IO2   | SD Card          |
| IO4   | SD Card          |
| IO21  | I2C Shared       |
| IO6   | SPI Shared       |
| IO22  | I2C Shared       |
| IO7   | SPI Shared       |
| IO0   | RTC              |
| IO13  | USB Interface    |
| IO19  | MAX17048         |
| IO11  | NOR Flash        |
| IO12  | USB Interface    |
| IO1   | RTC              |
| IO8   | GPIO             |
| IO15  | Buton Change     |
| IO18  | RTC              |
| IO17  | UART             |
| IO16  | UART             |
| EN    | Buton Reset      |
