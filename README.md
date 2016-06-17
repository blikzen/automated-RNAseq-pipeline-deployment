# automated-RNAseq-pipeline-deployment

Deployed by $ ./analysis_v4.sh

I wrote this for a postdoc who does alot of RNAseq and a modified ChIPseq type of analysis. Basically, this was designed for an openstack cloud with swift and cinder storage. It's launched on the head login node, and automates VM spin up, injects / installs need software for analysis, creates / attaches scratch, moves files from long term storage to scratch, performs analysis up to counts or peak calling, pushes data to an accessible web server, then cleans everything up. Very much so, a set it, forget it, and your data will be available tomorrow morning type thing. 

Specifically, asks user for a handful of information, e.g., flavor of VM, fill locations, type of analysis, etcs, which  define the parameters for the pipeline. It detaches the subsequent deployment and pipeline scripts from the shell, so the analysis runs entirely in the background of the VM. Pipeline progress and resource management can also be easily monitored.
