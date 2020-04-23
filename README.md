# squirrel_platelets_TMT_2020
Description of a TMT study of hibernating squirrel platelet samples performed at the OHSU PSR

---

# A Hibernating Squirrel Platelet Study with Tandem Mass Tags
## prepared by Jennifer Cunliffe
## [Oregon Health & Science University Proteomcs Shared Resource](https://www.ohsu.edu/proteomics-shared-resource)
### (OHSU PSR)
### April 17, 2020


***


![slide 1](images/Slide1.PNG)

*Slide 1* <br />
This was a collaboration with [Dr. Scott Cooper](https://www.uwlax.edu/profile/scooper/) at the University of Wisconsin - La Crosse. It also involved Dr. Joe Aslan at OHSU, our resident platelet expert. Blood platelets were collected from [13-lined ground squirrels](https://en.wikipedia.org/wiki/Thirteen-lined_ground_squirrel) before, during, and after winter hibernation.

***

![slide 2](images/Slide2.PNG)

*Slide 2* <br />
There are many physiological changes that must occur during hibernation. A main function of platelets is to clot blood and hibernating animal blood undergoes changes so it does not clot. (See [Cooper, et al. 2012](https://journals.physiology.org/doi/full/10.1152/ajpregu.00018.2012) and [Cooper, et al. 2016](https://journals.physiology.org/doi/full/10.1152/physiolgenomics.00120.2015) for more background.) Are there any protein expression differences in the platelet proteome during hibernation that might play a role in this clotting change? We can use isobaric labeling (also known as tandem mass tagging or TMT) and mass spectrometry to perform large-scale protein expression profiling.

> Cooper, S.T., Richters, K.E., Melin, T.E., Liu, Z.J., Hordyk, P.J., Benrud, R.R., Geiser, L.R., Cash, S.E., Simon Shelley, C., Howard, D.R. and Ereth, M.H., 2012. The hibernating 13-lined ground squirrel as a model organism for potential cold storage of platelets. American Journal of Physiology-Regulatory, Integrative and Comparative Physiology, 302(10), pp.R1202-R1208.

> Cooper, S.T., Sell, S.S., Fahrenkrog, M., Wilkinson, K., Howard, D.R., Bergen, H., Cruz, E., Cash, S.E., Andrews, M.T. and Hampton, M., 2016. Effects of hibernation on bone marrow transcriptome in thirteen-lined ground squirrels. Physiological genomics, 48(7), pp.513-525.

***

![slide 3](images/Slide3.PNG)

*Slide 3* <br />
TMT involves chemical reaction of peptides (not proteins) with special reagents. We first have to digest the proteins with trypsin and remove any buffer chemicals, like SDS and salts, that might interfere with the mass spectrometer. We have to reduce disulfide bonds (and block the cysteines) and denature the protein to digest with trypsin. Once we have peptides, we can label them with TMT reagents. We use liquid chromatography to spread out the complex peptide mixture and give the instrument time the measure the peptides. We use our in-house [TMT quantification pipeline](https://github.com/pwilmart/PAW_pipeline) to identify peptides, infer proteins, and summarize the TMT reporter ions.

***

![slide 4](images/Slide4.PNG)

*Slide 4* <br />
We had 11 TMT reagents available (11-plex) when the experiment was done. There are now 16-plex reagents and we have methods to use more than one plex in a study. Each reagent that labels a particular biological sample has a unique low mass reporter ion that get liberated during the mass spectrometry. Here we see the total reporter ion intensities for kininogen for the pre-hibernation (in red) and hibernation samples (in blue). This protein has increased expression during hibernation and has known involvement in blood coagulation, blood pressure regulation, and inflammation.

***

![slide 5](images/Slide5.PNG)

*Slide 5* <br />
Clustering views are a way to see if the experiment worked like we imagined. We might expect that the biological replicates within each condition would be similar to each other. If we have protein expression differences between groups, then we expect the clusters for each condition to be separated from each other. We can see that the blue cluster, the red cluster, and the green cluster are distinct.

***

![slide 6](images/Slide6.PNG)

*Slide 6* <br />
We use statistical modeling to test the differential expression (DE) levels of each protein to see if they are the same between conditions or different. Here we have an MA plot where the x-axis is a measure of the protein abundance and the y-axis is the expression fold-change (log2 scale). The black horizontal band are the proteins whose expression was unchanged. The red proteins were over-expressed in hibernating squirrel platelets. The blue proteins were down regulated. We see clear separations between up regulated (red), down regulated (blue()) and unchanged proteins (black). The DE candidates are also well distributed across the protein abundance range (spread along the x-axis).

***

![slide 7](images/Slide7.PNG)

*Slide 7* <br />
There are many different ways to visualize results. Here we have protein intensity scatter plots. The statistical test p-values are converted to false differential expression rates with the Benajimini-Hochberg multiple testing correction. We have used some FDR significance cutoffs to rank proteins into three DE candidate categories and the non-DE category. We have many high and medium DE candidates with more than 2-fold changes. Most of the non-DE proteins (lower right in purple) have less than 2-fold changes.

***

![slide 8](images/Slide8.PNG)

*Slide 8* <br />
Some of the ways to understand the differentially expressed proteins is to see what known functions they have and what pathways they are involved in. Not much is known about squirrel proteins, but a lot is known about human proteins. We can compare the squirrel protein sequences to human sequences using BLAST to find ortholog relationships. Python scripts for [BLAST mapping](https://github.com/pwilmart/PAW_BLAST) and [rich annotations](https://github.com/pwilmart/annotations) make this easy to do. We can then perform functional and pathway analysis with tools like [STRING](https://string-db.org/) using the information from the human orthologs.

***

![slide 9](images/Slide9.PNG)

*Slide 9* <br />
We see a richer, more complicated network for up-regulated proteins compared to down-regulated proteins. Further investigations into these DE candidate proteins are ongoing in the Cooper lab.

***

![slide 10](images/Slide10.PNG)

*Slide 10* <br />
We were able to identify and quantify over 3000 squirrel platelet proteins. Highly multiplexed TMT reagents allowed sufficient numbers of biological replicates per condition to perform high quality statistical analyses of realistic experimental designs. We had different expression patterns in each of the 3 conditions that were apparent from the cluster plot. We could test the proteins for differential expression and identify the proteins that were up and down regulated. We could use BLAST ortholog mapping and leverage human protein annotations to understand the functional and biological process changes associated with the hibernating ground squirrel platelet proteome.

***

Thank you!

Please contact the [OHSU PSR](https://www.ohsu.edu/proteomics-shared-resource) with any questions.
