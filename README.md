# Coronavirus-Home-Testing-Kit
Open source technique on how to test coronavirus at home


## Warning! Please do not test samples from other people to prevent cross-contamination (infecting you from their samples)! This repo only serves educational purposes and is only meant to encourage discussion.    
For more details, please refer to https://www.cdc.gov/coronavirus/2019-ncov/lab/rt-pcr-detection-instructions.html


The idea is to devise a simpler version of a RT-qPCR test, eliminate experimental roadblocks so that the test could be done at home. 

The test could be divided into two general steps, **RNA Extraction** and **qRT-PCR**.  

For pipetting, try using disposable sterile exact volume transfer pipettes found here: https://www.pipette.com/transferpipettes?sbr=873&sbn=Globe%20Scientific%C2%A0Exact%20Volume%20Transfer%20Pipettes
A bucket full of ice might also be needed to prevent degradation of RNA and real-time PCR enzymes.  

### RNA Extraction

Quick RNA Extraction Kits are available from third party venders such as Thermo Fischer that allows quick RNA extraction, e.g. https://www.thermofisher.com/us/en/home/life-science/dna-rna-purification-analysis/rna-extraction/rna-types/total-rna-extraction/cells-to-ct-kits.html, especially the TaqMan Gene Expression Cells-to-CT Kit (
https://assets.thermofisher.com/TFS-Assets/LSG/manuals/cms_056225.pdf)


### qRT-PCR

For the reverse transcription part, you do not need a thermocycler. You could instead use a cup of boiling water and a cup of water to hold constant 37°C (hold next to a heat source) to manually cycle between those temperatures. 

For the real-time PCR, you will need to set up a dark box. Then, the goal is to detect fluorescents from the test tubes in that dark box. This could be done with an arduino board and a photosensitive light sensor (https://create.arduino.cc/projecthub/Fouad_Roboticist/light-detecting-f6a321?ref=user&ref_id=1331452&offset=6). Note that it might be worth it to increase the proportion of reactants in the reaction to increase the fluorescents since the the sensitivity for the light sensor might be low. 

Next, you must order three RNA primers specific to COVID-19 according to the CDC guideline. The sequences could be found here: https://www.cdc.gov/coronavirus/2019-ncov/lab/rt-pcr-panel-primer-probes.html. The key is to design custom primers for COVID-19. For Thermo Fischer, it could be found here: https://www.thermofisher.com/order/custom-genomic-products/tools/genotyping/. Copy over the forward and reverse primers for N1-N3 along with RP (serving as control). 

Lastly, real-time PCR needs to quickly cycle between 50°C to 95°C, so readjust the temperature of the second cup of water from 35°C to 50°C so that it follows the temperature settings specified here on page 18: http://tools.thermofisher.com/content/sfs/manuals/cms_041280.pdf. 

Perform Real-time PCR using the previous four sets of experiments (N1, N2, N3, RP) 
For every cycle:
1. remove the rest tube from the water bath cups
2. place it in the dark box 
3. measure the level of fluorescents
4. repeat 40 times

Track if there are patterns of exponential increase in the level of light detected by photosensor, which indicates COVID-19 viral RNA. Results of four sets of experiments could be used for diagnosis according to this criteria: https://www.cdc.gov/coronavirus/2019-ncov/lab/rt-pcr-detection-instructions.html#interpreting-test-results










