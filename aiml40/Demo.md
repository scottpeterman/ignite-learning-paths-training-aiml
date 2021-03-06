# AIML40 - Demo Instructions

Demo of AIML40, including the preparation for the demo, is described in detail in [AIML40 Public Materials](http://github.com/microsoft/ignite-learning-paths/aiml/aiml40/). We will not duplicate the steps described there, but highlight some important tricks that make the demo better (and fit within 1 hour). Please read the public material first to familiarize yourself with the demo scenario.

## Demo Preparation

As described in [AIML40 Public Readme](http://github.com/microsoft/ignite-learning-paths/aiml/aiml40/README.md), there are the following preparation steps:

1. Create Azure ML Workspace (using Azure Template or CLI Commands)
2. Upload the dataset for AutoML demo to the workspace
3. Create compute cluster to speed up the demo
4. Setup the Jupyter notebook environment and open `asba.ipynb` file in it, getting ready to execute.

In addition to those steps, to ensure speedy demo you need to do the following:

1. **For Demo 1:** Open the browser to [Text Analytics Page](https://azure.microsoft.com/services/cognitive-services/text-analytics/?WT.mc_id=msignitethetour2019-github-aiml40) and in the text box below enter the following text and press **Analyze**: 
> The food was very fresh and flavoursome the service was very attentive. Would go back to this restaurant if visiting London again.
2. **For Demo 2:**
   - Open the page with your [Azure ML Workspace](http://ml.azure.com). If required -- select the correct workspace.
   - Make sure the dataset is uploaded
   - Go to **Automated ML** tab and perform the Auto ML experiement as described in the [AIML40 Public Readme](http://github.com/microsoft/ignite-learning-paths/aiml/aiml40/README.md). It will take quite a lot of time to run, so do it in advance.
   - Make sure that you refresh the page shortly before the presentation, so that you do not have to login again when doing the demo
3. **For Demo 3:**
   - Open `asba.ipynb` in the Jupyter Environment
   - Make sure you have correct Subscription ID pasted in the code (and also Cluster name / Resource Group name, in case you have changed the defaults)
   - Run all cells in the notebook making sure all steps run correctly. Some of the steps will take quite a lot of time to run, so prepare in advance.
   - Make sure you finish working with the notebook just before the demo, so that you do not have to enter credentials again.

So, before the demo, you would have a browser with the following 3 pages open:
 - [Text Analytics Page](https://azure.microsoft.com/services/cognitive-services/text-analytics/?WT.mc_id=msignitethetour2019-github-aiml40)
 - [Azure ML Workspace](http://ml.azure.com)
 - Jupyter Notebook with `asba.ipynb`

## Demo Time!

During the demo, we recommend to show the following:

1. **Demo 1.1**: Just open the browser with [Text Analytics Page](https://azure.microsoft.com/services/cognitive-services/text-analytics/?WT.mc_id=msignitethetour2019-github-aiml40) and click **Analyze**. Page should be pre-loaded.
2. **Demo 1.2**: 
  - On the same page, click **Example-English-Positive** to switch to default phrase *I had a wonderful trip to Seattle last week and even visited the Space Needle two times*, and then click **Analyze**
  - Observe good positive score
  - Make type in the word **wondderful**
  - Click **Analyze** and observe the score drop significantly
3. **Demo 2:** Azure ML Workspace and Automated ML
  - Open the browser with [Azure ML Workspace](http://ml.azure.com) -- page should be pre-loaded
  - Navigate to **Datasets**
  - Open the dateset
  - Expand **Sample Usage** on **Overview** tab to show the code
  - Switch to **Explore** to show the data
  - Switch to **Automated ML**
  - Put in experiment name, select compute, select dataset
  - Chose **Classification** task and **Stars** as target column
  - Expand **Advanced settings** and demonstrate available options, including the selection of algorithms
  - **DO NOT CLICK START**, as it will take a lot of time!
  - Instead, click on **Automated ML** tab again, and bring up the experiment you have performed before during preparation phase
  - Explain the graph showing different model runs, and what the best run is
  - Click on the best model to explore the **ROC**, **Precision-Recall** and other metrics graphs in more detail
  - Demonstrate the **Deploy model** button to show how simple it is to deploy a model
4. **Demo 3:** Using Azure ML Service with Python SDK
  - During this demo, you should follow and explain the cells of `absa.ipynb` notebook
  - To be completely on the safe side, you can just show the code without running it at all - this would be safe, but will not create an impression of code being executed in live demo mode
  - To make more live demo, please refer to [absa-instuctions.ipynb](absa-instuctions.ipynb) notebook, which explains which cells should not be run during the demo, and which can be safely run
  - In general, what we want to avoid is long-running tasks

## Tear Down

Because the demo is resource-intensive, please do not forget to:
* Delete the compute cluster (especially because auto-scale is turned off in our demo to save on cluster preparation time)
* You may also delete the Azure ML Workspace and Resource group altogether -- insturctions are provided in the [Public Readme](http://github.com/microsoft/ignite-learning-paths/aiml/aiml40/README.md)

