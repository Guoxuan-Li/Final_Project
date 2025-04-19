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
      </ul>
    </li>
    <li><a href="#Preparatory work">Preparatory Work</a>
      <ul>
        <li><a href="#datasets-used">Datasets Used</a></li>
      </ul>
    </li>
    <li><a href="#environmental-cost">Environmental Cost</a></li>
    <li><a href="#video summary">Video Summary</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#references">References</a></li>
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


## The Sentinel-2 Satellite




---
# 📝 Preparatory work




# ▶️ Video Summary
A short summary video, the contents include:
- Introduce the Project
- How to Generate Water Body Masks with Code (including three remote sensing methods and unsupervised learning method)
- Analyse the masks
- Assessment of the environmental cost of this project


[[🔗 Link to video]()]

<p align="right">(<a href="#readme-top">back to top</a>)</p>

# 📜 License

Distributed under the MIT License. See `LICENSE.txt` for details.

---

#  Contact

**Guoxuan Li**  - [zcfbgli@ucl.ac.uk](zcfbgli@ucl.ac.uk) / [guoxuan.li.mia@gmail.com](guoxuan.li.mia@gmail.com)

University College London, Department of Earth Sciences

---
<!-- ACKNOWLEDGMENTS -->
# Acknowledgments
This project was created for GEOL0069 at University College London, taught by Dr. Michel Tsamados, Weibin Chen and Connor Nelson. And the data of Sentinel-2 satellite imagery were downloaded from Copernicus Dataspace.

## 📚 References


![image](https://github.com/Guoxuan-Li/Final_Project/blob/main/Images/S2A_MSIL2A_20231028T042901_N0510_R133_T45QYE_20240910T030449-ql.jpg)
![image](https://github.com/Guoxuan-Li/Final_Project/blob/main/Images/S2A_MSIL2A_20241231T043201_N0511_R133_T45QYE_20241231T073201-ql.jpg)
