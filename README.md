# F1-Racing-Project
### What is it?
The project aims to analyse the dominant drivers and teams in the Formula1 racing championship over several races throughout the year. Leveraging Azure Cloud Storages and Databricks datalakehouse capabilities the source files are transformed to meaningful insights. 
### About F1
Formula 1 is an annual, global motorsport championship. It involves high-speed races between single-seat, open-wheel cars. These races, called Grands Prix, occur on dedicated race tracks and street circuits worldwide. Teams compete for both Drivers' and Constructors' World Championships across a season. Formula 1 season happens once a year, woughly over 20 races. Each race happens over a weekend. 

There are various race circuits. Usually there is only one race in a circuit each year. There are 10 teams that participate in each season and they are called constructors in Formula 1. Each team has 2 drivers and each driiver is assigned a specific car. There is a qualifying session on Saturday afternoon and it happens over three different stages. The qualifying results decide the grid position of the driver as to where he'll start the race.

Unlike qualifying sessions, which are decided over a single lap, races span multiple laps, roughly between 50 and 70 laps, depending on the length of the circuit. Also during the race, drivers make pit stops to change the tires or to replace the damaged car. Based on the race results, Drivers and constructors standings are decided. Whichever driver is on the top of the standings at the end of the season is the drivers champion. And similarly, the team that's leading the constructors standings becomes the Constructors champion.
### Architecture
<img width="1128" alt="image" src="https://github.com/user-attachments/assets/1ca43c12-d9c3-4e94-a811-c199183ff5d9" />

### Data Ingestion
Raw Formula 1 data, sourced from the Ergast API (CSV and JSON formats), is ingested into an Azure Data Lake Storage (ADLS) raw container. Files are stored for specific race dates (Folder -- '2021-03-21 ' contains all the historical data for the races, this data is being fully loaded, files ingested post this date will be incremental loads).

<img width="1128" alt="image" src="https://github.com/user-attachments/assets/10e643cd-3147-4541-a1a6-cd54477a75de" />

### Data Transformation
Transformations on the raw data is implemented to provide: 
- individual race_results over the year
- Driver standings over the year
- Constructors standings over the year
The data is stored in delta tables, will be used for the final analysis views

<img width="1128" alt="image" src="https://github.com/user-attachments/assets/4118c4c4-c0d8-49b4-a73e-e7d165c321ba" />
<img width="1128" alt="image" src="https://github.com/user-attachments/assets/a5f53a30-6213-4709-9f41-55b1196a6a43" />

