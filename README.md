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

