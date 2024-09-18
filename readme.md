# Examples of data models 
- This repo introduces examples of data models relating to building energy technology and district heating that have been developed through collaboration between the [E³](https://n5geh.de/e3/), [TWE-Flex](https://n5geh.de/twe-flex/) and [Digihast](https://n5geh.de/digihast/) projects in [N5GEH](https://n5geh.de/)

- The data models are based on [NGSI-v2](https://fiware-tutorials.readthedocs.io/en/latest/getting-started.html) from FIWARE and for documentation purposes are converted into [JSON Schema](https://json-schema.org/)

- The data models are created in Juptyter notebooks and saved as a JSON schema. The Python environment defined via Poetry ([`pyproject.toml`](./pyproject.toml)) can be used to run the notebooks. Install the virtual environment with [Poetry](https://python-poetry.org/): 
    ```
    poetry install
    ```
- A further overview of data models within the N5GEH can be found in the [n5geh.tutorials.data_model](https://github.com/N5GEH/n5geh.tutorials.data_model) repo. The use of JSON schema is also described further there.

## Contents
- [Data Model TWE-Flex](./tweflex_data_model/): Data model of domestic hot water heating with temperature maintenance band and district heating.
- [Data Model E³](./e3_data_model/): Data model of a heat supply system in a building with district heating connection and other energy sources with a bidirectional energy flow function
- [Data Model DIGiHAST](./digihast_data_model/): Data model from district heating network perspective of network nodes and digital house substations


## License

This project is licensed under the BSD-3-Clause license - see the [LICENSE](LICENSE) file for details.

## Copyright

<a href="https://tu-dresden.de/ing/maschinenwesen/iet/gewv"> <img alt="EBC" src="https://raw.githubusercontent.com/N5GEH/.github/main/logos/Logo-Banner-TUD-IET-GEWV.jpg" height="75"> </a>

2020-2024, TUD Dresden University of Technology, Chair of Building Energy Systems and Heat Supply

## Related projects

- EnOB: TWE-Flex - Optimisation and flexibilisation of domestic hot water heating systems <br>
<a href="https://n5geh.de/twe-flex/"> Project Website </a>

- EnEff: E³ - Low-emission and energy-efficient energy supply in urban areas using the latest intelligent ICT structures <br>
<a href="https://n5geh.de/e3/"> Project Website </a>

- EnEff: DIGiHAST - Digitalisation of heat transfer in house stations and network nodes <br>
<a href="https://n5geh.de/digihast/"> <img alt="National 5G Energy Hub" 
src="https://cloudstore.zih.tu-dresden.de/index.php/s/ZZiFLQC6bisxqds/preview" height="150"> </a>

- EnOB: N5GEH-Serv - National 5G Energy Hub <br>
<a href="https://n5geh.de/"> <img alt="National 5G Energy Hub" 
src="https://avatars.githubusercontent.com/u/43948851?s=200&v=4" height="150"></a>

## Acknowledgments

We gratefully acknowledge the financial support of the Federal Ministry for Economic Affairs and Climate Action (BMWK).

<a href="https://www.bmwi.de/Navigation/EN/Home/home.html"> <img alt="BMWK" 
src="https://raw.githubusercontent.com/RWTH-EBC/FiLiP/master/docs/logos/bmwi_logo_en.png" height="100"> </a>