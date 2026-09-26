# BioLynk
## Real-Time Emergency Blood Donor Matching & Response Network

> BioLynk connects hospitals with nearby compatible and available blood donors during emergencies through location-aware matching and automated notifications.

---

## 1. Problem & Research Evidence

India has an established blood-transfusion system, but research identifies challenges related to **blood demand–supply balance, geographic accessibility, and emergency coordination**.

### Blood Demand & Supply
A national study covering **251 healthcare facilities** estimated India's clinical blood demand at approximately **14.6 million units**, with supply meeting around **93% of estimated demand**.
* **Source:** PLOS ONE — [*The clinical demand and supply of blood in India: A National level estimation study*](https://doi.org/10.1371/journal.pone.0265951)

### Geographic Accessibility
A geospatial study across eight northern Indian states found that only **61.45%** of the studied population was within 60 minutes of a blood bank.
* **Source:** BMJ Global Health — [*Defining blood deserts and access to blood products for 660 million people*](https://doi.org/10.1136/bmjgh-2024-015637)

### Emergency Blood-Access Delays
A frontline healthcare study in Bihar reported **1–6 hour delays** in obtaining blood, with factors including availability, blood-bank proximity, and coordination.
* **Source:** PubMed — [*The global surgery blood drought: frontline provider data on barriers and solutions in Bihar, India*](https://pubmed.ncbi.nlm.nih.gov/31018826/)

### Recent Pan-India Evidence
A 2026 modelling study using **2024 e-RaktKosh data** analysed access across **735 districts and 5,679 blood-banking facilities**, identifying substantial geographic variation in accessibility.
* **Source:** Transfusion Medicine — [*Timely geographic access to blood banking facilities: A pan-India modelling study*](https://doi.org/10.1111/tme.70075)

---

## 2. The Gap BioLynk Addresses

Existing systems such as **e-RaktKosh** provide blood-bank and blood-availability infrastructure. 

BioLynk focuses on the complementary **last-mile donor coordination problem**:

> **When an emergency requirement needs additional donor support, how can a hospital rapidly identify and communicate with nearby compatible and available individual donors?**

BioLynk therefore does **not** aim to replace blood banks or existing blood-management systems.

---

## 3. Proposed Solution

```text
Hospital Emergency Request
           ↓
Blood Compatibility Filter
           ↓
  Availability Filter
           ↓
 Location-Based Matching
           ↓
  Emergency Notification
           ↓
    Donor Response
           ↓
Requirement Fulfilled?
        ↙     ↘
      YES     NO
       ↓       ↓
     CLOSE   Expand Radius
```

### Core Matching Factors
* **Matching Algorithm:**  
  $$\text{Priority Score} = f(\text{Compatibility}, \text{Availability}, \text{Proximity})$$

* **Dynamic Expansion:**  
  If the initial donor pool is insufficient, the search radius progressively expands to meet demand:
  $$20\text{ km} \longrightarrow 30\text{ km} \longrightarrow 50\text{ km}$$

---

## 4. Data & Dataset Strategy

BioLynk's core MVP relies on rule-based geospatial matching and **does not require a machine-learning training dataset**.

| Data Source | Purpose |
| :--- | :--- |
| **Government OGD / AIKosh** | Hospital identification & location reference data |
| **e-RaktKosh** | Blood-bank context / stock availability |
| **BioLynk Registration** | Donor blood group, location, availability & consent |
| **BioLynk System** | Real-time emergency request & matching logs |
| **Synthetic Data** | Project-generated datasets for development & load testing |

*Synthetic and project-generated data will be clearly distinguished from real-world datasets.*

---

## 5. Technology Stack

* **Frontend:** React.js
* **Backend:** Node.js + Express.js
* **Database / Caching:** Cloud Database + Redis
* **Location Services:** Google Maps Platform / Geospatial services
* **Notifications:** MSG91 / Twilio
* **Cloud Infrastructure:** Google Cloud Platform (GCP)

---

## 6. Why BioLynk?

BioLynk adds a real-time individual-donor coordination layer to the existing blood-management ecosystem.

$$\text{Emergency Request} \longrightarrow \text{Compatible Donor} \longrightarrow \text{Availability} \longrightarrow \text{Proximity} \longrightarrow \text{Automated Alert} \longrightarrow \text{Response}$$

The proposed system converts fragmented manual donor discovery into a structured, location-aware workflow.

---

## 7. Privacy & Safety

* **Consent-Based Registration:** Explicit opt-in required for all participating donors.
* **Controlled Information Access:** Strict role-based access control (RBAC).
* **Data Anonymization:** No unnecessary exposure of personal contact details or precise donor locations.
* **Security Standards:** Secure authentication (OAuth 2.0 / JWT) and end-to-end data encryption.
* **Human-in-the-Loop:** BioLynk facilitates donor discovery and communication; it does not independently make clinical transfusion decisions.

---

## 8. References & Data Sources

### Research Studies
* [PLOS ONE — National Blood Demand & Supply Study](https://doi.org/10.1371/journal.pone.0265951)
* [BMJ Global Health — Geographic Access to Blood Products](https://doi.org/10.1136/bmjgh-2024-015637)
* [Frontline Provider Study — Emergency Blood Access in Bihar](https://pubmed.ncbi.nlm.nih.gov/31018826/)
* [Pan-India Geospatial Study — 2024 e-RaktKosh Data](https://doi.org/10.1111/tme.70075)
* [WHO — Blood Safety and Availability Fact Sheet](https://www.who.int/news-room/fact-sheets/detail/blood-safety-and-availability)

### Government & Public Portals
* [e-RaktKosh — Government of India](https://eraktkosh.mohfw.gov.in/)
* [DGHS — Blood Transfusion Services / NBTC](https://dghs.mohfw.gov.in/bts.php)
* [Government of India Open Data — Hospital Directory](https://www.data.gov.in/catalog/hospital-directory-national-health-portal)
* [AIKosh — CGHS Hospital Dataset](https://aikosh.indiaai.gov.in/home/datasets/details/list_of_hospitals_empaneled_under_cghs_all_over_india.html)

### Technical Stack Documentation
* [Google Maps Platform](https://developers.google.com/maps)
* [Google Cloud Platform](https://cloud.google.com/)
* [Redis Documentation](https://redis.io/)
* [React.js Documentation](https://react.dev/)
* [Node.js Documentation](https://nodejs.org/)
* [Express.js Framework](https://expressjs.com/)
* [Twilio API](https://www.twilio.com/)
* [MSG91 Developer Docs](https://msg91.com/)
