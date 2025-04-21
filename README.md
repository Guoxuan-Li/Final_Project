<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a name="readme-top"></a>

<div align="center">
  <img src="https://github.com/Guoxuan-Li/Final_Project/blob/main/Images/S2A_MSIL2A_20231028T042901_N0510_R133_T45QYE_20240910T030449-ql.jpg"/>
  <img src="https://github.com/Guoxuan-Li/Final_Project/blob/main/Images/S2B_MSIL2A_20240913T162829_N0511_R083_T16RBT_20240913T220827-ql.jpg" />
</div>



# 🛰️ Using Different Water Index and Machine Learning to Classify Water Bodies in Delta Area with Sentinel-2
This is the final project of the UCL module GEOL0069, which is about classify water bodies in deltas using unsupervised learning with Sentinel-2 data.
<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a id="readme-top"></a>
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->


<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#about-the-project">About the Project</a>
      <ul>
        <li><a href="#description of the problem">Description of the Problem</a>
        <li><a href="#Data Selection">Data Selection</a></li>
        <li><a href="#The-sentinel-2 satellite">The Sentinel-2 Satellite</a></li>
        <li><a href="#remote-sensing-methods">Remote Sensing Methods</a></li>
        <li><a href="#machine-learning-method---k-means">Machine Learning Method – K-means </a></li>
        <li><a href="#Figure about the Used Methods">Figure about the Used Methods</a></li>
        <li><a href="#environmental-cost Assessment">Environmental Cost Assessment</a></li>
      </ul>
    </li>
    <li><a href="#Preparatory work">Preparatory Work</a>
      <ul>
        <li><a href="#Requirements">Requirements</a></li>
        <li><a href="#datasets-used">Datasets Used</a></li>
      </ul>
    </li>
    <li><a href="#Getting Started">Getting Started</a></li>
    <li><a href="#Brief Results and Conclusion">Brief Results and Conclusion</a></li>
    <li><a href="#video summary">Video Summary</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#Acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

---

# 🎯 About the Project
This project is the final project of the UCL module GEOL0069, it applies unsupervised machine learning techniques and the remote sensing technique to detect water bodies in the delta areas from Sentinel-2 satellite imagery. Specifically, I use different water indices - **AWEI, MNDWI and NDWI** with Sentinel-2 data and perform **k-means clustering** to extract water features. And then, analyse and compare the results of different masks about the distribution of water bodies. The analysis focuses on two different delta regions: **the Bengal Delta and the Mississippi River Delta**.

## 💡 Description of the Problem
Climate change is intensifying tropical cyclones, accelerating sea level rise and increasing coastal flooding (Ghosh et al., 2019). River deltas are particularly vulnerable to flooding due to their low elevation and densely populated cities (Edmonds et al., 2020). Therefore, conducting flood detection in the delta region is very necessary for the prevention of flood disasters. Traditional project based on field or laboratory research will lead to large energy usage, which increase environmental costs and time costs. This project provides an alternative method based on satellite remote sensing data for detecting the distribution of water bodies.

This study utilised the Sentinel-2 data provided by Copernicus Dataspace, combined with the water indices and the unsupervised learning method of k-means to achieve the monitoring of water bodies. The specific steps are:
- Calculate different water indices in the same place during the flood season and the non-flood season.
  - Automated Water Extraction Index (AWEI)
  - Modified Normalised Difference Water Index (MNDWI)
  - Normalised Difference Water Index (NDWI)
- Using K-means Clustering Algorithm classify water bodies based on different water indices, respectively.
- Using confusion matrix to compare the k-mean mask with the base mask.

And then, analyse with mask results:
- Which water body index is suitable for classification of water bodies in the delta environment.
- Can unsupervised learning assist in water body classification

At the same time, record and calculate the environmental cost of carbon emissions throughout the entire operation time.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 📍 Data Selection
This project conducts an analysis of water body distribution in two delta regions - the Bengal Delta and the Mississippi River Delta.

### The Bengal Delta
As the largest delta in the world, this region is low-lying and densely covered with water networks, which is an important area for studying water distribution, hydrological changes and flood monitoring (Akter et al., 2016). The flood period is from June to October, so I choose S2 data from September 2023 and December 2024 as the research object.

<div align="center">

<table>
  <tr>
    <td align="center">
      <img src="https://github.com/Guoxuan-Li/Final_Project/blob/main/Images/S2A_MSIL2A_20231028T042901_N0510_R133_T45QYE_20240910T030449-ql.jpg" width="300"/><br>
      <em>The Bengal Delta in October</em>
    </td>
    <td align="center">
      <img src="https://github.com/Guoxuan-Li/Final_Project/blob/main/Images/S2A_MSIL2A_20241231T043201_N0511_R133_T45QYE_20241231T073201-ql.jpg" width="300"/><br>
      <em>The Bengal Delta in December</em>
    </td>
  </tr>
</table>

</div>


### The Mississippi Delta
The dynamic landform subsidence of the Mississippi Delta is caused by the combined impact of human activities on sediment supply and river flow, ground subsidence and sea level rise, posing a significant threat to natural and social systems (Blum & Roberts, 2012; Twilley et al., 2016). Therefore, it is very necessary to conduct an analysis of the distribution of water bodies here.

September is the flood season in the Mississippi Delta. The main reason is that this period is when tropical storms and hurricanes are active. Heavy rain and the rise in river water levels increase the probability of floods. So I chose the same location in September and December as the research object.

<div align="center">

<table>
  <tr>
    <td align="center">
      <img src="https://github.com/Guoxuan-Li/Final_Project/blob/main/Images/S2B_MSIL2A_20240913T162829_N0511_R083_T16RBT_20240913T220827-ql.jpg" width="300"/><br>
      <em>The Mississippi Delta in September</em>
    </td>
    <td align="center">
      <img src="https://github.com/Guoxuan-Li/Final_Project/blob/main/Images/S2B_MSIL2A_20241222T163619_N0511_R083_T16RBT_20241222T214343-ql.jpg" width="300"/><br>
      <em>The Mississippi Delta in December</em>
    </td>
  </tr>
</table>

</div>

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## 🛰️ The Sentinel-2 Satellite
The GMES Sentinel-2 mission provides continuity for services that rely on multispectral high-resolution optical observations of the global land surface. GMES is a joint initiative of the European Commission (EC) and the European Space Agency (ESA), aiming to build Europe's capacity to provide and use business monitoring information for environmental and safety applications. This system features MSI and has 13 spectral bands, covering from visible light and near-infrared to short-wave infrared. The spatial resolution ranges from 10 to 60 meters (Spoto et al., 2012). 

A total of five bands used in this project:


| Band Name | Symbol | Methods | Wavelength (nm)|
|-----|-----|-----|-----|
| Blue band | B2 | AWEI | 458 - 523 | 
| Green band| B3 | AWEI, MNDWI and NDWI | 543 - 578 |
| Near-infrared band (NIR)| B8 or B8A | AWEI and NDWI | 785 - 899 |
| Short-wave infrared band (SWIR1)| B11 | AWEI and MNDWI | 1565 - 1655 | 
| Short-wave infrared band (SWIR2) | B12 | AWEI | 2100 - 2280 | 

The following figure shows the operation of Sentinel-2

(image)
<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 📡 Remote Sensing Methods

In this project, three water body indices are used to analyse the water body distribution through remote sensing data. Index **0** indicates non-water body, and index **1** indicates water body.

- Automated Water Extraction Index (AWEI) (Feyisa et al., 2014)
  - AWEI is a remote sensing index specifically used for the automatic extraction of water areas. Its main goal is to **enhance the differences** between water bodies and non-water bodies. There are two commonly used formulas. Due to the complex environment in the delta region, there are many shadows that can interfere with classification. So the shadow optimised version is applied to reduce shadow interference. The required bands for calculation are **blue band (B2), green band (B3), near-infrared band (B8 or B8A), and two short-wave infrared bands (B11 and B12)**.
    ```math
     \text{AWEI} = {\text{Blue} + 2.5 * \text{Green}} - 1.5 * ({\text{NIR} + \text{SWIR1}}) - 0.25 * {\text{SWIR2}}
     ```
- Modified Normalised Difference Water Index (MNDWI) (Xu, 2006)
  - MNDWI is a widely used index for water extraction, especially suitable for water extraction in urban, wetland and complex background. In addition, MNDWI has higher geometry accuracy compared to NDWI, especially at the threshold setting 0 (Wicaksono & Wicaksono, 2019). It relies on the difference between **the green band (B3) and the short-wave infrared band (B11)**.
    ```math
     \text{MNDWI} = \frac{\text{Green} - \text{SWIR1}}{\text{Green} + \text{SWIR1}}
     ```
- Normalised Difference Water Index (NDWI) (McFeeters, 1996)
  - Normalised Difference Water Index (NDWI) is a traditional water extraction formula, especially suitable for clear water and less interfering backgrounds. It relies on the difference between **the green band (B3) and the near-infrared band (B8)**.
    ```math
     \text{NDWI} = \frac{\text{Green} - \text{NIR}}{\text{Green} + \text{NIR}}
     ```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## ⚙️ Machine Learning Method – K-means
**K-means clustering** is an **unsupervised learning algorithm** used to divide a data set into a set of k groups (or clusters), where k represents the number of groups pre-specified by the analyst. It classifies data points based on the similarity of the data features (MacQueen, 1967). The basic idea is to define k centers of mass, one for each cluster, and then assign each data point to the nearest center of mass while keeping the center of mass as small as possible. One characteristic of unsupervised learning is that it doesn't require labels.

In this project, K-mean Clustering Algorithm is used for water body classification based on the different water body indices, which can effectively improve the accuracy of classification and emphasises the effectiveness and convenience of unsupervised learning for Earth environment monitoring.

K-means clustering key factors: 
- **Choosing k**: must be predefined and impacts results;
- **Centroid initialisation**: affects final clustering;
- **The assignment step**: data points are grouped by proximity to the nearest centroid using squared Euclidean distance;
- **Update step**: centroids are recalculated based on the mean position of assigned points

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 🖼️ Figure about the Used Methods
Using figures to introduce the remote sensing methods and machine learning methods used in the project (take the Bengal Delta data as an example).

![image](https://github.com/Guoxuan-Li/Final_Project/blob/main/Images/S2.png)
![image](https://github.com/Guoxuan-Li/Final_Project/blob/main/Images/K.png)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## ♻️ Environmental Cost Assessment
The environmental cost of this research project is relatively low, as it relies primarily on the use of freely available satellite remote sensing data and computational methods that do not require physical fieldwork or consumable resources.

This project utilises Sentinel-2 imagery from Earth observation satellites. Although the operation of satellites has an associated environmental footprint—including emissions from rocket launches and energy consumption during satellite manufacturing and operation—these costs are shared across a wide range of global users and applications.  Thus, the marginal environmental cost attributed to this specific study is negligible.

The time required to operate the project is calculated to calculate the carbon emissions.
- Check GPU Type in Colab: T4 GPU in this project
- Get Run Time: using `time` to measure total time GPU was active
- Estimate Emissions:
  - T4 GPU energy: ~70W/hour
  - Carbon intensity (global avg): according to the New 2024 UK Grid Emissions Factors, the average is about 0.22 kg CO2/kWh
  - Emissions (kg CO2) = (GPU_hours) * (Power_kW) * (Carbon_intensity)
<p align="right">(<a href="#readme-top">back to top</a>)</p>

---

# 📝 Preparatory Work
Before starting the research, preparatory work needs to be done to ensure the smooth operation of the project.

## 🧱 Requirements
- Python 3.10+
- Google Drive
- Google Colab
- The required python library: `rasterio`, `netCDF4`, `time`, `numpy`, `matplotlib`, `seaborn`, `sklearn`

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 📁 Datasets Used
- **Downloaded** the `.SAFE` data from the **Copernicus Dataspace** according to the time and location.
  - In this project, I selected the L2A data. This data has been processed for atmospheric effects (such as aerosols, clouds and water vapor, etc.), so the reflectance data is closer to the real situation on the ground and is suitable for long-term surface analysis.
  - For Bengal Delta:
    - `S2A_MSIL2A_20231028T042901_N0510_R133_T45QYE_20240910T030449.SAFE` for flooding period
    - `S2A_MSIL2A_20241231T043201_N0511_R133_T45QYE_20241231T073201.SAFE` for non-flooding period
  - For Mississippi Delta:
    - `S2B_MSIL2A_20240913T162829_N0511_R083_T16RBT_20240913T220827.SAFE` for flooding period
    - `S2B_MSIL2A_20241222T163619_N0511_R083_T16RBT_20241222T214343.SAFE` for non-flooding period
- **Unzipped** the file and uploaded it to Google Drive.
- **Uploaded** file to the Google Drive.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

---

# 🚀 Getting Started
This project was mainly conducted in colab, which is a cloud platform that enables us to run python code directly. To run a copy of this project, you can do it step-by-step:

- Download `Using Different Water Index and Machine Learning to Classify Water Bodies in Delta Area with Sentinel-2.ipynb` from this repository.
- Upload it to your Google Drive
- Modify the file paths in the Colab notebook according to the location where you saved data.
  - Notably, in order to simplify the path, I have extracted the data image that I need to use separately, that the `Bangladesh_10/` in the code includes the original path `S2A_MSIL2A_20231028T042901_N0510_R133_T45QYE_20240910T030449.SAFE/GRANULE/L2A_T45QYE_A043602_20231028T043908/IMG_DATA` and the same goes for other data. So when you use the code, you need to convert it to your personal path.
  - A relatively simple method is to directly copy the path and modify it after connecting drive and colab.
- Run the code sequentially.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

---

# ✅ Brief Results and Conclusion
Here are the example results of MNDWI mask and k-mean classification mask based on MNDWI in the two deltas. More results can be found in the notebook.

<p align="center">
  <img src="https://github.com/Guoxuan-Li/Final_Project/blob/main/Images/B_K_MNDWI.png" width="700"/>
  <br/>
  <em> MNDWI related masks in Bengal Delta</em>
</p>

<p align="center">
  <img src="https://github.com/Guoxuan-Li/Final_Project/blob/main/Images/M_K_MNDWI.png" width="700"/>
  <br/>
  <em> MNDWI related masks in Mississippi Delta </em>
</p>


This project mainly used three water body index methods, **AWEI, MNDWI and NDWI**. The results showed that **in the complex delta environment**:
- The **AWEI and MNDWI** are **better** for analysing this environment.
- In contrast, **NDWI** may be more susceptible to the influence of **sediments**, leading to classification errors.
- The classification formed by combining the three indices with **k-mean** is more accurate, minimising classification errors caused by interference from other factors.
- This emphasises the **effectiveness and reliability** of the method combining **machine learning and remote sensing methods** for environmental monitoring.
- The total carbon emissions is 0.0084kg, indicating that this project created a small environmental cost.

In conclusion, this project demonstrates an environmentally responsible research approach, using open access to Earth observation data and machine learning algorithms to conduct large-scale monitoring of water bodies in two deltas with minimal environmental impact. It emphasised the convenience and effectiveness of combining remote sensing methods with machine learning methods to observe the Earth, and further reduced energy consumption to enhance the sustainability of future work.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

---

# ▶️ Video Summary
A short summary video, the contents include:
- Introduce the Project
- How to Generate Water Body Masks with Code (including three remote sensing methods and unsupervised learning method)
- Analyse the masks
- Assessment of the environmental cost of this project


[[🔗 Link to video]()]

<p align="right">(<a href="#readme-top">back to top</a>)</p>

---

# 📜 License

Distributed under the MIT License. See `LICENSE.txt` for details.
<p align="right">(<a href="#readme-top">back to top</a>)</p>

---

# 🧑 Contact
**Guoxuan Li**  - [zcfbgli@ucl.ac.uk](zcfbgli@ucl.ac.uk) / [guoxuan.li.mia@gmail.com](guoxuan.li.mia@gmail.com)

University College London, Department of Earth Sciences
<p align="right">(<a href="#readme-top">back to top</a>)</p>

---

<!-- ACKNOWLEDGMENTS -->
# 📚 Acknowledgments
This project was created for GEOL0069 at University College London, taught by Dr. Michel Tsamados, Weibin Chen and Connor Nelson. And the data of Sentinel-2 satellite imagery were downloaded from Copernicus Dataspace.

## References
- Akter, J., Sarker, M. H., Popescu, I., & Roelvink, D. (2016). Evolution of the Bengal Delta and its prevailing processes. Journal of Coastal Research, 32(5), 1212-1226.

- Blum, M. D., & Roberts, H. H. (2012). The Mississippi delta region: past, present, and future. Annual Review of Earth and Planetary Sciences, 40(1), 655-683.

- Edmonds, D. A., Caldwell, R. L., Brondizio, E. S., & Siani, S. M. (2020). Coastal flooding will disproportionately impact people on river deltas. Nature communications, 11(1), 4741.

- Feyisa, G. L., Meilby, H., Fensholt, R., & Proud, S. R. (2014). Automated Water Extraction Index: A new technique for surface water mapping using Landsat imagery. Remote sensing of environment, 140, 23-35.

- Ghosh, A., Das, S., Ghosh, T., & Hazra, S. (2019). Risk of extreme events in delta environment: A case study of the Mahanadi delta. Science of the Total Environment, 664, 713-723.

- MacQueen, J. (1967, January). Some methods for classification and analysis of multivariate observations. In Proceedings of the Fifth Berkeley Symposium on Mathematical Statistics and Probability, Volume 1: Statistics (Vol. 5, pp. 281-298). University of California press.

- McFeeters, S. K. (1996). The use of the Normalized Difference Water Index (NDWI) in the delineation of open water features. International journal of remote sensing, 17(7), 1425-1432.

- New 2024 UK Grid Emissions Factors (2024), from https://www.itpenergised.com/new-2024-uk-grid-emissions-factors/, assessed on April 18th, 2025.
  
- Spoto, F., Sy, O., Laberinti, P., Martimort, P., Fernandez, V., Colin, O., ... & Meygret, A. (2012, July). Overview of sentinel-2. In 2012 IEEE international geoscience and remote sensing symposium (pp. 1707-1710). IEEE.

- Twilley, R. R., Bentley, S. J., Chen, Q., Edmonds, D. A., Hagen, S. C., Lam, N. S. N., ... & McCall, A. (2016). Co-evolution of wetland landscapes, flooding, and human settlement in the Mississippi River Delta Plain. Sustainability science, 11, 711-731.

- Wicaksono, A., & Wicaksono, P. (2019). Geometric accuracy assessment for shoreline derived from NDWI, MNDWI, and AWEI transformation on various coastal physical typology in Jepara Regency using Landsat 8 OLI imagery in 2018. Geoplanning J. Geomat. Plan, 6(1), 55-72. 

- Xu, H. (2006). Modification of normalised difference water index (NDWI) to enhance open water features in remotely sensed imagery. International journal of remote sensing, 27(14), 3025-3033.

<p align="right">(<a href="#readme-top">back to top</a>)</p>
