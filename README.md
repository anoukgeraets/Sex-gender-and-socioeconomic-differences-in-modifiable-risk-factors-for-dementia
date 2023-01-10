# Sex/gender and socioeconomic differences in modifiable risk factors for dementia

Code by Anouk Geraets for doi: 10.1038/s41598-022-27368-4
Please cite this paper when using the code: Geraets, A.F.J., Leist, A.K. Sex/gender and socioeconomic differences in modifiable risk factors for dementia. Sci Rep 13, 80 (2023). https://doi.org/10.1038/s41598-022-27368-4  

## Data availability

The English Longitudinal Study of Ageing (ELSA) was developed by a team of researchers based at University College London, the Institute for Fiscal Studies and the National Centre for Social Research. The data are linked to the UK Data Archive and freely available through the UK data services and can be accessed here: https://discover.ukdataservice.ac.uk. 

## Funding

The English Longitudinal Study of Ageing is administered by a team of researchers based at the University College London, NatCen Social Research, the Institute for Fiscal Studies, and the University of Manchester. Funding is provided by National Institute on Aging (R01AG017644; principal investigator: Dr Steptoe) and by a consortium of UK government departments coordinated by the National Institute for Health Research. This work has received funding from the European Research Council (ERC) under the European Union’s Horizon 2020 research and innovation programme (Grant agreement No. 803239).

## Main Code Details

We use data from Wave 1 (2002/2003) till Wave 9 (2018/2019). Since Wave 4 (2008/2009; n=9,886) includes a large number of modifiable risk factors for dementia, it was considered the baseline for this study. In case of missing information on socioeconomic status, risk factors for dementia or potential confounders, non-missing data from adjacent waves (in most cases Wave 3 (2006/2007) or Wave 5 (2010/2011) was used. The most recent data files available on September 29th, 2022, were downloaded that day. 

## Main analyses sex/gender differences

keep if `finstat4` =="C1CM" | `finstat4` =="C3CM" | `finstat` =="C4CM" 

replace `w4xwgt` = 0.00000001 if `w4xwgt`==0

stset `end_dem_int` [pweight = `w4xwgt`] if !missing(`SEB_dem_prev_w9`) , id(`idauniq`) failure(`SEB_dem_prev_w9`==1) enter(time `date_ii4`) origin(time `birthdate`) scale(365.25)

### Total study population

stcox i.`heartdisease` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`hypertension` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`cholesterol` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`diabetes` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`obesity` i.`indsex` c.`indager` i. `wealth_wave4_tertiles`, vce(cluster `idahhw4)

stcox i.`hearingloss` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`smoking` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`alcohol` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`physactivity` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`sleepdist` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`diet` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`depression` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`lowedu_c` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`socialactivity` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`cognactivity` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

### Overall sex/gender difference dementia risk

stcox i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

### Interaction risk factor with sex/gender

stcox i.`heartdisease`## i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`hypertension`## i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`cholesterol`## i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`diabetes`## i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`obesity`## i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`hearingloss`## i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`smoking`## i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`alcohol`## i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`physactivity`## i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`sleepdist`## i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`diet`## i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`depression`## i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`lowedu_c`## i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`socialactivity`## i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`cognactivity`##i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

### Women

keep if `indsex` ==2

stcox i.`heartdisease` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`hypertension` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`cholesterol` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`diabetes` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`obesity` i.`indsex` c.`indager` i. `wealth_wave4_tertiles`, vce(cluster `idahhw4)

stcox i.`hearingloss` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`smoking` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`alcohol` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`physactivity` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`sleepdist` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`diet` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`depression` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`lowedu_c` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`socialactivity` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`cognactivity` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

clear

### Men

keep if `indsex` ==1

stcox i.`heartdisease` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`hypertension` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`cholesterol` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`diabetes` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`obesity` i.`indsex` c.`indager` i. `wealth_wave4_tertiles`, vce(cluster `idahhw4)

stcox i.`hearingloss` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`smoking` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`alcohol` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`physactivity` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`sleepdist` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`diet` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`depression` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`lowedu_c` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`socialactivity` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

stcox i.`cognactivity` i.`indsex` c.`indager` i.`wealth_wave4_tertiles`, vce(cluster `idahhw4`)

clear


### No childhood deprivation

keep if `deprivescale` ==0
stcox i.`heartdisease` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hypertension` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cholesterol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diabetes` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`obesity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hearingloss` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`smoking` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`alcohol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`physactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`sleepdist` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diet` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`depression` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`lowedu_c` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`socialactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cognactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

clear

### Childhood deprivation

keep if `deprivescale` ==1

stcox i.`heartdisease` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hypertension` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cholesterol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diabetes` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`obesity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hearingloss` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`smoking` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`alcohol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`physactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`sleepdist` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diet` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`depression` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`lowedu_c` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`socialactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cognactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

clear

### Interaction risk factor with childhood deprivation

stcox i.`heartdisease`##i.`deprivescale` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hypertension`##i.`deprivescale` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cholesterol`##i.`deprivescale` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diabetes`##i.`deprivescale` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`obesity`##i.`deprivescale  i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hearingloss`##i.`deprivescale` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`smoking`##i.`deprivescale` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`alcohol`##i.`deprivescale` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`physactivity`##i.`deprivescale` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`sleepdist`##i.`deprivescale` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diet`##i.`deprivescale` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`depression`##i.`deprivescale` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`lowedu_c`##i.`deprivescale` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`socialactivity`##i.`deprivescale` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cognactivity`##i.`deprivescale` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

### Medium/high occupation breadwinner

keep if `jobdadlow` ==0

stcox i.`heartdisease` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hypertension` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cholesterol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diabetes` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`obesity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hearingloss` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`smoking` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`alcohol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`physactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`sleepdist` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diet` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`depression` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`lowedu_c` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`socialactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cognactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

clear

### Low occupation breadwinner

keep if `jobdadlow` ==1

stcox i.`heartdisease` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hypertension` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cholesterol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diabetes` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`obesity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hearingloss` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`smoking` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`alcohol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`physactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`sleepdist` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diet` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`depression` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`lowedu_c` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`socialactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cognactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

clear

### Interaction risk factor with occupation breadwinner

stcox i.`heartdisease`##i.`jobdadlow` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hypertension`##i.`jobdadlow` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cholesterol`##i.`jobdadlow` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diabetes`##i.`jobdadlow` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`obesity`##i.`jobdadlow  i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hearingloss`##i.`jobdadlow` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`smoking`##i.`jobdadlow` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`alcohol`##i.`jobdadlow` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`physactivity`##i.`jobdadlow` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`sleepdist`##i.`jobdadlow` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diet`##i.`jobdadlow` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`depression`##i.`jobdadlow` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`lowedu_c`##i.`jobdadlow` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`socialactivity`##i.`jobdadlow` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cognactivity`##i.`jobdadlow` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

### Overall childhood deprivation and occupation breadwinner difference dementia risk

stcox i.`indsex` c.`indager` i.`deprivescale`, vce(cluster `idahhw4`)

stcox i.`indsex` c.`indager` `jobdadlow`, vce(cluster `idahhw4`)

### Occupational attainment low

keep if `occupation` ==1

stcox i.`heartdisease` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hypertension` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cholesterol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diabetes` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`obesity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hearingloss` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`smoking` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`alcohol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`physactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`sleepdist` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diet` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`depression` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`lowedu_c` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`socialactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cognactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

clear

### Occupational attainment medium

keep if `occupation` ==2

stcox i.`heartdisease` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hypertension` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cholesterol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diabetes` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`obesity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hearingloss` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`smoking` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`alcohol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`physactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`sleepdist` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diet` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`depression` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`lowedu_c` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`socialactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cognactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

clear

### Occupational attainment high

keep if `occupation` ==3

stcox i.`heartdisease` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hypertension` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cholesterol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diabetes` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`obesity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hearingloss` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`smoking` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`alcohol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`physactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`sleepdist` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diet` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`depression` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`lowedu_c` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`socialactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cognactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

clear

### Wealth low

keep if `wealth_wave4_tertiles` ==1

stcox i.`heartdisease` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hypertension` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cholesterol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diabetes` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`obesity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hearingloss` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`smoking` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`alcohol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`physactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`sleepdist` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diet` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`depression` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`lowedu_c` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`socialactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cognactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

clear

### Wealth medium

keep if `wealth_wave4_tertiles` ==2

stcox i.`heartdisease` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hypertension` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cholesterol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diabetes` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`obesity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hearingloss` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`smoking` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`alcohol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`physactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`sleepdist` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diet` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`depression` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`lowedu_c` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`socialactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cognactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

clear

### Wealth high

keep if `wealth_wave4_tertiles` ==3

stcox i.`heartdisease` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hypertension` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cholesterol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diabetes` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`obesity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hearingloss` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`smoking` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`alcohol` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`physactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`sleepdist` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diet` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`depression` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`lowedu_c` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`socialactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cognactivity` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

clear

### Interaction risk factor with occupation

generate `occupation_1vs3` = .
replace `occupation_1vs3` = 1 if `occupation`==1
replace `occupation_1vs3` = 0 if `occupation`==3

stcox i.`occupation_1vs3` i.`indsex` c.`indager` , vce(cluster `idahhw4`)

generate `occupation_2vs3` = .
replace `occupation_2vs3` = 1 if `occupation`==2
replace `occupation_2vs3` = 0 if `occupation`==3

stcox i.`occupation_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`heartdisease`##i.`occupation_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hypertension`##i.`occupation_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cholesterol`##i.`occupation_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diabetes`##i.`occupation_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`obesity`##i.`occupation_1vs3  i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hearingloss`##i.`occupation_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`smoking`##i.`occupation_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`alcohol`##i.`occupation_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`physactivity`##i.`occupation_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`sleepdist`##i.`occupation_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diet`##i.`occupation_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`depression`##i.`occupation_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`lowedu_c`##i.`occupation_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`socialactivity`##i.`occupation_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cognactivity`##i.`occupation_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`heartdisease`##i.`occupation_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hypertension`##i.`occupation_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cholesterol`##i.`occupation_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diabetes`##i.`occupation_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`obesity`##i.`occupation_2vs3  i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hearingloss`##i.`occupation_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`smoking`##i.`occupation_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`alcohol`##i.`occupation_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`physactivity`##i.`occupation_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`sleepdist`##i.`occupation_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diet`##i.`occupation_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`depression`##i.`occupation_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`lowedu_c`##i.`occupation_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`socialactivity`##i.`occupation_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cognactivity`##i.`occupation_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

### Interaction risk factor with wealth

generate `wealth_1vs3` = .
replace `wealth_1vs3` = 1 if `wealth_wave4_tertiles`==1
replace `wealth_1vs3` = 0 if `wealth_wave4_tertiles`==3

generate `wealth_2vs3` = .
replace `wealth_2vs3` = 1 if `wealth_wave4_tertiles`==2
replace `wealth_2vs3` = 0 if `wealth_wave4_tertiles`==3

stcox i.`heartdisease`##i.`wealth_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hypertension`##i.`wealth_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cholesterol`##i.`wealth_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diabetes`##i.`wealth_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`obesity`##i.`wealth_1vs3  i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hearingloss`##i.`wealth_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`smoking`##i.`wealth_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`alcohol`##i.`wealth_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`physactivity`##i.`wealth_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`sleepdist`##i.`wealth_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diet`##i.`wealth_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`depression`##i.`wealth_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`lowedu_c`##i.`wealth_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`socialactivity`##i.`wealth_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cognactivity`##i.`wealth_1vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`heartdisease`##i.`wealth_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hypertension`##i.`wealth_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cholesterol`##i.`wealth_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diabetes`##i.`wealth_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`obesity`##i.`wealth_2vs3  i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`hearingloss`##i.`wealth_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`smoking`##i.`wealth_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`alcohol`##i.`wealth_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`physactivity`##i.`wealth_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`sleepdist`##i.`wealth_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`diet`##i.`wealth_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`depression`##i.`wealth_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`lowedu_c`##i.`wealth_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`socialactivity`##i.`wealth_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

stcox i.`cognactivity`##i.`wealth_2vs3` i.`indsex` c.`indager`, vce(cluster `idahhw4`)

### Overall occupation and wealth difference dementia risk

generate `wealth_r` = .
replace `wealth_r` = 1 if `wealth_wave4_tertiles`==3
replace `wealth_r` = 2 if `wealth_wave4_tertiles`==2
replace `wealth_r` = 3 if `wealth_wave4_tertiles`==1

stcox i.`indsex` c.`indager` i.`wealth_r`, vce(cluster `idahhw4`)

generate `occupation_r` = .
replace `occupation_r` = 1 if `occupation` ==3
replace `occupation_r` = 2 if `occupation`==2
replace `occupation_r` = 3 if `occupation`==1

stcox i.`indsex` c.`indager` i.`occupation_r`, vce(cluster `idahhw4`)
