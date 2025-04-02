# Oxytocin and Dopamine Receptor Expression: Cellular Level Implications for Pair Bonding

Dataset DOI: [10.5061/dryad.s1rn8pkk3](10.5061/dryad.s1rn8pkk3)

## Description of the data and file structure

## Data Description

This dataset was collected from four cohorts of voles:

* Sexually naive prairie voles (NP)
* Sexually naive meadow voles (NM)
* Pairbonded prairie voles (PP)
* Paired meadow voles (PM)

Data was obtained through microscopy image analysis using Fiji ImageJ software.

## Data Collection & Processing

### Microscopy Analysis

* DAPI masks were generated using the Analyze Particles function in Fiji ImageJ. Each region of interest (ROI) represents a nucleus.
* The presence or absence of transcript was assessed for each ROI across three channels: D1DR (Drd1), D2DR (Drd2), and OXTR (Oxtr).
* Data collected per ROI included:
  * ROI number
  * ROI area
  * Mean, minimum, and maximum gray values
  * Percent area covered by pixels

### Oxtr Puncta Quantification

* Oxtr puncta counts were recorded in the Oxtr Puncta Counts file for all four cohorts.
* Secondary Object Count (Sec_Object Count) was collected only for the OXTR channel, representing the number of puncta per ROI.
* Puncta detection utilized:
  * Morphological Filters Plugin ([GitHub link](https://github.com/ijpb/MorphoLibJ))
  * Object Inspector (2D/3D) Plugin

### Regional Classification

* Each ROI was assigned a Region1 category:
  * Core1 = Core of the nucleus accumbens
  * Shell1 = Medial shell
  * Shell3 = Lateral shell
* The Region variable specifies subregion and hemisphere (left/right).
* Rostral-caudal levels (RC levels) of the nucleus accumbens were recorded.

---

## Methods (From Manuscript)

Images were analyzed using Fiji ImageJ software (version 2.14.0/1.54f). Images were split into four channels:

* Channel 0 = DAPI
* Channel 1 = Drd1
* Channel 2 = Drd2
* Channel 3 = Oxtr

Regions of interest (ROIs) outlining DAPI-stained nuclei were automatically generated in Fiji ImageJ. Thresholds for DAPI nuclear staining were manually established to eliminate background and accurately overlay nuclei.

### DAPI Mask Validation

* Accuracy was verified in 10% of images (one per animal) by comparing experimenter-counted vs. automatic nuclei counts.
* Counts differed by ≤5%, supporting the reliability of automatic ROI generation.

### Signal Detection & Quantification

* The DAPI mask overlay was applied to Drd1, Drd2, and Oxtr images (Fig. 1C).
* A white top-hat transformation enhanced contrast, improving bright feature detection.
* Collected signal data included:
  * ROI number (nucleus number)
  * Minimum, mean, and maximum intensity values
  * % area (for both 16-bit and 8-bit data)

### Data Processing & Analysis

* Cellular distribution data was analyzed via custom Python code ([GitHub repository](https://github.com/donaldsonlab/RNAscope-paper)).
* This script identified:
  * Positively labeled nuclei for each channel
  * Double and triple-labeled cells (co-expression)

### Oxtr Puncta Quantification

* Oxtr puncta were quantified using:
  * Morphological Filters Plugin ([GitHub link](https://github.com/ijpb/MorphoLibJ))
  * Object Inspector (2D/3D) Plugin

### Files and variables

#### File: R3\_L1\_PM\_cellular\_distribution\_8\_bit\_v2.xlsx

**Description:** rostral-caudal level 1, paired meadow voles, transcript distribution data (8 bit)

##### Variables

* Region1 (nucleus accumbens subregion), 
* Region (nucleus accumbens subregion with laterality indicated),
*  Channel (label for transcript examined in that wavelength) , 
* ROI (region of interest = nucleus) , 
* Area (of nucleus/ROI), 
* Mean (gray value of transcript in that ROI in that channel indicated), 
* Min (gray value of transcript in that ROI in that channel indicated), 
* Max (gray value of transcript in that ROI in that channel indicated), 
* % Area (amount of area with nonzero pixels within ROI for that channel), 
* Sec Object Count (Oxtr puncta for OXTR channel only). Values are blank for D1DR and D2DR channels in this column.

#### File: R3\_L1\_NM\_cellular\_distribution\_8\_bit\_v2.xlsx

**Description:** rostral-caudal level 1, naive meadow voles, transcript distribution data (8 bit)

##### Variables

* Region1 (nucleus accumbens subregion), 
* Region (nucleus accumbens subregion with laterality indicated),
*  Channel (label for transcript examined in that wavelength) , 
* ROI (region of interest = nucleus) , 
* Area (of nucleus/ROI), 
* Mean (gray value of transcript in that ROI in that channel indicated), 
* Min (gray value of transcript in that ROI in that channel indicated), 
* Max (gray value of transcript in that ROI in that channel indicated), 
* % Area (amount of area with nonzero pixels within ROI for that channel), 
* Sec Object Count (Oxtr puncta for OXTR channel only). Values are blank for D1DR and D2DR channels in this column.

#### File: R3\_L1\_NP\_cellular\_distribution\_8\_bit\_v2.xlsx

**Description:** rostral-caudal level 1, naive prairie voles, transcript distribution data (8 bit)

##### Variables

* Region1 (nucleus accumbens subregion), 
* Region (nucleus accumbens subregion with laterality indicated),
*  Channel (label for transcript examined in that wavelength) , 
* ROI (region of interest = nucleus) , 
* Area (of nucleus/ROI), 
* Mean (gray value of transcript in that ROI in that channel indicated), 
* Min (gray value of transcript in that ROI in that channel indicated), 
* Max (gray value of transcript in that ROI in that channel indicated), 
* % Area (amount of area with nonzero pixels within ROI for that channel), 
* Sec Object Count (Oxtr puncta for OXTR channel only). Values are blank for D1DR and D2DR channels in this column.

#### File: R3\_L1\_PP\_cellular\_distribution\_8\_bit\_v2.xlsx

**Description:** rostral-caudal level 1, pairbonded prairie voles, transcript distribution data (8 bit)

##### Variables

* Region1 (nucleus accumbens subregion), 
* Region (nucleus accumbens subregion with laterality indicated),
*  Channel (label for transcript examined in that wavelength) , 
* ROI (region of interest = nucleus) , 
* Area (of nucleus/ROI), 
* Mean (gray value of transcript in that ROI in that channel indicated), 
* Min (gray value of transcript in that ROI in that channel indicated), 
* Max (gray value of transcript in that ROI in that channel indicated), 
* % Area (amount of area with nonzero pixels within ROI for that channel), 
* Sec Object Count (Oxtr puncta for OXTR channel only). Values are blank for D1DR and D2DR channels in this column.

#### File: R3\_L1\_Oxtr\_Puncta\_Counts\_v2.xlsx

**Description:** Oxtr puncta counts per ROI for naive prairie voles, naive meadow voles, pairbonded prairie voles, and paired meadow voles

##### Variables

* Animal # (sex is M or F and number is corresponding number given in colony)
* Species (meadow or prairie vole)
* Bond status (sexually naive or paired(bonded)
* RC level (rostral caudal of nucleus accumbens; only level 1 is in this data set)
* Region1 (subregion of nucleus accumbens)
* Region (subregion of nucleus accumbens with laterality indicated)
* ROI (region of interest corresponds to each nuclei detected)
* Sec Object Count (# of Oxtr puncta detected within ROI)
* Volume (^3) (data not used)

## Code/software

Data files are in Excel sheets. Data sorting was done through Python scripts found on Donaldson Lab Github
