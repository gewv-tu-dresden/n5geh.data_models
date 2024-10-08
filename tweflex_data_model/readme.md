# Data Modells for the Project TWE-Flex

## Information on the data model
- Creation of the data models in the Jupyter Notebook [twe_flex_data_modell.ipynb](./twe_flex_data_modell.ipynb)
- JSON schema files [schemes](./schemes/) for the relevant entities

- The data model is based on NGSI-v2 and the VDI 3814 - 4.1
    - The ID of Entities is generated from the entity type and an ID, such as `entity-type:ID`
    - The ID of the attribute is given by a combination of 
        - the following parts:
            - Subcomponent (Part of the entity)
            - Type of data point
            - Position of the data point
        - with the following strucur: `subcomponent__data-point-type__data-point-position`

- An overview of the data points is provided in the following table

| Entity-Type             | Example Entity ID               | Description                     | Attribute ID                | Attribute Type | Data Type | Unit          | Description                                    |
|----------------------|--------------------------------|----------------------------------|--------------------------------|------------------|-------------|-----------------|---------------------------------------------------|
| `thermal_storage`    | `thermal_storage:001`          | Thermal Storage                  | `hw__temperature__20`           | attribute        | Number      | °C              | Temperature of the heating water in position at 20 per cent of the high of the thermal storage tank   |
|                      |                                |                                  | `hw__temperature__50`           | attribute        | Number      | °C              | Temperature of the heating water in position at 50 per cent of the high of the thermal storage tank   |
|                      |                                |                                  | `hw__temperature__80`           | attribute        | Number      | °C              | Temperature of the heating water in position at 50 per cent of the high of the thermal storage tank   |
|                      |                                |                                  | `hw__temperature__x`           | attribute        | Number      | °C              | Temperature at point x (numbering/height in %) (if more points are needed)   |
|                      |                                |                                  | `hw__volume`                   | static_attribute | Number      | m³              | Volume of heating water in storage    
|                      |                                |                                  |                                 |                  |              |                |                                                    |
| `dhw_installation`   | `dhw_installation:001`         | Domestic Hot Water Installation  | `dhw__temperature__in`         | attribute        | Number      | °C              | Inlet temperature of DHW                          |
|                      |                                |                                  | `dhw__temperature__out`        | attribute        | Number      | °C              | Outlet temperature of DHW                         |
|                      |                                |                                  | `dhw__temperature__x`          | attribute        | Number      | °C              | DHW temperature at a specific position            |
|                      |                                |                                  | `dhw__volumeflow`              | attribute        | Number      | m³/h            | Volume flow of DHW in the pipe |
|                      |                                |                                  |                                 |                  |              |                |                                                    |
| `dhw_installation`| `dhw_measuring_section:001`  | DHW Measuring Section Laboratory | `dhw__status__volumeflow`      | attribute        | Number      | -               | Status of which flow meter is used                |
|                      |                                |                                  | `tmb__temperature__x`          | attribute        | Number      | °C              | Temperature of the heat tape                      |
|                      |                                |                                  | `ambient__temperature__x`      | attribute        | Number      | °C              | Ambient temperature   |
|                      |                                |                                  |                                 |                  |              |                |                                                    |
| `dhw_installation`   | `dhw_distribution:001`         | DHW Distribution Laboratory      | `dhw__temperature__setpoint`   | attribute        | Number      | °C              | Setpoint temperature measurement                  |
|                      |                                |                                  | `dhw__temperature__setpoint`   | command          | Number      | °C              | Setpoint temperature for DHW                      |
|                      |                                |                                  | `dhw__status__measuring_section`| attribute        | Number      | -               | Status if the measuring section is flowing        |
|                      |                                |                                  | `dhw__status__bypass`          | attribute        | Number      | -               | Status if the bypass is flowing                   |
|                      |                                |                                  | `dhw__volumeflow__setpoint`    | attribute        | Number      | m³/h | l/min     | Setpoint volume flow measurement                  |
|                      |                                |                                  | `dhw__volumeflow__setpoint`    | command          | Number      | m³/h | l/min     | Setpoint volume flow                              |
|                      |                                |                                  |                                |                  |              |                |                                                    |
| `dhw_installation`   | `dhw_calculation:001`          | Calculated Values for DHW        | `dhw__temperature__mean`       | attribute        | Number      | °C              | Calculated temperature of DHW                     |
|                      |                                |                                  | `dhw__tapping`                 | attribute        | Number      | -               | Detection of tapping events                       |
|                      |                                |                                  | `calculation__time__temperature`| attribute       | Number      | SEC             | Calculation time for temperature                  |
|                      |                                |                                  | `calculation__time__tapping`   | attribute        | Number      | SEC             | Calculation time for tapping detection            |
|                      |                                |                                  |                                 |                  |              |                |                                                    |
| `temperature_maintenance_band`| `temperature_maintenance_band:001`      | temperature maintenance band / pipe heating system           | `electrical_input__resistance` | attribute        | Number      | Ohm             | Resistance of the heat tape                       |
|                      |                                |                                  | `electrical_input__voltage`    | attribute        | Number      | V               | Voltage of the heat tape                          |
|                      |                                |                                  | `electrical_input__current`    | attribute        | Number      | A               | Current of the heat tape                          |
|                      |                                |                                  | `electrical_input__power`      | attribute        | Number      | W               | Power of the heat tape                            |
|                      |                                |                                  | `electrical_input__energy`     | attribute        | Number      | Wh              | Energy consumption of the heat tape               |
|                      |                                |                                  | `operation__status`            | attribute        | Number      | -               | Operating status of the heat tape                 |
|                      |                                |                                  | `operation__status`            | command          | Number      | -               | Operating status of the heat tape                 |
|                      |                                |                                  | `operation__error`             | attribute        | Number      | -               | Error code                                        |
|                      |                                |                                  | `operation__warning`           | attribute        | Number      | -               | Warning code                                      |
|                      |                                |                                  | `operation__duty_cycle__lenght`| attribute       | Number      | s               | Length of the duty cycle                          |
|                      |                                |                                  | `operation__duty_cycle__active`| attribute       | Number      | %               | Active part of the duty cycle                     |
|                      |                                |                                  | `operation__duty_cycle__active`| command          | Number      | %               | Active part of the duty cycle                     |
|                      |                                |                                  | `calculation_coefficient__length`| static_attribute | Number    | m               | Length of the heat tape                           |
|                      |                                |                                  | `calculation_coefficient__resistance`| static_attribute | StructuredValue | - | Coefficients for calculation from resistance to temperature |
|                      |                                |                                  | `calculation_coefficient__temperature`| static_attribute | StructuredValue | - | Coefficients for calculation from temperature to DHW temperature |
|                      |                                |                                  | `dhw__temperature`             | attribute       | Number      | °C              | Measurement point for DHW temperature             |
|                      |                                |                                  |                                 |                  |              |                |                                                    |
| `heat_meter`         | `heat_meter:001`               | Heat Meter                       | `heat__temperature__in`         | attribute        | Number      | °C              | Inlet temperature                                 |
|                      |                                |                                  | `heat__temperature__out`        | attribute        | Number      | °C              | Outlet temperature                                |
|                      |                                |                                  | `heat__volumeflow`              | attribute        | Number      | m³/h or l/min     | Volume flow                                       |
|                      |                                |                                  | `heat__power`                   | attribute        | Number      | W or kW          | Heat power                                        |
|                      |                                |                                  | `heat__energy`                  | attribute        | Number      | kWh | MWh        | Heat energy / thermal energy                      |

## Related projects

- EnOB: TWE-Flex - Optimisation and flexibilisation of domestic hot water heating systems <br>
<a href="https://n5geh.de/twe-flex/"> Project Website </a>

- EnOB: N5GEH-Serv - National 5G Energy Hub <br>
<a href="https://n5geh.de/"> <img alt="National 5G Energy Hub" 
src="https://avatars.githubusercontent.com/u/43948851?s=200&v=4" height="150"></a>

## Acknowledgments

We gratefully acknowledge the financial support of the Federal Ministry <br> 
for Economic Affairs and Climate Action (BMWK), promotional reference 03EN1056A-B.

<a href="https://www.bmwi.de/Navigation/EN/Home/home.html"> <img alt="BMWK" 
src="https://raw.githubusercontent.com/RWTH-EBC/FiLiP/master/docs/logos/bmwi_logo_en.png" height="100"> </a>