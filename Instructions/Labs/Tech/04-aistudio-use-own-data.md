# Use your own data with Azure AI Studio

The Azure AI Studio Service enables you to use your own data with the intelligence of the underlying LLM. You can limit the model to only use your data for pertinent topics, or blend it with results from the pre-trained model.

**Duration: 10 to 15 minutes**

## Observe normal chat behavior without adding your own data

Before connecting Azure AI Studio to your data, first observe how the base model responds to queries without any grounding data.

1. Navigate to the **playground**.
1. Enter the following prompts, and observe the output.

    ```code
    I'd like to take a trip to New York. Where should I stay?
    ```

    ```code
    What are some facts about New York?
    ```

1. Try similar questions about tourism and places to stay for other locations that will be included in our grounding data, such as London, or San Francisco. You'll likely get complete responses about areas or neighborhoods, and some general facts about the city.

## Create Azure AI Search
Navigate to https://portal.azure.com/#home

Search for AI Search.
![AI Search](../../media/use-own-data/ai-search.png)

Create an instance of the service.

![Create AI Search](../../media/use-own-data/create-ai-search.png)

> **Note**: Azure AI Search is a cloud search service provided by Microsoft Azure that offers AI-powered capabilities to enhance search experiences within applications. It's designed to provide sophisticated search capabilities over large volumes of data, integrating seamlessly with other Azure resources.


Select East US 2 (US Students) or Australia East (Australian Students).


![AI Search Basics](../../media/use-own-data/ai-search-parameters.png)

- **Subscription**: *Same subscription as your Azure AI Studio resource*
- **Resource group**: *Same resource group as your Azure AI Studio resource*
- **Service name**: *Enter globally unique name*
- **Location**: **East US 2 (US Students)** or **Australia East (Australian Students)**
- **Pricing tier**: **Basic**


Review and Create the Service.

![Create Cognitive Search Review and Create](../../media/ai-studio-create-cognitive-search-reviewcreate.png)



Once the service is created, navigate to it.


![Create Cognitive Search Go To](../../media/ai-studio-create-cognitive-search-goto.png)



**Enable Semantic Search.**

> **Note**: Microsoft is releasing a new method that combines vector, semantic and keyword search.


![Create Cognitive Search Enable Semantic Search](../../media/ai-studio-create-cognitive-search-enablesemantic.png)




## Connect your data in the chat playground

Next, add your data in the chat playground to see how it responds with your data as grounding

1. Navigate to the **Playground**, and select *Add your data* in the Assistant setup pane.

    ![Add your data](../../media/ai-studio-owndata-add.png)


2. Select **Add Connection**.


    ![Add Connection](../../media/use-own-data/add-connection.png)

2. Configure the Connection as follow

    ![Configure the Connection as Follow](../../media/use-own-data/connection-configuration.png)


1. Select the previously created AI Search.
   
    ![Index Storage](../../media/use-own-data/your-data-index-storage.png)

2. Configure the Search Settings as follow
   
    ![Search Settings](../../media/use-own-data/your-data-search-index.png)


1. Configure the Index Settings as Follow
 
    ![Index Settings](../../media/use-own-data/your-data-index-settings.png)



1. Review and Finish
    
   ![Review and Finish](../../media/use-own-data/your-data-review-and-finish.png)

1. The information will be captured in a Vector database, you can follow the progress by going to the Index section.

    ![Index Name](../../media/use-own-data/index-name.png)

1. Click on the Index

    ![Index Progress](../../media/use-own-data/index-progress.png)

> **Note**: When you reach this stage, please inform the instructor. This step will take between 15 and 30 minutes.

## Chat with a model grounded in your data

Now that you've added your data, ask the same questions as you did previously, and see how the response differs.

```
I'd like to take a trip to New York. Where should I stay?
```

![Query Data](../../media/use-own-data/query-data.png)

```
What are some facts about New York?
```
![Response from Own Data](../../media/ai-studio-own-data-NY-question2.png)


You'll notice a very different response this time, with specifics about certain hotels and a mention of Margie's Travel, as well as references to where the information provided came from. If you open the PDF reference listed in the response, you'll see the same hotels as the model provided.


> **Note**: **Add your data** is still in preview and might not always behave as expected for this feature, such as giving the incorrect reference for a city not included in the grounding data.



## Navigate to the Data and Index Section
Navigate to the data sections to explore new assets added.

![Data Section](../../media/ai-studio-data-section.png)

If you click on the data, you will see information about it.


![Data Information](../../media/ai-studio-data-section-index.png)


Navigate to the Index Section.


![Index Section](../../media/ai-studio-indexes.png)

