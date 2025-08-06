### Report: SUV Car Market Analysis

---

#### Table of Content  
* Project Name: SUV Car Market Analysis  
* Project Background  
* Project Goals  
* Data Collection and Sources  
* Formal Data Governance  
* Regulatory Reporting  
* Methodology  
* Data Structure & Initial Checks  
* Documenting Issues  
* Executive Summary  
* Insights Deep Dive  
* Recommendations  
* Future Work  
* Technical details  
* Assumptions and Caveats  

---

#### Project Name  
SUV Car Market Analysis  

---

#### Project Background  
As a data analyst for a prominent automotive dealership active for over a decade, I analyzed the SUV market to provide actionable insights. The company operates in Saudi Arabia's retail automotive sector, focusing on SUV sales. Key metrics include sales volume, average transaction price, and vehicle performance indicators. The dataset covers 20 distinct SUV models (2018-2024) from various manufacturers.  

---

#### Project Goals  
Provide a detailed market overview to maintain competitiveness. Key objectives:  
* **Price and Taxation Analysis**: Deconstruct pricing strategies and VAT impacts (15% in SAR).  
* **Fuel Efficiency and Mileage Trends**: Evaluate fuel usage and mileage capabilities.  
* **Market Segmentation**: Examine car company distribution by nationality.  
* **Performance Analysis**: Investigate relationships between vehicle attributes and performance.  



---

#### Data Collection and Sources  
* **Primary Source**: Single CSV file (`suv_cars_only.csv`) stored locally.  
* **No external APIs/databases** were utilized.  

---

#### Formal Data Governance  
* No existing governance framework documented.  
* **Recommendation**: Establish data standardization, quality checks, and centralized data dictionary.  

---

#### Regulatory Reporting  
* Compliance efforts not documented.  
* **Recommendation**: Develop plan to align tax/vehicle specifications with regulatory standards.  

---

#### Methodology  
**Tools**: Python (Pandas, NumPy, Matplotlib, Seaborn)  
**Key Operations**:  
- Dropped `Fuel/Electric Economy` column  
- Created `Total_Mileage` = `Fuel Usage (km/L)` × `Tank Size (L)`  
- Generated statistical summaries via `.describe()`  

---

#### Data Structure & Initial Checks  
**Table**: `SUV_DATA` (20 records)  
**Columns**:  

| Column               | Type    | Description                          | Key Stats                     |
|----------------------|---------|--------------------------------------|-------------------------------|
| id                   | Integer | Unique identifier                    | -                             |
| Company              | String  | Manufacturer (e.g., Mercedes-Benz)   | -                             |
| Car Model            | String  | Model name (e.g., G-Class)           | -                             |
| Year                 | Integer | Manufacturing year (2018-2024)       | -                             |
| Price (SAR)          | Integer | Price in Saudi Riyals                | Mean: 184,002; Max: 1,150,000|
| Tax (15%) SAR        | Integer | 15% VAT amount                       | Mean: 27,600 SAR              |
| Fuel Usage (km/L)    | Float   | Fuel efficiency                      | Mean: 13.28 km/L              |
| Tank Size (L)        | Float   | Fuel capacity                        | Mean: 70.1 L                  |
| Total_Mileage        | Float   | Calculated mileage per tank          | Mean: 888.38 km               |

*Entity Relationship Diagram here*  

---

#### Documenting Issues  
| Table    | Column       | Issue                                                                 | Magnitude | Resolution                             |
|----------|-------------|-----------------------------------------------------------------------|-----------|----------------------------------------|
| SUV_DATA | Price (SAR) | Extreme range (70k–1.15M SAR); outlier skews averages                | High      | Segment luxury/non-luxury for analysis |

---

#### Executive Summary  
**Finance Director Summary**:  
- Average non-luxury SUV price: **~120,000 SAR**  
- Average VAT burden: **17,625 SAR** per vehicle  
- Average mileage per tank: **888 km**  
- Top brands: German, Japanese, American  



---

#### Insights Deep Dive  

##### Category 1: Price and Taxation Analysis  
- Mean price (184,002 SAR) skewed by Mercedes G-Class outlier (1.15M SAR)  
- Median price (117,500 SAR) better represents typical SUV  
- VAT adds 10,500–172,500 SAR per vehicle  
<img width="989" height="590" alt="c8393474-625e-48c9-bef6-578299ff50c8" src="https://github.com/user-attachments/assets/a98c4c0c-1b45-4b26-bf98-983ec55edd35" />

##### Category 2: Fuel Efficiency and Mileage Trends  
- Fuel efficiency: **13.28 km/L** (max 24 km/L)  
- Nissan Patrol leads mileage (1,400 km/tank) due to 140L tank  
- High std. dev. (240.64 km) indicates significant variability  
<img width="784" height="590" alt="362e0fb2-34a3-4680-b9cc-ee4c3014eec2" src="https://github.com/user-attachments/assets/d742bfc9-5022-4d7d-8015-346fce39eb14" />

##### Category 3: Market Segmentation  
- Key markets: **Germany, USA, Japan**  
- Luxury (Mercedes/Porsche) and mass-market (Nissan/Chevrolet) coexist  
- Limited data on nationality distribution (2 German models in sample)  
<img width="788" height="790" alt="53de3182-2e91-4b9d-983b-186b8bc2584c" src="https://github.com/user-attachments/assets/79df9b32-f791-46d6-b9cc-cb4fbfdfb523" />

##### Category 4: Performance Analysis  
- 100% automatic transmissions  
- No manual transmission data limits segmentation  
- Performance metrics require engine size/horsepower augmentation  
<img width="790" height="490" alt="4c9edbb4-000b-4e13-8ac7-aaeecd3d9713" src="https://github.com/user-attachments/assets/ff4bd7b3-7576-4f52-9373-d6832212c4f0" />

---

#### Recommendations  
**For Sales/Marketing Teams**:  
1. Target core market (<200,000 SAR SUVs) skewed by luxury outlier  
2. Highlight high-mileage models (e.g., Nissan Patrol) for long-distance buyers  
3. Develop fuel-efficiency rating system for sales collateral  
4. Train staff on value propositions across price segments  
5. Expand data collection to manual transmissions/other categories  

---

#### Future Work  
1. **Time-series analysis** of sales trends  
2. **Customer segmentation** using purchase behavior data  
3. **Predictive modeling** for inventory pricing  

---

#### Technical Details  
**Environment**: Jupyter Notebook (Python)  
**Key Libraries**:  
- Pandas/NumPy (data manipulation)  
- Matplotlib/Seaborn (visualization)  


---

#### Assumptions and Caveats  
1. **Limited sample size** (20 records) may not reflect full market  
2. **Mercedes G-Class price** treated as valid outlier  
3. **Location assumption**: Saudi Arabia (SAR currency)  
4. **Single data source** (`suv_cars_only.csv`)  
5. **Missing ERD** limits relational understanding  
