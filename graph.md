```mermaid
graph TB
    %% Technical Variables
    GridReliab[Grid Reliability]
    LoadShed[Load Shedding]
    EskomCoal[Coal Power Production by Eskom]
    CoalMining[Coal Mining]
    SolarGen[Solar Power Generation]
    WindGen[Wind Power Generation]
    NuclearGen[Nuclear Power Generation]
    RenewGen[Renewable Power Generation]
    InfraEff[Efficiency of Existing Infrastructure]
    UseExistInfra[Use of Existing Infrastructure]
    
    %% Economic Variables
    ElecDemand[Electricity Demand]
    GDPGrowth[GDP Growth]
    EnergyTariffs[Energy Tariffs]
    ElecPrice[Electricity Price for Consumers]
    PrivateInvest[Private Investment in New Generation]
    Employment[Employment in Existing Industries]
    JobCreation[Job Creation]
    Productivity[Productivity of Industries]
    CoalCost[Cost to Produce Coal]
    CoalEcon[Coal Extraction Economies of Scale]
    SolarCost[Solar Capital Cost]
    Affordability[Affordability]
    Poverty[Poverty]
    
    %% Social/Political Variables
    Population[Population]
    BirthRate[Birth Rate]
    DeathRate[Death Rate]
    PublicTrust[Public Trust]
    EskomConfidence[Public Confidence in Eskom]
    HealthStrain[Healthcare System Strain]
    PolicyCoal[Political/Policy Support for Coal]
    PolicyRenew[Policy Support for Renewables]
    RenewSubsidy[Subsidies to Promote Renewables]
    NegPerception[Negative Public Perception/Safety Concerns Nuclear]
    PoliticalRisk[Political Risk]
    
    %% Environmental Variables
    CarbonEmiss[Carbon Emissions]
    AirPollut[Air Pollution]
    LandPollut[Land Pollution]
    WaterAvail[Water Availability]
    ResDeplete[Resource Depletion]
    WasteManage[Waste Management & Regulatory Oversight]
    ClimateChange[Weather Extremities/Climate Change]
    Irradiance[Irradiance]
    WindSpeed[Wind Speeds]
    SolarResource[Solar Resource Availability]
    WindResource[Wind Resource Availability]
    LandSolar[Land Availability for Solar Fields]
    LandWind[Land Availability for Wind Farms]
    Agriculture[Agriculture]
    CarbonTax[Carbon Taxation]
    EnergyTax[Energy Taxation]
    
    %% R1: Coal Dependency & Economic Growth Loop
    EskomCoal -->|+| GridReliab
    GridReliab -->|-| LoadShed
    LoadShed -->|-| Productivity
    Productivity -->|+| GDPGrowth
    GDPGrowth -->|+| ElecDemand
    ElecDemand -->|+| EskomCoal
    
    %% R2: Infrastructure Efficiency Reinforcing
    UseExistInfra -->|+| InfraEff
    InfraEff -->|+| GridReliab
    GridReliab -->|+| EskomConfidence
    EskomConfidence -->|+| PublicTrust
    PublicTrust -->|+| EnergyTariffs
    EnergyTariffs -->|+| UseExistInfra
    
    %% R3: Coal Economies of Scale
    CoalMining -->|+| CoalEcon
    CoalEcon -->|-| CoalCost
    CoalCost -->|-| EskomCoal
    EskomCoal -->|+| CoalMining
    
    %% R4: Renewable Investment Loop
    RenewGen -->|+| GridReliab
    GridReliab -->|+| PublicTrust
    PublicTrust -->|+| PolicyRenew
    PolicyRenew -->|+| RenewSubsidy
    RenewSubsidy -->|+| PrivateInvest
    PrivateInvest -->|+| RenewGen
    
    %% R5: Eskom Confidence Degradation
    LoadShed -->|-| EskomConfidence
    EskomConfidence -->|-| EnergyTariffs
    EnergyTariffs -->|-| UseExistInfra
    UseExistInfra -->|-| InfraEff
    InfraEff -->|-| GridReliab
    GridReliab -->|+| LoadShed
    
    %% R6: Job Loss Spiral
    LoadShed -->|-| Employment
    Employment -->|-| GDPGrowth
    GDPGrowth -->|-| JobCreation
    JobCreation -->|-| ElecDemand
    
    %% R7: Renewable Cost Decline
    PrivateInvest -->|+| SolarGen
    SolarGen -->|-| SolarCost
    SolarCost -->|+| PrivateInvest
    
    %% B1: Price Demand Balance
    ElecDemand -->|+| ElecPrice
    ElecPrice -->|-| Affordability
    Affordability -->|-| ElecDemand
    
    %% B2: Carbon Regulation
    EskomCoal -->|+| CarbonEmiss
    CarbonEmiss -->|+| ClimateChange
    ClimateChange -->|+| CarbonTax
    CarbonTax -->|-| PolicyCoal
    PolicyCoal -->|+| EskomCoal
    
    %% B3: Air Quality Health
    EskomCoal -->|+| AirPollut
    AirPollut -->|+| HealthStrain
    HealthStrain -->|+| DeathRate
    DeathRate -->|-| Population
    Population -->|+| ElecDemand
    
    %% B4: Water Constraint
    EskomCoal -->|-| WaterAvail
    WaterAvail -->|-| EskomCoal
    ClimateChange -->|-| WaterAvail
    
    %% B5: Resource Depletion
    CoalMining -->|+| ResDeplete
    ResDeplete -->|-| CoalMining
    
    %% B6: Land Competition
    SolarGen -->|-| LandSolar
    LandSolar -->|-| Agriculture
    Agriculture -->|-| SolarGen
    
    %% B7: Poverty-Affordability
    ElecPrice -->|+| Poverty
    Poverty -->|-| Affordability
    
    %% Additional Key Connections
    SolarGen -->|+| RenewGen
    WindGen -->|+| RenewGen
    Irradiance -->|+| SolarResource
    SolarResource -->|+| SolarGen
    WindSpeed -->|+| WindResource
    WindResource -->|+| WindGen
    ClimateChange -->|-| WindSpeed
    ClimateChange -->|+| Irradiance
    
    NuclearGen -->|+| GridReliab
    NuclearGen -->|+| NegPerception
    NegPerception -->|-| PolicyRenew
    
    CoalMining -->|+| LandPollut
    LandPollut -->|-| Agriculture
    
    EskomCoal -->|+| Employment
    RenewGen -->|+| JobCreation
    
    PrivateInvest -->|-| PoliticalRisk
    LoadShed -->|+| PoliticalRisk
    
    EnergyTariffs -->|+| ElecPrice
    WasteManage -->|-| LandPollut
    
    PolicyCoal -->|+| UseExistInfra
    
    %% Population dynamics
    BirthRate -->|+| Population
    
    %% Poverty impact on health
    Poverty -->|+| DeathRate
    
    classDef technical fill:#e1f5ff,stroke:#333,stroke-width:2px
    classDef social fill:#ffe1f5,stroke:#333,stroke-width:2px
    classDef environmental fill:#e1ffe1,stroke:#333,stroke-width:2px
    classDef economic fill:#fff5e1,stroke:#333,stroke-width:2px
    
    class GridReliab,LoadShed,EskomCoal,CoalMining,SolarGen,WindGen,NuclearGen,RenewGen,InfraEff,UseExistInfra technical
    class Population,BirthRate,DeathRate,PublicTrust,EskomConfidence,HealthStrain,PolicyCoal,PolicyRenew,NegPerception,PoliticalRisk social
    class CarbonEmiss,AirPollut,LandPollut,WaterAvail,ResDeplete,WasteManage,ClimateChange,Irradiance,WindSpeed,SolarResource,WindResource,LandSolar,LandWind,Agriculture environmental
    class ElecDemand,GDPGrowth,EnergyTariffs,ElecPrice,PrivateInvest,Employment,JobCreation,Productivity,CoalCost,CoalEcon,SolarCost,Affordability,Poverty,CarbonTax,EnergyTax,RenewSubsidy economic
