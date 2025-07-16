# brazil
This repository contains a dataset on deforestation, children's health, and socioeconomic status in Brazil.

SOURCES OF DATA:
- Global Forest Watch (https://www.globalforestwatch.org/)
- DATASUS – Ministério da Saúde (https://datasus.saude.gov.br/)
- Agência de Notícias - IBGE (https://agenciadenoticias.ibge.gov.br/)
- Rorato, A. C., Dal’Asta, A. P., Lana, R. M., Dos Santos, R. B., Escada, M. I. S., Vogt, C. M., ... & Codeço, C. T. (2023). Trajetorias: a dataset of environmental, epidemiological, and economic indicators for the Brazilian Amazon. Scientific Data, 10(1), 65.

NOTE: Results that were not available from datasets are set as "NaN". All deforestation data outside the Amazon region is set to "NaN".

The struct "All_data" contains the following fields:

Fields that describe the geography of municipios:
- MunicipiosID: Numerical IDs of the municipios (5570 numerical entries);
Indices: 1st index: municipio.
- MunicipiosShortID: Short numerical IDs of the municipios (5570 numerical entries);
Indices: 1st index: municipio.
- MunicipiosName: Name of the municipios (5570 string entries);
Indices: 1st index: municipio.
- State: Abbreviation of the State to which the municipios belong (5570 string entries);
Indices: 1st index: municipio.
- MacroRegion: Macro-region of Brazil to which the municipios belong (5570 string entries);
Indices: 1st index: municipio.
- isAmazon: Whether the municipio is in the Legal Amazon region - 1: Yes (in Amazon); 0: No (not in Amazon) (5570 Boolean entries);
Indices: 1st index: municipio.
- Longitude: Longitude of the centroid of the municipios (5570 numerical entries);
Indices: 1st index: municipio.
- Latitude: Latitude of the centroid of the municipios (5570 numerical entries);
Indices: 1st index: municipio.
- Area: Area of municipios [ha] (5570 numerical entries);
Indices: 1st index: municipio.

Fields that describe the sociodemography and economics of municipios:
- Population: Total population of municipios by year (2002-2021), reconstructed from GDP computations (5570x20 numerical entries);
Indices: 1st index: municipio; 2nd index: year (2002-2021). 
- Demographics: Population of municipios by sex, race, and age range (2x2x6x5x5570 numerical entries);
Indices: 1st index: year of census (1: 2010; 2: 2022); 2nd index: sex (1:M; 2:F); 3rd index: race (1:Unknown; 2:Branca; 3:Preta; 4:Amarela; 5:Parda; 6:Indigena); 4th index: age range (1: <1 year; 2: 1-4 year; 3: 5-9 year; 4: 10-14 year; 5: 15-19 year); 5th index: municipio.
- IndigenousPopulation: Indigenous population of municipios by sex and age range (2x2x4x5570 numerical entries);
Indices: 1st index: year of census (1: 2010; 2: 2022); 2nd index: sex (1:M; 2:F); 3rd index: age range (1: 0-4 year; 2: 5-9 year; 3: 10-14 year; 4: 15-19 year); 4th index: municipio.
- GDP: Overall GDP and per capita GDP of municipios by year (2002-2021) (5570x20x2 numerical entries);
Indices: 1st index: municipio; 2nd index: year (2002-2021); 3rd index: variable selection (1: Overall GDP; 2: Per capita GDP)

Fields that describe deforestation: (all data outside Legal Amazon area is not defined and equal to NaN)
- TreeCover: Tree cover at 2 selected years and tree cover gain 2000-2020 in each municipios, for different thresholds for percent canopy cover levels (5570x3x8 numerical entries);
Indices: 1st index: municipio; 2nd index: variable selection (1: Tree cover 2000 [ha]; 2: Tree cover 2010 [ha]; 3: Gain 2000-2020 [ha]); 3rd index: Thresholds (1: 0; 2: 10; 3: 15; 4:20; 5:25; 6:30; 7:50; 8:75).
- TreeCoverLoss: Tree cover loss [ha] in municipios by year (2001-2022), for different thresholds for percent canopy cover levels (5570x22x8 numerical entries);
Indices: 1st index: municipio; 2nd index: year (2001-2022); 3rd index: Thresholds (1: 0; 2: 10; 3: 15; 4:20; 5:25; 6:30; 7:50; 8:75).
- PrimaryForestCover: Primary forest cover [ha] in municipios in 2000 (5570 numerical entries);
Indices: 1st index: municipio.
- PrimaryForestLoss: Primary forest cover loss and equivalent emissions in municipios by year (2001-2022) (5570x22x2 numerical entries);
Indices: 1st index: municipio; 2nd index: year (2001-2022); 3rd index: variable selection (1: primary forest cover loss [ha]; 2: equivalent CO2 emissions [Mg])

Fields that describe illnesses: (not all data are available for all years)
The number of people affected by illnesses/hospitalized/death are included here.
The following illnesses are considered: ACP; ATL; Chagas; Chickenpox; Chikungunya; CongenitalToxoplasmosis; Deaths; Dengue; Hospitalizations; Leprosy; Leptospirosis; Malaria; MeaslesRubella; Meningitis; Poisoning; Schistosomiasis; Tubercolosis; VenomousAnimals; VisceralLeishmaniasis; WhoopingCough; Zika; Typhoid.
All of the fields have the same structure: 
Indices: 1st index: Year (1995-2023); 2nd index: sex (1:M; 2:F); 3rd index: race (1:Unknown; 2:Branca; 3:Preta; 4:Amarela; 5:Parda; 6:Indigena); 4th index: age range (1: <1 year; 2: 1-4 year; 3: 5-9 year; 4: 10-14 year; 5: 15-19 year); 5th index: municipio.
