# Revision_Scope
This is the readme for this paper: When Interpretability Measures Don't Transfer: Construct Validity in Reasoning-Trace Revision Analysis

The files in here have to be run in a very specific order in order for everything to work.

Task_1_Data_Pipeline Contains the trace generation code, outlined in methods->setup-> trace generation and revision classification, has to be run on A100, usually takes ~ 8 hours.
Label_thing_planning_study contains the revisions candidate serachign and calsisfication for scope. This is outlined in the same place in the paper as the last notebook. This can be run end to end without any issues, and can be run on cpu, as long the runner has a OpenAI-API Key. Relatively short, maybe ~ 1 hour
Activation_Extractor_LLM_Planning has the activation extractor. This extracts activations from our revisions earlier, as outlined in methods->setup. 
Untitled 10 - This has the vast majority of code in the project. As such, it is set up so you can click on a cell, and click run all below, and then it will stop once you finish a certain point. The frist section must be immediately run after Activation_Extractor, because the first portion recovers the rejects and the activations from the rejects. This first section also contains the control probe, which is one of the major controls in our paper. Immediately after running, run the next section of untitled 10, this is the bootstrapping code, which gives that statistical rigor to ensure the probe is working correctly
Task 4- Task 4 needs to be run after untitled 10. 
Task 5- Needs to be run after task 4
Untitled 10- The next set of code that needs to be run is the spreadsheet code. This creates the annotated sample spreadsheets given to our annotater, as outlined in Methods-> Hand labeling. 
Counterfactual_Necessity Pilot - his code contains the counterfactual suppression. This needs to be run before running untitled 10 for the final time, due to a bug we have not figured out yet. This gives the results fro counterfactual necessity
Untitled 10 - Once everything else is run, the last section of untitled 10 can be run to get the results for embedding divergence. This contains everything relating to embedding divergence, inclduing the 3 arm control. 

That is pretty much everything you need to know to use this code. All the code provided here is designed to run on an A100 GPU with High Ram at the highest on google colab. No more compute is neccesary. Certain parts, such as the spreadsheet generation and the label part can be run on CPU only, details on run time and cpu/gpu are inside each notebook. 
