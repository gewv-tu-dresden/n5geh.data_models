# Data Modells for the Project E³

Comments with ?? (for search)

- Creation of the data models in the Jupyter Notebook [e3_data_modell.ipynb](./e3_data_modell.ipynb)
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

| Entity-Type             | Example Entity ID               | Description                     | Attribute ID                 | Attribute Type | Data Type | Unit          | Description                                    |
|----------------------|--------------------------------|----------------------------------|--------------------------------|------------------|-------------|-----------------|---------------------------------------------------|
| `thermal_storage`    | `thermal_storage:001`          | Thermal Storage                  | `hw__temperature__20`           | attribute        | Number      | °C              | Temperature of the heating water in position at 20 per cent of the high of the thermal storage tank   |
|                      |                                |                                  | `hw__temperature__50`           | attribute        | Number      | °C              | Temperature of the heating water in position at 50 per cent of the high of the thermal storage tank   |
|                      |                                |                                  | `hw__temperature__80`           | attribute        | Number      | °C              | Temperature of the heating water in position at 50 per cent of the high of the thermal storage tank   |
|                      |                                |                                  | `hw__temperature__x`           | attribute        | Number      | °C              | Temperature at point x (numbering/height in %) (if more points are needed)   |
|                      |                                |                                  | `hw__volume`                   | static_attribute | Number      | m³              | Volume of heating water in storage      
|                      |                                |                                  |                                 |                  |              |                |                                                    |
| `heat_meter`         | `heat_meter:001`               | Heat Meter                       | `heat__temperature__in` (heat notwendig??)        | attribute        | Number      | °C              | Inlet temperature                                 |
|                      |                                |                                  | `heat__temperature__out`        | attribute        | Number      | °C              | Outlet temperature                                |
|                      |                                |                                  | `heat__volumeflow`              | attribute        | Number      | m³/h or l/min     | Volume flow                                       |
|                      |                                |                                  | `heat__power`                   | attribute        | Number      | W or kW          | Heat power                                        |
|                      |                                |                                  | `heat__energy`                  | attribute        | Number      | kWh | MWh        | Heat energy / thermal energy                      |
|                      |                                |                                  |                                 |                  |              |                |                                                    |
| `heat_transfer_station` | `heat_transfer_station:001`  | Heat Transfer Station          | `primary__temperature__in`    | attribute      | Number    | °C      | Primary side delivery temperature               |
|                         |                               |                                 | `primary__temperature__out`   | attribute      | Number    | °C      | Primary side return temperature                 |
|                         |                               |                                 | `primary__pressure__in`      | attribute      | Number    | Pa or bar(abs) | Pressure in primary side flow                    |
|                         |                               |                                 | `primary__pressure__out`     | attribute      | Number    | Pa or bar(abs) | Pressure in primary side return                  |
|                         |                               |                                 | `secondary__temperature__in`  | attribute      | Number    | °C      | Secondary side delivery temperature             |
|                         |                               |                                 | `secondary__temperature__out` | attribute      | Number    | °C      | Secondary side return temperature               |
|                         |                               |                                 | `secondary__volumeflow__in`  | attribute      | Number    | m³/h or l/min | Secondary side volume flow (Consumer)          |
|                         |                               |                                 | `secondary__volumeflow__out` | attribute      | Number    | m³/h or l/min | Secondary side volume flow (Prosumer)          |
|                         |                               |                                 | `operation__mode`            | command        | String / StructuredValue | - | Operating mode of the heat transfer station |
|                         |                               |                                 | `heat__power__rated`         | static_attribute | Number    | W or kW   | Rated power in the reference case               |
|                         |                               |                                 | `heat__power__setpoint`      | command        | Number / StructuredValue | W or kW | Setpoint power in the reference case            |
|                         |                               |                                 | `heat__temperature__setpoint`| command        | Number / StructuredValue | °C | Setpoint temperature in the reference case      |
|                         |                               |                                 | `heat__meter__in`            | Relationship  | heat_meter | -  | Heat meter for the reference case (Consumer)    |
|                         |                               |                                 | `heat__meter__out`           | Relationship  | heat_meter | -  | Heat meter for the reference case (Prosumer)    |
|                      |                                |                                  |                                 |                  |              |                |                                                    |
| `heating_circuit`       | `heating_circuit:001`         | Heating Circuit                | `heat__temperature__in`      | attribute      | Number    | °C      | Inlet temperature to heating circuit            |
|                         |                               |                                 | `heat__temperature__out`     | attribute      | Number    | °C      | Outlet temperature from heating circuit         |
|                         |                               |                                 | `heat__volumeflow`           | attribute      | Number    | m³/h or l/min | Volumetric flow rate through heating circuit    |
|                         |                               |                                 | `outdoor__temperature`       | attribute      | Number    | °C      | Outdoor temperature                              |
|                      |                                |                                  |                                 |                  |              |                |                                                    |
| `dhw_station`           | `dhw_station:001`             | DHW Station                    | `heat__temperature__in`      | attribute      | Number    | °C      | Inlet temperature of heating water to DHW station|
|                         |                               |                                 | `heat__temperature__out`     | attribute      | Number    | °C      | Outlet temperature of heating water from DHW station |
|                         |                               |                                 | `heat__volumeflow`           | attribute      | Number    | m³/h or l/min | Volumetric flow rate of heating water through DHW station |
|                         |                               |                                 | `dhw__temperature__in`       | attribute      | Number    | °C      | Inlet temperature of TWW to DHW station         |
|                         |                               |                                 | `dhw__temperature__out`      | attribute      | Number    | °C      | Outlet temperature of TWW from DHW
