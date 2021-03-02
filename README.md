
# Critical raw materials

_Idea, research, data analysis, data visualization and writing:_  [Michel Penke](https://michelpenke.de)


**Read the full articles on DW.com:**
- [Deposits and markets](https://www.dw.com/en/xxx)
- [Demand and substitution](https://www.dw.com/en/xxx)
- [Environment damage and human rights violation](https://www.dw.com/en/xxx)

The so-called critical raw materials are thirty resources identified by the European Union that are irreplaceable for its future industry. 

DW analyzed the production, market distortion, future demand, alternative elements, environmental damages and human rights violations during the mining process.  

The following text will explain the process behind this story: Which data sources were used, how the analysis was conducted and how the data was visualized.

# Source data



| **Data** | **Source** | **Link** |
| --- | --- | --- |
| List of CRM | EU Commission| [Communication from the Commission to the European Parliament, the Council, the European Economic and Social Committee and the Committee of the Regions](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:52020DC0474)|
| CRM Supply risk | EU Commission| [EU Science Hub](https://rmis.jrc.ec.europa.eu/?page=crm-list-2020-e294f6)|
| Location of CRM deposits I | USGS | [USMIN mineral deposit database](https://mrdata.usgs.gov/general/map-global.html#home)|
| Location of CRM deposits II | ROSYS | [Rohstoffinformationssystem](https://rosys.dera.bgr.de/mapapps/resources/apps/rosys/index.html)|
| CRM Trade Data | OEC| [Country reports](https://legacy.oec.world/en/resources/data/)|
| World Governance Index| WGI | [WGI](https://info.worldbank.org/governance/wgi/)|
| Fragil State Index | FSI | [FSI](https://fragilestatesindex.org/data/)|
| Environmental Performance Index | EPI| [EPI](https://epi.yale.edu/epi-results/2020/component/epi)|
| CRM Future demand & Usage| EU Commission | [Critical Raw Materials for Strategic Technologies and Sectors in the EU](https://rmis.jrc.ec.europa.eu/uploads/CRMs_for_Strategic_Technologies_and_Sectors_in_the_EU_2020.pdf)|
| CRM Usage & Recycling | EU Commission | [Report on Critical Raw Materials and the Circular Economy](http://publications.europa.eu/resource/cellar/d1be1b43-e18f-11e8-b690-01aa75ed71a1.0001.01/DOC_1)|
| CRM Toxicity I | Umweltbundesamt | [Weiterentwicklung von Handlungsoptionen einer ökologischen Rohstoffpolitik ÖkoRess II](https://www.umweltbundesamt.de/sites/default/files/medien/1410/publikationen/2020-06-17_texte_79-2020_oekoressii_abschlussbericht.pdf)|
| CRM Toxicity II | Fraunhofer Society| [Analyse kritischer Rohstoffe für die Landesregierung Baden-Würtemberg](https://um.baden-wuerttemberg.de/fileadmin/redaktion/m-um/intern/Dateien/Dokumente/2_Presse_und_Service/Publikationen/Wirtschaft/2014_Studie_Analyse_kritischer_Rohstoffe_fuer_die_Landesstrategie_BW.pdf)|

# Analysis
### Mapping the deposits
The first part of the analysis was to map the deposit area which are currently mined. Untapped deposits were ignored. The geographical data comes from the [USMIN mineral deposit database](https://mrdata.usgs.gov/general/map-global.html#home) and the German [Rohstoffinformationssystem](https://rosys.dera.bgr.de/mapapps/resources/apps/rosys/index.html). 

![](graphics/map_crm.png)

There are three colored layers that indicated the importance of the deposit. All thirty raw material markets were analyzed individually and their mining areas mapped. In case the market share of the mining country were above 66 percent of one of the thirty markets they were colored in dark blue. Medium blue stands for 33 percent and above and light blue for below 33 percent.

_Known methodological problems: The classification as high, medium and low importance is somehow random since there is no scientific figure or score that states when a player in a market starts to control or dominate the whole system and therefore has a "high" or "low" importance. Furthermore, the quality of the data about mining locations is difficult to estimate. The known mines differ from source to source and were never complete. Therefore, two sources had to been matched._
### Analyzing the importance of market shares
An overall analysis calculated the market shares of all top ten mining nations in all thirty CRM markets each and summed them up. In case there were more than ten mining nations all minor miners were ignored. 

![](graphics/treemap_crm.png)

_Known methodological problems: There are multiple partly contradictory data sets about the market shares of global CRM production._ 
### Trade risks
To visualize the trade risks two aspects needed to be taken into account. One, the market distortion since trading partners are more dependent if only one or just a small number of players control big market shares. Two, the reliability of the local government, the rule of law and other stabilizing social factors which are crucial for a prosperous trade relation. 

![](graphics/scatterplot_crm.png)

A suitable approach to quantify the market distortion is the [Herfindahl index (HHI)](https://journals.sagepub.com/doi/10.1177/0003603X9504000206). It is a measure of the size of players in a market and their scatter. HHI is defined as the sum of the squares of the players' shares within the market. 

<img src="https://render.githubusercontent.com/render/math?math=H :=\sum_{i=1}^N a^2_i">

The HHI score can be normalized to make it independent of the amount of _n_. Whereas the Herfindahl index ranges from 1/_n_ to one, the normalized Herfindahl index ranges from 0 to 1. It is computed as:

<img src="https://render.githubusercontent.com/render/math?math=H :={{H - {1\over n}}\over{1 -{1\over n}}}">

The second factor, the reliability of the local government and economic stability, was easily numbered with the [Good governance index (WGI)](https://info.worldbank.org/governance/wgi/). Therefore, the WGI of each mining nation was weighted due to their market share and summed to get a WGI of the whole market for each CRM. The WGI score ranges from 0 to 100 with 100 being the best. 

_Known methodological problems: It could be disputed if the WGI is the best source to quantify the reliability of a state system to guarantee a stable trade environment. Furthermore, the text states that there are ten CRMs that are of high risk because they show a high market distortion and a low WGI. The methodological thresholds were 0.5 for HHI and 50 for WGI. These thresholds could be numbered differently which would result in another outcome in which CRMs' trade risks are high._
### Usage
The data source for the usage sectors is an [EU Commission's study](https://rmis.jrc.ec.europa.eu/uploads/CRMs_for_Strategic_Technologies_and_Sectors_in_the_EU_2020.pdf). 

![](graphics/typochart_crm_2.png)

_Known methodological problems: none._
### Future demand
The data originates from the same source. Three scenarios are described in the study. The high-demand scenario is visualized in the chart while the low-demand scenario is mentioned in the article right next to it. 

![](graphicsTypochart_crm_1.png)

_Known methodological problems: Future demand depends heavily on technological development. Even small changes in the industry may result in large shifts to other resources or in an increase or a decrease of individual CRMs._
### Recycling
The data for the recycling rates comes from an [EU Commission's study](http://publications.europa.eu/resource/cellar/d1be1b43-e18f-11e8-b690-01aa75ed71a1.0001.01/DOC_1). 

![](graphics/columnchart_crm.png)

_Known methodological problems: none._
### Toxicity
To visualize toxicity two variables were compared: The toxicity of the mining process of each CRM and the capability of a nation to deal with the damage that may result from the process. Two nations that both mine a resource but differ in their efforts to eliminate the consequences have to be treated differently. 
The data for the resource toxicity come from a study of the [Fraunhofer Society](https://um.baden-wuerttemberg.de/fileadmin/redaktion/m-um/intern/Dateien/Dokumente/2_Presse_und_Service/Publikationen/Wirtschaft/2014_Studie_Analyse_kritischer_Rohstoffe_fuer_die_Landesstrategie_BW.pdf) while the numbers for the nations' environmental efforts are based on the [Environmental Performance Index (EPI)](https://epi.yale.edu/epi-results/2020/component/epi). The toxicity is grouped categorically from low to high. The EPI is, as usual, quantified in a range from 0 till 100 with 100 being the best. 

![](graphics/scatterplot_category_crm.png)

_Known methodological problems: To categorize the toxicity of a raw material is difficult and can easily be disputed. Whether the toxicity for the human body, the CO2 emissions or the mining in the natural habitat of endangered species should be part of this index and how they should be weighted is a subjective decision. Besides, the study of the Fraunhofer Society doesn't deliver a categorization for all CRMs._




