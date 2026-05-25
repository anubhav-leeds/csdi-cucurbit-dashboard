# **Composite Sowing Dates Index-informed cucurbit sowing-window climatic analogue dashboard**



This repository hosts a live, browser-based research dashboard for exploring \*\*Composite Sowing Dates Index-informed cucurbit sowing-window climatic analogues over India\*\*.



The dashboard translates field-experiment-derived crop response information into a spatial climate-screening layer using future climate model data. It is designed as a \*\*prototype research and visualisation tool\*\*, not as an operational farmer advisory system. Its purpose is to show where projected growing-window climates resemble the field-observed thermal conditions associated with relatively higher or lower Composite Sowing Dates Index values for selected cucurbit crops and sowing windows.



#### **## Live dashboard**



Open the dashboard here:



https://anubhav-leeds.github.io/csdi-cucurbit-dashboard/



The dashboard is hosted using GitHub Pages. The repository contains the dashboard HTML file and the supporting map images used by the interactive interface.



#### **## Scientific purpose**



Cucurbit crops are important warm-season vegetables in Indian horticulture, but their phenology, flowering, reproductive success, physiological performance, biochemical stress response, and yield are sensitive to temperature conditions during the crop-growing window. Sowing date is a low-cost agronomic intervention that can shift crop exposure to temperature, rainfall, and humidity conditions during sensitive growth stages.



This dashboard was developed to explore the following question:



> Where do future growing-window climates over India resemble the field-observed climate conditions associated with better or poorer Composite Sowing Dates Index performance in cucurbit crops?



The dashboard therefore links three components:



1\. field-experiment trait and index information;

2\. crop-specific sowing-window calendar definitions;

3\. gridded historical and future climate model data.



It does \*\*not\*\* directly predict yield, physiology, biochemistry, or field-observed Composite Sowing Dates Index at each grid cell. Instead, it maps \*\*climatic analogue suitability\*\*, meaning similarity between projected gridded climate conditions and the field conditions under which different index values were observed.



#### **## Crop and season coverage**



The dashboard covers four cucurbit species:



\- ridge gourd (\*Luffa acutangula\*);

\- bottle gourd (\*Lagenaria siceraria\*);

\- sponge gourd (\*Luffa cylindrica\*);

\- cucumber (\*Cucumis sativus\*).



It includes three season definitions:



\- Summer–Spring 1;

\- Kharif;

\- Summer–Spring 2.



For each season, three experimentally tested sowing-window classes are represented:



\- SD1: earliest or recommended tested sowing window;

\- SD2: delayed tested sowing window;

\- SD3: very delayed tested sowing window.



The dashboard should be interpreted only within these tested sowing-window classes. It does not estimate exact sowing dates outside the tested experimental windows.



#### **## Field-experiment basis**



The biological anchor for the dashboard is a field-experiment dataset in which four cucurbit species were evaluated across sowing windows and seasons using morphological, physiological, biochemical, reproductive, and yield-related traits.



The Composite Sowing Dates Index was developed as an extended composite index that integrates a broader set of traits than the earlier Composite Cucurbit Growth Index. The index uses normalised trait scores and component weights derived from the field-experiment framework.



The equation used for the Composite Sowing Dates Index is:



```text

Composite Sowing Dates Index =

0.340 × (CARB + AA + RL)

\+ 0.217 × (MF + MC)

\+ 0.142 × (TB + PR + LA)

\+ 0.122 × (M:F)

\+ 0.092 × (pH)

\+ 0.087 × (POX + SLA)



where:



CARB = carbohydrate;

AA = ascorbic acid;

RL = root length;

MF = male flowers;

MC = moisture content;

TB = total biomass;

PR = protein;

LA = leaf area;

M:F = male-to-female flower ratio;

pH = leaf pH;

POX = peroxidase enzyme activity;

SLA = specific leaf area.



Before applying the equation, all included trait values were normalised to a 0–1 scale. The normalisation was performed within each crop across all three seasons and all three sowing windows. This choice was used because the aim of the dashboard is to compare sowing-window and seasonal responses within each crop without allowing large inter-species differences in absolute trait magnitudes to dominate the index.



For most traits, higher values were treated as favourable. Two traits were treated as lower-is-better:



male-to-female flower ratio;

specific leaf area.



Peroxidase enzyme activity and leaf pH were treated as higher-is-better because they were interpreted as indicators of stress response or physiological functioning in the field-experiment context.



The grouped terms in the equation were used as written. This means that the final Composite Sowing Dates Index value itself may exceed 1. The important constraint is that the individual normalised trait scores lie between 0 and 1.



#### **Climate data source**



The climate data layer uses National Aeronautics and Space Administration Earth Exchange Global Daily Downscaled Projections, Coupled Model Intercomparison Project Phase 6.



The workflow used daily gridded data for:



maximum near-surface air temperature;

minimum near-surface air temperature;

precipitation.



The gridded data have approximately 0.25° × 0.25° spatial resolution. Daily files were processed over India using an India state-boundary-based land mask.



The dashboard includes:



historical baseline: 1985–2014;

future Shared Socioeconomic Pathway 2-4.5;

future Shared Socioeconomic Pathway 5-8.5;

mid-century period: 2041–2070;

late-century period: 2071–2100.



The dashboard provides an ensemble-median view and individual model views for the selected climate model set. The ensemble-median view should be treated as the main headline view. Individual models are included to show model-to-model spread and should be interpreted as sensitivity views.



#### **Climate metrics calculated**



For every grid cell, climate model, scenario, period, crop, season, and sowing window, the workflow extracted the crop growing-window climate based on the field-experiment sowing dates and crop-window durations.



The main climate variable used to construct the suitability score was growing-window mean temperature:



Mean temperature = (maximum temperature + minimum temperature) / 2



Precipitation totals, growing degree days, hot-day counts, and related window metrics were also generated as diagnostic information in the processing workflow, but the main dashboard suitability score is a thermal analogue score.



Growing Degree Days were calculated using a base temperature of 15.5 °C:



Growing Degree Days = sum(max(mean temperature - 15.5, 0))

Composite Sowing Dates Index-informed thermal analogue suitability score



The dashboard does not map the raw Composite Sowing Dates Index directly. A raw index value measured at one experimental site cannot be directly assigned to every grid cell in India. Instead, the workflow uses the field experiment as an empirical anchor.



For each crop and season, the field experiment provides:



the sowing-window class;

the field-observed growing-window thermal condition;

the Composite Sowing Dates Index value associated with that sowing window.



The workflow then compares each gridded climate-model growing-window temperature with these field-observed thermal anchors.



The main score shown in the dashboard is the:



Composite Sowing Dates Index-informed thermal analogue suitability score.



This is a 0–100 score. Higher values indicate that the selected grid cell and period have growing-window thermal conditions that more closely resemble field-observed conditions associated with higher Composite Sowing Dates Index values for the selected crop, season, and sowing-window class.



The score should be interpreted as follows:



high score: stronger thermal similarity to field conditions associated with higher index performance;

medium score: partial similarity or intermediate analogue strength;

low score: weak similarity, poor analogue match, or extrapolation outside the field-observed thermal range.



The score is not a yield forecast and is not a direct prediction of the Composite Sowing Dates Index.



#### **Dashboard components**

1\. Suitability slider: historical versus future



The main slider compares the historical baseline with the selected future scenario and period.



The left and right maps show the same crop, season, and sowing-window class, but for different climate periods. The slider allows visual comparison of where suitability increases or decreases under future climate conditions.



This panel is useful for asking:



where does a tested sowing window remain climatically similar to its historical analogue?

where does future warming reduce analogue suitability?

where do future conditions become more or less favourable relative to the field-experiment thermal anchors?

2\. Projected best analogue among tested sowing windows



This panel compares SD1, SD2, and SD3 for the selected crop, season, scenario, and period.



Each grid cell is assigned to the tested sowing-window class with the highest suitability score, but only where the result is sufficiently robust. If the top sowing-window scores are too close, or if the selected class is outside the calibrated thermal range, the grid cell is shown as no robust recommendation.



This map should be read as:



projected best analogue among experimentally tested sowing windows.



It should not be read as an exact sowing-date recommendation.



3\. Future shift in best tested-window analogue



This panel shows how the best tested-window analogue changes from historical to future conditions.



The shift is shown as a class difference:



future best sowing-window class − historical best sowing-window class



For example:



0 means no change in best tested-window class;

+1 means a shift by one class toward a later tested window;

\-1 means a shift by one class toward an earlier tested window.



This panel helps identify regions where future climate may change the relative suitability of the experimentally tested sowing windows.



4\. Model agreement layers



For the ensemble-median view, the dashboard includes model-agreement support layers.



These maps show how many models agree on specific signals, such as suitability decline or agreement with the ensemble-selected best-window class. Values range from 0 to 10, where higher values indicate stronger agreement across the model set.



These layers are intended to help users distinguish robust spatial patterns from locations where model spread is larger.



#### **How to interpret the dashboard**



This dashboard is best used as a research-screening tool. It can support:



visual exploration of projected climate exposure for cucurbit sowing windows;

comparison of crop- and season-specific analogue patterns;

identification of regions where future thermal conditions may move outside field-observed calibration ranges;

development of hypotheses for future field trials;

communication of climate adaptation questions in horticultural systems.



The dashboard is not intended to provide direct farm-level advice.



#### **Important caveats**

The dashboard does not predict yield, fruit number, biomass, biochemical traits, physiological traits, or observed Composite Sowing Dates Index at grid-cell scale.

The dashboard maps thermal analogue suitability only. It does not fully represent management, soil, irrigation, pests, disease pressure, cultivar differences, local agronomy, market timing, or farmer decision-making.

The field-experiment anchors come from a limited number of site-years and tested sowing windows. Multi-location and multi-year validation is needed before operational use.

The best-window map is limited to SD1, SD2, and SD3 as experimentally tested classes. It does not generate new sowing dates.

Future climate projections contain model uncertainty. The ensemble-median view is the main summary, while individual models are provided as diagnostic sensitivity views.

The dashboard should be treated as a prototype for scientific exploration, manuscript development, and stakeholder discussion, not as a final agricultural advisory service.

