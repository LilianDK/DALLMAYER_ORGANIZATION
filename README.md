<h3 align="center">DALLMAYER_ORGANIZATION</h3>

---

<p align="center"> This repo is just for sharing and organizing stuff.
    <br> 
</p>

## 📝 Table of Contents
* [General Information](#1)
  * [Timeline](#1.1)
  * [Expected deliverables](#1.2)
  * [Evaluation criteria](#1.3)
  * [Further information](#1.4)
  * [Contacts](#1.5)
  * [Data](#1.6)
* [Meeting Minutes](#2)
  * [2024-07-04 Kick-Off](#2.1)
  * [2024-07-16 Team Kick-Off](#2.2)
  * [2024-07-26 Touchpoint on research question](#2.3)
  * [2024-08-08 Status data preparation pipeline](#2.4)
  * [2024-08-29 Status data preparation pipeline](#2.5)


## 🧐 General Information <a name = "1"></a>

#### Timeline <a name = "1.1"></a>
- 4. Juli 2024, 16:15 Uhr: Kick-Off-Veranstaltung (digital) DONE WE WERE THERE (see minutes from kick-off meeting 04.07.2024)
- 8. Juli 2024, bis 23:59 Uhr: Registrierung DONE
- 7. Oktober 2024, 16:15 Uhr: Zwischenberichtsveranstaltung (digital)
- 17. November 2024, bis 23:59 Uhr: Abgabe der Resultate
- 17. Januar 2025, 16:15 Uhr: Abschlussveranstaltung und Bekanntgabe des Siegers (digital)
- 3. März 2025: Auszeichnung im Rahmen der DHd-Tagung 2025 in Bielefeld

#### Expected deliverables <a name = "1.2"></a>
- PDF in DE or EN, 200-300 words "Begründung und Kontextualisierung der Fragestellung" ASAP
- Jupyter Notebook with title "_code.ipynb" (restricted to Python, R , Java) IN NOVEMBER
- PDF with title "_text.pdf" in DE or EN IN NOVEMBER

#### Evaluation criteria <a name = "1.3"></a>
- Eine kreative geisteswissenschaftliche Fragestellung, die die Analyse von Big Data begründet und voraussetzt.
- Eine kritische und facettenreiche Analyse des Datensatzes.
- Einsatz von kreativen und möglichst generalisierbaren datenwissenschaftlichen Methoden zur Identifizierung und Beseitigung von Mängeln im Datensatz.
- Für Ansatz A: Ein solides Argument für die fachwissenschaftliche Antwort auf die gestellte Frage.
- Für Ansatz B: Entwicklung eines effizienten Plans für das Digitalisierungsverfahren der Zeitungen, der den FAIR-Prinzipien entspricht.
  
#### Further information <a name = "1.4"></a>
- https://hermes-hub.de/formate/challenges/challenges-ausschreibungen/challenge24_1.html

#### Contacts <a name = "1.5"></a>
- hermes.challenges@uni-marburg.de
- https://hermes-data.slack.com

#### Data <a name = "1.6"></a>
- German language news paper articles extracted text + OCR (optional) incl. metadata from 1914 to 1945 as Pickled Pandas Data Frames
- https://hessenbox.uni-marburg.de/getlink/fi5WMibFaZX2ueh4xBvqwM/Datensatz (159 GB)
- There is additional image data up to 2 TB

## 🧐 Meeting Minutes <a name = "2"></a>
All public information.
#### Minutes from kick-off meeting 04.07.2024 <a name = "2.1"></a>
##### Data <a name = "2.1.1"></a>
- We are receiving the raw data right after their OCR pre-processing on which we shall work
- They recommend not to use the API because data is changing there. Instead they ask us to download the data from the given link
- If we do not have enough disk space we can work with a fraction of the provided data instead of the total dataset
- We must not enrich the data with other data sources because of licensing etc.

##### IP <a name = "2.1.2"></a>

#### Minutes from team kick-off meeting 16.07.2024 <a name = "2.2"></a>
##### Research question <a name = "2.2.1"></a>
- Everyone thinking about some interesting concepts that could be investigated for the next meeting

##### Organisation <a name = "2.2.2"></a>
- Everything in Github Repo

##### Expected Deliverables <a name = "2.2.3"></a>
- We have to deliver 2 things: (1) Forschungsfrage/Fragestellung und (2) Ansatz A oder Ansatz B

#### Minutes from meeting 26.07.2024 - specification research question <a name = "2.3"></a>
##### Data Cleansing <a name = "2.3.1"></a>
- Due to the OCR there is a lot of noise in the data. Like useless pieces and fragements of characters. Therefore, with a sliding-window approach everything jibberish will be thrown away (DT)
- Due to the huge amount of data we sub-set for a dataset to commit further investigations on. Therefore, the data will be facetted and a selection of journal and years will be derived from that (BS)
  
##### Data Pre-Processing <a name = "2.3.2"></a>
- With LLMs or anything other usefull methods the articles are refined to achieve following variables: Journal Outlet (extracted), Publication Year (extracted), Title (generated), Summary of Article (generated), Keyword/Concept (generated) (MM)
  
##### Data Enrichment and Embedding Experiments <a name = "2.3.3"></a>
- With LLMs or anything other usefull methods the data is enriched to achieve following variables: Keyword/Concept (generated) (LDK)
- Following the data pre-processing embedding experiments as well as clustering experiments after that are conducted (all)
  
##### Data Visualization and testing against research questions <a name = "2.3.4"></a>
- In the next meeting we see if we can specify the visualization

##### Sidenote <a name = "2.3.5"></a>  
- Larry J. Griffin and Robert R. Korstad (1998): Historical Inference and Event-Structure Analysis, https://www.jstor.org/stable/26405517

#### Minutes from meeting 08.08.2024 - status data preparation pipeline <a name = "2.4"></a>
##### Data Cleansing <a name = "2.4.1"></a>
- Sliding-window and "beautification" of data works. Code moves slowly, therefore checking on that again. (DT -> BS)
- Sub-set of data for initial tests is Süddeutsche, Kölnischer and Reichsanzeiger.
  
##### Data Pre-Processing <a name = "2.4.2"></a>
- Pipeline is: cleaning > reduction through summaries and concepts creation with LLM > embedding
- For the summaries and concepts creation a modification of chain of density prompt seems usefull. Checking output again for the selected subset (LDK)
  
##### Data Enrichment and Embedding Experiments <a name = "2.4.3"></a>
- Following the data pre-processing embedding experiments as well as clustering experiments after that are conducted (all)
  
##### Data Visualization and testing against research questions <a name = "2.4.4"></a>
- In the next meeting we see if we can specify the visualization

##### Sidenote <a name = "2.4.5"></a>  
- https://github.com/rspeer/python-ftfy

#### Minutes from meeting 29.08.2024 - status data preparation pipeline <a name = "2.5"></a>
##### Data Cleansing <a name = "2.5.1"></a>
- Data cleansing will be the transformation from pandas pickles to JSON
- Sliding-window approach to clear out random characters
  
##### Data Pre-Processing <a name = "2.5.2"></a>
- Re-writing the "old German" text into "modern German" as part of the data preprocessing step is tested
  
##### Data Enrichment and Embedding Experiments <a name = "2.5.3"></a>
- The cleansed and pre-processed data will be enriched with meta data and short summaries of the first page for each newspaper 
  
##### Data Visualization and testing against research questions <a name = "2.5.4"></a>
- xx

##### Sidenote <a name = "2.5.5"></a>  
- xx
