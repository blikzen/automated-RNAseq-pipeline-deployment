# automated-RNAseq-pipeline-deployment

Deployed by $ ./analysis_v4.sh

I wrote this for a postdoc who does alot of RNAseq and a modified ChIPseq type of analysis. It's designed for an OpenStack cloud with Swift and Cinder storage, but is generalizable to AWS. It's launched on the users login node, asks the user for minimal information to define the parameters for the analysis, automates VM spin up, injects / installs need software for analysis, creates / attaches scratch, moves files from long term storage to scratch, performs analysis up to counts or peak calling, pushes data to an accessible web server, then cleans everything up. A sort of set it, forget it, and your data will be available tomorrow morning type thing. At the moment, doesn't integrate the R side scripting into the pipeline as my end user typically likes to do that himself. Still that's certainly doable from an automation standpoint, given you have a very good idea what an optimal pipeline is for a wide range of scenarios.

Also, this is a very limited usage scenario. Then end user doesn't really have alot of resources to work with, so the scripting doesn't really need to take into account more complex parallelization use cases, e.g., clustering, multiple VM deployments, that type of thing, but which is certainly doable to perform alot of analyses at scale.
