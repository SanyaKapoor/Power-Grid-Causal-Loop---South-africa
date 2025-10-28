```mermaid
graph TB
    %% Technical Variables
    ElecGen[Electricity Generation Capacity]
    CoalGen[Coal Generation]
    RenewGen[Renewable Generation]
    GridReliab[Grid Reliability]
    LoadShed[Load Shedding Frequency]
    Demand[Electricity Demand]
    InfraMaint[Infrastructure Maintenance]
    
    %% Economic Variables
    ElecPrice[Electricity Prices]
    InvestRenew[Investment in Renewables]
    EconGrowth[Economic Growth]
    UtilRevenue[Utility Revenue]
    
    %% Social Variables
    PopGrowth[Population Growth]
    Indust[Industrial Activity]
    QualLife[Quality of Life]
    PubTrust[Public Trust in Utility]
    EnergyPov[Energy Poverty]
    
    %% Environmental Variables
    CO2Emiss[CO2 Emissions]
    AirPollut[Air Pollution]
    HealthImpact[Public Health Impact]
    ClimateImpact[Climate Change Impact]
    WaterAvail[Water Availability]
    CoalRes[Coal Resource Depletion]
    
    %% Policy Variables
    CarbonTax[Carbon Tax/Regulations]
    RenewSubsidy[Renewable Subsidies]
    
    %% R1: Coal Dependency Reinforcing Loop
    CoalGen -->|+| ElecGen
    ElecGen -->|+| GridReliab
    GridReliab -->|-| LoadShed
    LoadShed -->|-| EconGrowth
    EconGrowth -->|+| Demand
    Demand -->|+| CoalGen
    
    %% R2: Economic Growth Reinforcing Loop
    GridReliab -->|+| EconGrowth
    EconGrowth -->|+| Indust
    Indust -->|+| Demand
    Demand -->|+| UtilRevenue
    UtilRevenue -->|+| InfraMaint
    InfraMaint -->|+| GridReliab
    
    %% R3: Renewable Investment Reinforcing Loop
    RenewGen -->|+| GridReliab
    GridReliab -->|+| PubTrust
    PubTrust -->|+| RenewSubsidy
    RenewSubsidy -->|+| InvestRenew
    InvestRenew -->|+| RenewGen
    
    %% R4: Degradation Reinforcing Loop
    LoadShed -->|-| PubTrust
    PubTrust -->|-| UtilRevenue
    UtilRevenue -->|-| InfraMaint
    InfraMaint -->|-| GridReliab
    GridReliab -->|+| LoadShed
    
    %% B1: Price Balancing Loop
    Demand -->|+| ElecPrice
    ElecPrice -->|-| Demand
    
    %% B2: Environmental Regulation Balancing Loop
    CoalGen -->|+| CO2Emiss
    CO2Emiss -->|+| ClimateImpact
    ClimateImpact -->|+| CarbonTax
    CarbonTax -->|-| CoalGen
    
    %% B3: Resource Constraint Balancing Loop
    CoalGen -->|+| CoalRes
    CoalRes -->|-| CoalGen
    
    %% B4: Health Feedback Loop
    CoalGen -->|+| AirPollut
    AirPollut -->|+| HealthImpact
    HealthImpact -->|-| QualLife
    QualLife -->|-| Indust
    Indust -->|-| Demand
    
    %% Additional Connections
    ElecGen -->|+| CO2Emiss
    RenewGen -->|-| CO2Emiss
    PopGrowth -->|+| Demand
    ElecPrice -->|+| EnergyPov
    EnergyPov -->|-| QualLife
    CoalGen -->|+| WaterAvail
    WaterAvail -->|-| CoalGen
    ClimateImpact -->|-| WaterAvail
    LoadShed -->|+| EnergyPov
    
    %% Revenue connections
    ElecPrice -->|+| UtilRevenue
    InvestRenew -->|+| ElecGen
    
    classDef technical fill:#e1f5ff,stroke:#333,stroke-width:2px
    classDef social fill:#ffe1f5,stroke:#333,stroke-width:2px
    classDef environmental fill:#e1ffe1,stroke:#333,stroke-width:2px
    classDef economic fill:#fff5e1,stroke:#333,stroke-width:2px
    
    class ElecGen,CoalGen,RenewGen,GridReliab,LoadShed,InfraMaint technical
    class PopGrowth,QualLife,PubTrust,EnergyPov social
    class CO2Emiss,AirPollut,HealthImpact,ClimateImpact,WaterAvail,CoalRes environmental
    class ElecPrice,InvestRenew,EconGrowth,UtilRevenue,Indust,Demand,CarbonTax,RenewSubsidy economic
