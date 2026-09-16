---
title: OMA Smart Data Models Mapping for Water
description: Mapping between OMA LwM2M Objects and FIWARE Smart Data Models for smart water management.
layout: doc
---

# {{ $doc.title }}

- [**Reference Document**](https://groups.io/g/smartcities-sig/files/Discussion/2026/20260513-especificacion%20de%20caso%20de%20uso%20water%20v0.1.docx)  

## Quantities to be measured

- [X] Volume per unit of time (or during a time period indicated as the second value). Specify whether liters or cubic meters.
- [X] Time at which it was measured (time of completion, or start)
- [x] Temperature, pH and other environmental soil parameters
- [ ] Weather at that time
- [ ] Weather forecast at that time
- [x] Water pressure
- [ ] Additional characteristics of the water: recycled or potable…



## Data Models

- Water meter (OMA) Object [#3424](https://github.com/OpenMobileAlliance/lwm2m-registry/blob/prod/3424.xml)
    -The water pressure could be possibly added to the OMA Data Model

- Water quality sensor (OMA) Object [#3426](https://github.com/OpenMobileAlliance/lwm2m-registry/blob/prod/3426.xml)

- Pressure monitoring sensor (OMA) [#3427](https://github.com/OpenMobileAlliance/lwm2m-registry/blob/prod/3427.xml)

- [WaterConsumptionObserved (Smart Data Models)](https://github.com/smart-data-models/dataModel.WaterConsumption/blob/master/WaterConsumptionObserved/doc/spec.md)

- [WaterDistributionNetwork (Smart Data Models)](https://github.com/smart-data-models/dataModel.WaterDistribution/blob/master/WaterDistributionNetwork/doc/spec.md)

- [AgriParcelRecord (Smart Data Model)](https://github.com/smart-data-models/dataModel.Agrifood/blob/master/AgriParcelRecord/doc/spec.md)

- [WeatherObserved  (Smart Data Model)](https://github.com/smart-data-models/dataModel.Weather/blob/master/WeatherObserved/doc/spec.md)



## Mappable information

| OMA                               | FIWARE                                       |
| --------------------------------- | -------------------------------------------- |
| Latitude (6/1) Longitude (6/2)    | WaterConsumptionObserved.location            |
| Cumulated water volume (3424/1)   | WaterConsumptionObserved.waterConsumption    |
| Timestamp (3424/5518)             | WaterConsumptionObserved.observationDateTime |
| Minimum  flow rate (3424/7)       | WaterConsumptionObserved.minFlow             |
| Maximum  flow rate (3424/8)       | WaterConsumptionObserved.maxFlow             |
| Leak  detected (3424/10)          | WaterConsumptionObserved.alarmStopsLeaks     |
| Fraud detected (3424/13)          | WaterConsumptionObserved.moduleTampered      |
| pH (3426/1 - WaterQuality object) | WaterConsumptionObserved.pHTSA               |
| Pressure (3427/1)                 | WaterDistributionNetwork.waterPressure       |
| Temperature (3303/5700)           | AgriParcelRecord.soilTemperature             |
| Acidity (3326/5700)               | TODO                                         |


### Tests

 - [OMA-ETS-uCIFI-Test-Cases-Smart-Water](https://github.com/OpenMobileAlliance/scwg-ETS-conformance-for-Smart-City/blob/Dev/ETS/uCIFI-Test-Cases-Smart-Water.md)
