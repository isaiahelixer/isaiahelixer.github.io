---
title: Component Selection
---

# Component Selection

Subsystem board powered from 9 V input through a 5 V regulator.  
Includes a PIC18F16Q41 Curiosity Nano microcontroller connected to:  
- Analog soil moisture sensor  
- Temperature / humidity sensor  
- Rain sensor  
- 8-pin connector to communicate with other boards  

## Soil Moisture Sensors

*Table 1: Soil Moisture Sensor Comparison*

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/300/287/217/SEN0114_sml.jpg)<br>**Option 1:** SEN0114 Soil Moisture Sensor Module<br>$ — each<br>[link to product](https://www.digikey.com/en/products/detail/dfrobot/SEN0114/6588525?gclsrc=aw.ds&gad_source=1&gad_campaignid=20243136172&gbraid=0AAAAADrbLljjqP1OlpuYdh5M1W-hfUbv9&gclid=Cj0KCQjwjL3HBhCgARIsAPUg7a72iXUga0vyWkCpTmrg7OEWgcecpY3oCWXcBJWl99RSd2a7WRIvGukaAgzTEALw_wcB) | *Simple analog output*<br>*Low cost*<br>*Compact design* | *Corrodes over time if left in soil*<br>*Requires calibration for accuracy* |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/001/169/089/MFG_ST0160_sml%28200x200%29.jpg)<br>**Option 2:** ST0160 Capacitive Soil Moisture Sensor V2.0<br>$ — each<br>[link to product](https://www.digikey.com/en/products/detail/sunfounder/ST0160/22116813?gclsrc=aw.ds&gad_source=1&gad_campaignid=20243136172&gbraid=0AAAAADrbLljjqP1OlpuYdh5M1W-hfUbv9&gclid=Cj0KCQjwjL3HBhCgARIsAPUg7a4EblarQQQLZEiHysFPVUKRckIVFPQZiBxU5v7J3dNoex9XDlxkbKsaAjHHEALw_wcB) | *No corrosion (capacitive)*<br>*Stable analog readings*<br>*Low power consumption* | *More expensive than SEN0114*<br>*Slightly larger PCB footprint* |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/100/930/342/MFG_314990620_sml.jpg)<br>**Option 3:** Industrial Soil Moisture & Temperature Sensor (4-20 mA Output)<br>$ — each<br>[link to product](https://www.digikey.com/en/products/detail/seeed-technology-co-ltd/314990620/16570933?gclsrc=aw.ds&gad_source=1&gad_campaignid=20232005509&gbraid=0AAAAADrbLliHISOuiELCQaQga1eaoIOmc&gclid=Cj0KCQjwjL3HBhCgARIsAPUg7a6GUOuKgdWM8bK_z-oZTCjWhKf-02W3xt938QRWk4AhGV1x-1FNQZ0aAj1jEALw_wcB) | *Industrial-grade durability*<br>*Includes temperature output*<br>*Long-term outdoor reliability* | *Higher cost*<br>*Requires analog-to-current interface circuitry* |

**Choice:** Option 2 — ST0160 Capacitive Soil Moisture Sensor V2.0  

**Rationale:** Provides corrosion-free sensing with stable analog output, ideal for long-term moisture monitoring in outdoor environments while maintaining low cost and simple integration with the PIC ADC.

---

## Temperature & Humidity Sensors

*Table 2: Temperature & Humidity Sensor Comparison*

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
| ![](https://m.media-amazon.com/images/I/51J9ha5fZKL._SX425_.jpg)<br>**Option 1:** DHT22 / AM2302 Sensor<br>$ — each<br>[link to product](https://www.amazon.com/HiLetgo-Temperature-Humidity-Electronic-Practice/dp/B01N9BA0O4?th=1) | *Low cost*<br>*Simple one-wire interface*<br>*Good community support* | *Slow sampling rate*<br>*Limited accuracy (±2 °C, ±5 % RH)* |
| ![](https://cdn-shop.adafruit.com/970x728/2857-03.jpg)<br>**Option 2:** Adafruit Sensirion SHT31-D Sensor (I²C)<br>$ — each<br>[link to product](https://www.adafruit.com/product/2857?gad_source=1&gad_campaignid=21079227318&gbraid=0AAAAADx9JvRao8jpCtH97p0BS1kvCOCfs&gclid=Cj0KCQjwjL3HBhCgARIsAPUg7a6aRmfh7hVts6f-NzgjwWEcrnFF6SG6mYFPvHJF_5_NLzgAmvnoko8aAptiEALw_wcB) | *High accuracy (±0.3 °C, ±2 % RH)*<br>*I²C communication*<br>*Fast response time* | *Moderate cost*<br>*Requires I²C pins on MCU* |
| ![](https://m.media-amazon.com/images/I/71Z1V1E1iNL._SX425_.jpg)<br>**Option 3:** SHT45 Precision Temperature Humidity Module<br>$ — each<br>[link to product](https://www.amazon.com/Precision-Temperature-Humidity-Interface-Breakout/dp/B0F1T4FM37/ref=sr_1_5?crid=2VJIOX6WRDNSV&dib=eyJ2IjoiMSJ9.zLBsVEuSKpEuyBZVms1dVu0643-k49KWv2t-UJYjMxNGQcBPK1_THaOCvx9d6-2-ntkOCHWHa7Rdj9jf1VsCOK43UwYetYYVvY5T-MND0ftnXYeAf6bon6pU6m5dubFih_55ThChYhZLtXHg5aTiAKZXexRsSKD_ONrPuilh63rLFCSjnOHcOfUEDkzDDCb2BSlUocbAAWiidhY3d8GbziNRZ7AfDPOkyjFCQxTitOA.4fzmUt8u5s_igziwHNm6q_OWwX7cZa_uKZrncxJJp5g&dib_tag=se&keywords=high+precision+temp+humidity+sensor&qid=1760576969&sprefix=high+percision+temp+humidity+sensor%2Caps%2C115&sr=8-5) | *Very high precision (±0.1 °C, ±1 % RH)*<br>*Low power consumption*<br>*Compact form factor* | *Higher price*<br>*May require fine-pitch connector or adapter* |

**Choice:** Option 2 — Adafruit Sensirion SHT31-D Sensor  

**Rationale:** Offers a balance between precision, power efficiency, and integration simplicity using I²C communication, aligning well with the PIC18F16Q41’s peripheral support.

---

## Rain Sensors

*Table 3: Rain Sensor Comparison*

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/001/169/089/MFG_ST0247_sml%28200x200%29.jpg)<br>**Option 1:** ST0247 Raindrop Detection Sensor Module<br>$ — each<br>[link to product](https://www.digikey.com/en/products/detail/sunfounder/ST0247/22116808?gclsrc=aw.ds&gad_source=1&gad_campaignid=20243136172&gbraid=0AAAAADrbLljjqP1OlpuYdh5M1W-hfUbv9&gclid=Cj0KCQjwjL3HBhCgARIsAPUg7a7lPwbIinfl1HWkQD0m-_1eTPRBahGmL4eiiv88jQ6CN0GsMBAA35UaAuRsEALw_wcB) | *Low cost and easy to interface*<br>*Analog and digital outputs* | *Susceptible to corrosion and false positives*<br>*Not quantitative* |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/003/217/526/MFG_SEN0545_sml%28200x200%29.jpg)<br>**Option 2:** SEN0545 Rain Sensor (UART Output)<br>$ — each<br>[link to product](https://www.digikey.com/en/products/detail/dfrobot/SEN0545/18069212?gclsrc=aw.ds&gad_source=1&gad_campaignid=20232005509&gbraid=0AAAAADrbLliHISOuiELCQaQga1eaoIOmc&gclid=Cj0KCQjwjL3HBhCgARIsAPUg7a5ib2a6vLSE00kvNW-UBVDEF8pqLx0DSEHB3ZOGEL2FSJWKz9Z_23gaAmehEALw_wcB) | *Digital UART interface*<br>*Corrosion-resistant coating*<br>*Stable signal processing built-in* | *Slightly higher cost*<br>*Requires UART parsing logic* |
| ![](https://ae-pic-a1.aliexpress-media.com/kf/Sc002d2b6c540434aa2b6636900dfaa44D.jpg_640x640q75.jpg_.avif)<br>**Option 3:** Optical Rain Gauge Sensor (RS485 Pulse Output)<br>$ — each<br>[link to product]([URL](https://www.aliexpress.com/p/tesla-landing/index.html?scenario=c_ppc_item_bridge&productId=3256809806842311&_immersiveMode=true&withMainCard=true&src=google&aff_platform=true&isdl=y&src=google&albch=shopping&acnt=708-803-3821&isdl=y&slnk=&plac=&mtctp=&albbt=Google_7_shopping&aff_platform=google&aff_short_key=UneMJZVf&gclsrc=aw.ds&&albagn=888888&&ds_e_adid=&ds_e_matchtype=&ds_e_device=c&ds_e_network=x&ds_e_product_group_id=&ds_e_product_id=en3256809806842311&ds_e_product_merchant_id=5561010287&ds_e_product_country=US&ds_e_product_language=en&ds_e_product_channel=online&ds_e_product_store_id=&ds_url_v=2&albcp=19108282527&albag=&isSmbAutoCall=false&needSmbHouyi=false&gad_source=1&gad_campaignid=19108284222&gbraid=0AAAAAD6I-hFTzxHMvC0P7g7-KEDZyVPXJ&gclid=Cj0KCQjwjL3HBhCgARIsAPUg7a5OO4ZGq7sFIcbFeqVzzmS34YxdUDmL9Aym0eGSSBtH2n28LKDXv14aAmETEALw_wcB)) | *Industrial precision and long lifetime*<br>*Non-contact optical detection* | *High price*<br>*Requires RS485 interface and external housing* |

**Choice:** Option 2 — SEN0545 Rain Sensor (UART Output)  

**Rationale:** Provides reliable digital output with minimal maintenance and better environmental resistance than basic analog boards, while avoiding the complexity and cost of industrial RS485 systems.

---

## Voltage Regulator (9 V → 5 V)

*Table 4: Voltage Regulator Comparison*

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/300/415/110/497%7ETO220-3TO220AB%7E%7E3_sml.jpg)<br>**Option 1:** LM7805 Linear Regulator<br>$ — each<br>[link to product](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805ACV/585962?gclsrc=aw.ds&gad_source=1&gad_campaignid=20509815359&gbraid=0AAAAADrbLlhRNmrlatu8xAxdWtHI80ley&gclid=Cj0KCQjwjL3HBhCgARIsAPUg7a7KnZXvXwXNpi7chQOzYTkAFFRfNkGRiLEYhx7zuVN-bOktpTwngCAaAm3zEALw_wcB) | *Simple design*<br>*Low noise*<br>*Stable 5 V output* | *Inefficient when dropping 9 V to 5 V*<br>*Generates heat at higher currents* |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/001/202/809/296%7E4040001-2%7ELP%7E3_sml%28200x200%29.jpg)<br>**Option 2:** UA78L05ACLP <br>$ — each<br>[link to product](https://www.digikey.com/en/products/detail/texas-instruments/UA78L05ACLP/13465029) | *High efficiency*<br>*Cooler operation*<br>*Can handle higher currents* | *Slight switching noise*<br>*More complex layout* |

**Choice:** Option 1 — LM7805 Linear Regulator  

**Rationale:** System current is low (< 150 mA) so the LM7805 offers sufficient efficiency with low noise, ideal for stable analog measurements on the sensor inputs.

---

## Microcontroller

**Component:** PIC18F16Q41 Curiosity Nano  
**Supply:** 5 V from LM7805 Regulator  

**Rationale:** Chosen for its low-power operation, built-in ADC channels for analog sensor inputs, I²C and UART support for digital sensors, and native compatibility with Microchip’s Curiosity Nano ecosystem for fast development and debugging.

