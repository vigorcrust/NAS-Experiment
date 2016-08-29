# NAS-Experiment
Experiment of a Home NAS System

## Hardware
Replacement of my QNAP TS-410. I was quite happy with this NAS, but it has aged over the time and I am afraid that it will fail soon. So I need a replacement. Looking at available solutions from various distributors you end up having a solution which has the same performance as the old one at a high cost and they are not as flexible as a DIY NAS.

### Requirements
- min. 4 HDD drives + drive/USB for OS
- significant lower price than an of-the-shelf NAS
- low power consumption
- support container virtualisation
- Gbit LAN
- low noise
- free choice of OS
- max. 200mm (H) 400mm (D) (measurements of my shelf)
- low volume (less than 20,000 cm^2)
- front and rear USB ports
- extensible

### Components
All prices are taken on 29th August 2016 from a rough Google search.

| Component | Description                                                         | Amount | Price    |
| --------- | ------------------------------------------------------------------- | ------:| --------:|
| Mainboard | ASRock J3160-ITX SoC So.BGA Dual Channel DDR3 Mini-ITX (incl. CPU)  | 1      |  82.00 € |
| Memory    | 8GB (1x 8192MB) Kingston ValueRAM DDR3L-1600 SO-DIMM CL11-11 Single | 2      |  35.00 € |
| Case      | Antec ISK 600 Mini-ITX                                              | 1      |  50.00 € |
| PSU       | Be-Quiet! System Power B8 300W bulk                                 | 1      |  32.00 € |
| USB-Pen   | 64 GB SanDisk Ultra Fit schwarz USB 3.0 (NOT RECOMMENDED)\*         | 1      |  17.00 € |
\* Some versions of this USB stick have problems booting from it. (ex. [Using-a-Sandisk-Maybe-Don-t](https://neverware.zendesk.com/hc/en-us/articles/217440748-Using-a-Sandisk-Maybe-Don-t-))

So the basic system, without hard drives, costs around **251.00 €** (w/o shipping).

The reasons for the choice of components are the following:
- CPU: Intel® Quad-Core Pentium® J3160 (I use a N3700 with similar specs. w slightly less performance and power consumption)
  - 6.5W TDP low power consumption
  - 2157 PassMark Points
  - fanless
  - cheap
  - 4x SATA3 Ports
  - 4x USB 3.0 Ports; 2x USB 2.0 Ports (rear) + 1x USB 3.0 Port (front)
- Case: Antec ISK 600
  - 18,708 cm^2 volume (195mm (H) x 260mm (W) x 369mm (D))
  - Front USB connector
  - 2 x 2.5" HDD trays; 3 x 3.5" HDD trays; 1 x slim optical drive bay
- PSU: Be-Quiet! System Power B8
  - cheap
  - @20% load only 11,6 dB(A)
  - 4x 15-pin SATA power connector
  - 2x 4-pin PATA power connector

### Optional Components
| Component | Description                                                         | Price    |
| --------- | ------------------------------------------------------------------- | --------:|
| Drive     | SAMSUNG SN-506BB SATA (slim) - BluRay                               |  62.00 € |
| Cable 1   | SATA HD Molex 4 Pin to x2 15 Pin SATA Power Splitter Cable          |   5.00 € |
| Cable 2   | Slim SATA 13P to SATA 7P with 4-pin power Cable                     |   3.00 € |
| Adapter   | IO Crest Mini PCIe 2 Port SATA III RAID Controller (SI-MPE40095)    |  28.00 € |

- Drive: BluRay writer
  - import/export data
- Cable 1
  - Convert one 4-pin PATA to two 15-pin SATA power connectors totaling in 6 SATA power connectors
- Cable 2
  - Convert the other 4-pin PATA + SATA data connector to a combined adapter for slim drives
- Adapter
  - Use the Mini-PCIe connector to add two additional SATA devices totaling in 6 SATA devices
  - The PCI Express 2.0 x1 can be used but I leave it for other devices like network/SAS/USB/etc.

### Drives
I reuse my old 2TB hard drives and add initially one new 2TB drive and new ones as the old ones die.

| Component | Description                                                         | Price    |
| --------- | ------------------------------------------------------------------- | --------:|
| HDD       | 2000GB Seagate Momentus ST2000LM003 5.400U/min 32MB 2.5" SATA 6Gb/s |  91.00 € |

I know it's not the largest or best drive but the power consumption is 0.7W (idle) to 2.3W (read/write), which is quite good.

### Power consumption
I just used test reports and the information specified. So the power consumption is just an educated guess and not tested.

| Component        | Description               | Standby w WOL | Idle        | Load        |
| ---------------- | ------------------------- | -------------:| -----------:| -----------:|
| Basic System\*1  | Mainboard, CPU, RAM       |       3.0 W   |    17.5 W   |    25.0 W   |
| HDDs             | 5x HDD @80% efficency PSU |       4.4 W   |     4.4 W   |    14.4 W   |
| Aux. devices     | SATA controller, USB-Pen  |       0.6 W   |     3.1 W   |     5.6 W   |  
|                  | **NAS w/o optical drive** |     **8.0 W** |  **25.0 W** |  **45.0 W** |
| Drive            | BluRay\*2                 |       0.5 W   |     2.5 W   |    25.0 W   |

\*1: [technikaffe - a german comparison site](http://www.technikaffe.de/anleitung-324-asrock_n3700_itx_test_und_vergleich_mit_dem_asrock_n3150_itx)
\*2: [Specs BluRay](http://www.mydvddrives.com/sata-bd-rom-blu-ray-combo-drive-for-matshita-bd-cmb-uj160-104916.html)


### Round-up
| Component           | Description                                         | Price        |
| ------------------- | --------------------------------------------------- | ------------:|
| Basic System        | Mainboard, CPU, RAM, Case, PSU, USB-Pen             |   251.00 €   |
| Optional Components | BluRay, Cable 1, Cable 2, Adapter                   |    98.00 €   |
|                     | **NAS w/o hard drives**                             | **349.00 €** |
| HDDs                | 5x HDD 2TB@91.00€ + 3x SATA Cable@2.00€             |   461.00 €   |
|                     | **NAS w 10TB Storage Capability**                   | **810.00 €** |  

### Compair to commercial NAS solution

#### QNAP TS-569 Pro (old model)

| Features            | Commercial NAS   | This NAS        |
| ------------------- | -----------------| ---------------:|
| PassMark Points     | 844              |          2157   |
| RAM                 | 1GB              |          16GB   |
| Power Idle          | 46.7 W \*1       |        25.0 W   |
| Power Load          | 58.6 W \*1       |        45.0 W   |
| Price               | 829.00 € \*2     |      349.00 €   |

\*1: [techpowerup](https://www.techpowerup.com/reviews/Synology/DS416/16.html)
\*2: [Conrad Electronics](https://www.conrad.de/de/qnap-5-bay-nas-ts-569-pro-617621.html)

#### Thecus N5810 Pro

| Features            | Commercial NAS   | This NAS        |
| ------------------- | -----------------| ---------------:|
| PassMark Points     | 1884             |          2157   |
| RAM                 | 4GB              |          16GB   |
| Power Idle          | 35.1 W \*1       |        25.0 W   |
| Power Load          | 55.3 W \*1       |        45.0 W   |
| Price               | 589.00 € \*2     |      349.00 €   |

\*1: [techpowerup](https://www.techpowerup.com/reviews/Thecus/N5810_Pro/17.html)
\*2: [Cyberport](https://www.cyberport.de/?DEEP=3F38-08Y&APID=117&gclid=CjwKEAjwuo--BRDDws3x65LL7h8SJABEDuFRy-PzBnlgvtcQdT0JWjT7efEFRp2w8BRM9o4E_jCWYxoCZ6nw_wcB)

#### Synology DS916+
Just a 4-bay NAS

| Features            | Commercial NAS   | This NAS        |
| ------------------- | -----------------| ---------------:|
| PassMark Points     | 1891             |          2157   |
| RAM                 | 8GB              |          16GB   |
| Power Idle          | 29.7 W \*1       |        25.0 W   |
| Power Load          | 43.0 W \*1       |        45.0 W   |
| Price               | 571.00 € \*2     |      349.00 €   |

\*1: [techpowerup](https://www.techpowerup.com/reviews/Thecus/N5810_Pro/17.html)
\*2: [Geizhals](https://geizhals.de/synology-diskstation-ds916-a1439658.html)


## Software
