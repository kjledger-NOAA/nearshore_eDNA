# nearshore eDNA

eDNA metabarcoding meeting [notes](https://docs.google.com/document/d/1Rp4ZUWfbEIUR9bBEf40BQqtvNvOP0KSQv7GWAV4t0I0/edit#heading=h.eb0y8t2ced3x)

mock community [species list](https://drive.google.com/drive/folders/1ngmfKEM3wCmhXcM7XOED4ukvpCMr1ZvT) and [fastas](https://drive.google.com/drive/folders/1ngmfKEM3wCmhXcM7XOED4ukvpCMr1ZvT) (note: these include a few extra species that will not be used for this project)

notes from 11/8/2024:
- added additional mock community samples to rawdata on sedna (20260701_nearshore_mifish)
- ran initial data processing steps on all field samples and mock communities using "config.nearshore.mifish.yaml" and stored output in "dadasnake/nearshore_w_mock_mifish_updated_20241106"
- and ran blastn against the ncbi nt db on sedna and stored output in "blast/nearshore_mifish_20241106"

- assigned taxonomy using "1_taxonomic_assignment_blastn.Rmd"
- cleaned up pcr replicates and asv's using "2_decontamination.Rmd" 
- also assigned taxonomy by comparing sequences to just fastas of the mock community species using "1.5_taxonomic_assignment_mockdb.Rmd"
- explored mock community samples and exported file for quantitative metabarcoding evaluation of mock communities - "3_mockcommunities.Rmd"
- ran qm models with different subsets of mock communities set to be true - "4_quantitativemetabarcoding_mock.Rmd"
- explored qm of mock communities in "5_qm_mock_figures.Rmd" and amplification efficiencies in "6_qm_mock_alpha.Rmd"

- exploring field samples (no qm adjustments yet) in "7_fieldsamples.Rmd"




