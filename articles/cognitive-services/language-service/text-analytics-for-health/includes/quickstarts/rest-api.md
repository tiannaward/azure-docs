---
author: jboback
manager: nitinme
ms.service: cognitive-services
ms.subservice: language-service
ms.topic: include
ms.date: 10/31/2022
ms.author: jboback
ms.custom: ignite-fall-2021
---

[Reference documentation](/rest/api/language/2022-05-01/text-analysis-runtime/analyze-text)

Use this quickstart to send language detection requests using the REST API. In the following example, you will use cURL to identify medical [entities](../../concepts/health-entity-categories.md), [relations](../../concepts/relation-extraction.md), and [assertions](../../concepts/assertion-detection.md) that appear in text.


## Prerequisites

* The current version of [cURL](https://curl.haxx.se/)
* An Azure subscription - [create one for free](https://azure.microsoft.com/free/cognitive-services/)
* Once you have your Azure subscription, <a href="https://portal.azure.com/#create/Microsoft.CognitiveServicesTextAnalytics"  title="Create a Language resource"  target="_blank">create a Language resource </a> in the Azure portal to get your key and endpoint. After it deploys, click **Go to resource**.
    * You will need the key and endpoint from the resource you create to connect your application to the API. You'll paste your key and endpoint into the code below later in the quickstart.
    * You can use the free pricing tier (`Free F0`) to try the service (providing 5000 text records - 1000 characters each) and upgrade later to the `Standard S` pricing tier for production. You can also start with the `Standard S` pricing tier, receiving the same initial quota for free (5000 text records) before getting charged. For more information on pricing, visit [Language Service Pricing](https://azure.microsoft.com/pricing/details/cognitive-services/language-service/).

> [!NOTE]
> * The following BASH examples use the `\` line continuation character. If your console or terminal uses a different line continuation character, use that character.
> * You can find language specific samples on [GitHub](https://github.com/Azure-Samples/cognitive-services-quickstart-code).
> * Go to the Azure portal and find the key and endpoint for the Language resource you created in the prerequisites. They will be located on the resource's **key and endpoint** page, under **resource management**. Then replace the strings in the code below with your key and endpoint.
To call the API, you need the following information:


|parameter  |Description  |
|---------|---------|
|`-X POST <endpoint>`     | Specifies your endpoint for accessing the API.        |
|`-H Content-Type: application/json`     | The content type for sending JSON data.          |
|`-H "Ocp-Apim-Subscription-Key:<key>`    | Specifies the key for accessing the API.        |
|`-d <documents>`     | The JSON containing the documents you want to send.         |

The following cURL commands are executed from a BASH shell. Edit these commands with your own resource name, resource key, and JSON values.

> [!div class="nextstepaction"]
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0Cl5zkG3CnDjq6O?PLanguage=REST API&Pillar=Language&Product=Text-analytics-for-health&Page=quickstart&Section=Prerequisites" target="_target">I ran into an issue</a>


## Text Analytics for health

[!INCLUDE [REST API quickstart instructions](../../../includes/rest-api-instructions.md)]

[!INCLUDE [Sample request](request.md)]


> [!TIP]
> Fast Healthcare Interoperability Resources (FHIR) structuring is available for preview using the Language REST API. The client libraries are not currently supported. [Learn more](../../how-to/call-api.md) on how to use FHIR structuring in your API call.

## Clean up resources

If you want to clean up and remove a Cognitive Services subscription, you can delete the resource or resource group. Deleting the resource group also deletes any other resources associated with it.

* [Portal](../../../../cognitive-services-apis-create-account.md#clean-up-resources)
* [Azure CLI](../../../../cognitive-services-apis-create-account-cli.md#clean-up-resources)

> [!div class="nextstepaction"]
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0Cl5zkG3CnDjq6O?PLanguage=CSHARP&Pillar=Language&Product=Text-analytics-for-health&Page=quickstart&Section=Clean-up-resources" target="_target">I ran into an issue</a>

