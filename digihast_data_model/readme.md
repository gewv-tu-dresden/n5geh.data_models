# Data Modells for the Project DIGiHAST

## Information on the data model

- Creation of the data models in the Jupyter Notebook [datenmodell.ipynb](./datenmodell.ipynb)
- The data model is based on NGSI-v2 and partially on DIN ISO/TS 81346-2 (Only the equipment labels were adopted)
  - The ID of Entities is generated from the entity type and an ID, such as `entity-type:ID`
  - The ID of the attribute represents meter/measerung device ID

- An overview of the data points is provided in the following table

| Entity-Type      | Example Entity ID        | Description                    | Attribute ID           | Attribute Type   | Data Type     | Unit   | Description                                             |
|------------------|--------------------------|--------------------------------|------------------------|------------------|---------------|--------|---------------------------------------------------------|
| `BJ`             | `BJ:71799655`            | Heat Meter of DH Substation    | `fwtemp`               | attribute        | Number        | °C     | Supply temperature of the substation primary side       |
|                  |                          |                                | `rttemp`               | attribute        | Number        | °C     | Return temperature of the substation primary side       |
|                  |                          |                                | `flow`                 | attribute        | Number        | m³/h   | Flow of the substation primary side                     |
|                  |                          |                                | `power`                | attribute        | Number        | kW     | Power of the substation primary side                    |
|                  |                          |                                | `volume`               | attribute        | Number        | m³     | Volume of the substation primary side                   |
|                  |                          |                                | `energy`               | attribute        | Number        | kWh    | Energy of the substation primary side                   |
|                  |                          |                                | `ref_entity`           | static_attribute | Relationship  |        | Reference to the entity                                 |
|                  |                          |                                |                        |                  |               |        |                                                         |
| `BT`             | `BT:001001`              | temperature sensor             | `temperature`          | attribute        | Number        | °C     | Temperature Sensor                                      |
|                  |                          |                                | `ref_entity`           | static_attribute | Relationship  |        | Reference to the entity                                 |
|                  |                          |                                |                        |                  |               |        |                                                         |
| `BP`             | `BP:002001`              | pressure sensor                | `pressure`             | attribute        | Number        | bar    | Pressure Sensor                                         |
|                  |                          |                                | `ref_entity`           | static_attribute | Relationship  |        | Reference to the entity                                 |
|                  |                          |                                |                        |                  |               |        |                                                         |
| `BF`             | `BF:006001`              | flow sensor                    | `pressure`             | attribute        | Number        | m³/h   | Flow Sensor                                             |
|                  |                          |                                | `ref_entity`           | static_attribute | Relationship  |        | Reference to the entity                                 |
|                  |                          |                                |                        |                  |               |        |                                                         |
| `BS`             | `BS:600225`              | rotational frequency           | `rotational_frequency` | attribute        | Number        | rpm    | Rotational Frequency                                    |
|                  |                          |                                | `ref_entity`           | static_attribute | Relationship  |        | Reference to the entity                                 |
|                  |                          |                                |                        |                  |               |        |                                                         |
| `iHAST`          | `iHAST:1`                |  DH Substation                 | `fwtemp_tcr`           | static_attribute | Number        | °C     | Technical connection regulations for supply temperature |
|                  |                          |                                | `rttemp_tcr`           | static_attribute | Number        | °C     | Technical connection regulations for return temperature |
|                  |                          |                                | `design_flow`          | static_attribute | Number        | m³/h   | Design flow of the substation                           |
|                  |                          |                                | `connected_load`       | static_attribute | Number        | kW     | Connected Load of the substation                        |
|                  |                          |                                | `address`              | static_attribute | PostalAddress |        | Address of the substation                               |
|                  |                          |                                | `location`             | static_attribute | Location      |        | Location (GPS coordinates) of the substation            |
|                  |                          |                                |                        |                  |               |        |                                                         |
| `iKNOTEN`        | `iKNOTEN:1`              |  DH Node                       | `location`             | static_attribute | Location      |        | Location (GPS coordinates) of the Node                  |

## Related projects

- EnOB: Digitization of heat transfer in house stations and network nodes <br>
<a href="https://n5geh.de/digihast/"> <img alt="National 5G Energy Hub" 
src="https://cloudstore.zih.tu-dresden.de/index.php/s/ZZiFLQC6bisxqds/preview" height="150"> </a>

- EnOB: N5GEH-Serv - National 5G Energy Hub <br>
<a href="https://n5geh.de/"> <img alt="National 5G Energy Hub" 
src="https://avatars.githubusercontent.com/u/43948851?s=200&v=4" height="150"></a>

## Acknowledgments

We gratefully acknowledge the financial support of the Federal Ministry <br> 
for Economic Affairs and Climate Action (BMWK), promotional reference 03EN3056A-C.

<a href="https://www.bmwi.de/Navigation/EN/Home/home.html"> <img alt="BMWK" 
src="https://raw.githubusercontent.com/RWTH-EBC/FiLiP/master/docs/logos/bmwi_logo_en.png" height="100"> </a>