## Lab 3: Develop V2 of the Recommendation API

#### Duration

60 mins

#### What you will Learn

Your company invested in Gen AI and built an LLM, so we want to leverage that LLM to improve the Recommendations API that was developed by outside contractors. Now that we made sure we can rely on the Subscription API, we’re going to take ownership of the recommendation API and update it to expose the AI fields.

With this lab, we will focus on:

- Prototyping an API
- Mocking an API
- Gather feedback on an API
    

#### What you will do in this Lab

- Import an Open API Specification as a Postman Collection
- Update the Collection to reflect the changes you want to make to your API
- Mock the collection
- Share with consumers and get feedback
    

#### Import an Open API Spec

Since we are taking over development of the Recommendation API, we need to import the Open API Spec for v1 of the API

##### Step 1 - Obtain the Spec file from the outside contractors

- Download this [Open API Specification file](https://drive.google.com/file/d/1x9Qm8-19ZdSUJuLApsJnFA-KRnnE4Z1h/view?usp=drive_link) to your local workstation.
- If you have difficulties downloading the file, the contents of the file can be found in the [Appendix](https://docs.google.com/document/d/1uMkuwgNnMBznZ0Y5Pfko-XXEwBlruXXZZT7Z6lscxeo/edit#heading=h.ofpmdo9jv93l). Simply save the contents to a local recommendations-v1.yaml file.
    

##### Step 2 - Import the Spec

- Navigate to the Private workspace you created previously.
- Click on the Import button next to the Workspace Name
    

<img src="https://lh7-us.googleusercontent.com/Rigt32pTqVtrsgfTvJZ5w_qQv1ONToqDbr2vNmZ3IM9kERY1PZtwzLKUPiQMkMUzrFCR3weozI3VroeJnG3F4dnjWrCiPYIPy2lHSRdMlRWdEv7qgZJIB66OdnkA4X2JDYI_86ginzI6MNA4zWZAS3I">

- In the pop-up dialog, select the yaml file that you downloaded or created in Step 1:
    

<img src="https://lh7-us.googleusercontent.com/0NvI3hBuKyHJThnO5LNBgvesx0r4gFeujVsMDB8ESkOYKF5MXSNPG57-BnM9ExEovk-v9sgqN4ICvav9VSid_PgRTWFYK5HundYQwW47-JRe_SKT-YwCK9YAZ9AoGGTlrg2LsBKLVCGStpY7oV6O5Gk">

- Select the Postman Collection option:
    

<img src="https://lh7-us.googleusercontent.com/Njz8cRbjdWp051Kkeyic97X4awXURlvghpuy-207KlH2GvByFNpNLKI-xjsOilMr_EjPncEURGZSk_Y85E0odKOWb11Ld932cy9B4qqJUfxNa8TxNcEQFDJS9L8swYieL8Mz7UPpTv8L0OenoRxaRGA">

- Click on Import and explore V1 of the API
    

<img src="https://lh7-us.googleusercontent.com/FJFmwYuxvOXvsI6i30gLxm9zKNmdliaOOoWvkCkWbp4EdJdwQDegEPM8HT_6pp_uJUiBnYwDWZmeSEuJ0n_MRaR3eN_YsglpMTCnSolI9K_UzBzkLlYpPfVVzml4_ZGhIBwaXkY1kf1ON-WsXoH7kHg">

**Note: There are other options to import your APIs as Postman Collection,** [<b>learn more here</b>](https://learning.postman.com/docs/getting-started/importing-and-exporting/importing-and-exporting-overview/#importing-data-into-postman)

#### Create V2 of the Recommendations API

We now have a collection called Product Recommendations API which represents the current state of the API as it is used today. We want to create a new structure within the API to represent V2. But first we need to rename the collection, because we will be sharing it later and need to differentiate yours from your classmates.

##### Step 1 - Rename the collection

- Click on three dots next to the Product Recommendation API collection name and select Rename:
    

<img src="https://lh7-us.googleusercontent.com/6D1XGIy0JZMAQWneJrZxiMOoPAmTWOqbldsEfdaJREf2Du4Dcxa38ElHz9YpF6GMKhR5j3LnTH8Ot1zcNSHR_5t9uSjsCzgPDI7JQJ9uuceQg1mTHYZqerazSa1WTkJAqBh-UOdm42Ka_OiBV-P-ONM" width="446" height="1002">

- Prefix your handle and a dash to Product Recommendations API
    

<img src="https://lh7-us.googleusercontent.com/IOmTD1lTBM6IN5-yFoSsu36wjVsgAlGoCpDqoRZJcuVw9PybfDAgLAlq5gsES3G2ZgGTIa5wv2zHhlaALkbyhvcPJUQn4zkb9RHSpUkgCFcBjzuaEzEOSzjKmr3pJ1WCDBQtOoXRUgDNEgNUCzbGkvI">

##### Step 2 - Update the Collection for the addition of V2

- Update the description to help others understand its purpose
    

<img src="https://lh7-us.googleusercontent.com/JNgJmB7VXTNFA5n06DO06_knlrP4lpHKmlHLcrhMcQ3rjrce1G2as8QJ7OMJ4RQ7o-uDa8iFdY0HhDHubxac1ij3AkrIgk8BR_8l9h6viGnehcXBND2rJwMbI9Kcqi_bMrt4dSFzMUT1taUmLsYWRNo">

- We want to make a copy of the V1 folder and everything underneath it to kickstart our V2 work. Click on the three dots next to the v1 folder and select duplicate
- Expand everything underneath v1 Copy to see that everything was duplicated from v1:
    

<img src="https://lh7-us.googleusercontent.com/imJ-n9XwoDGvW4CKI5Af3GdUBrqA1-08P16MYv9c2kiBF0IrxCypYe2bgYi_lOdQ8QYzx9skOx9EcXlrA6OshMAE67RWd6Qc9zHBjWLlk8ASHMlR7Rimjo-aufLnf8MlzNzULGKz5033l0aIz1sD0rs" width="402" height="520">

- Click on the three dots next to the v1 Copy folder and rename the folder to v2:
    

<img src="https://lh7-us.googleusercontent.com/xlRuraiB08DBdnpMej8ZYcxAh5nc84HPEU0nyKsa50M1HkV9yx7-4lfdsoL8LRhzUbXE7Ar8uHXRLaJPl68P2Z6xOaBtKxZFm1sizKBfNDChQksf3v_q8zJ0q0AtaZlVQ8NPKp5uMlh1roq-Dewa2Ao">

- Click into the Get product recommendation request as well as each example underneath the request and change the url from v1 to v2:
    

<img src="https://lh7-us.googleusercontent.com/xuuG4n9d2Hmb3234AFZ6ajKGDNxpI9yoLJUeMiq1aI-ta-1GS-9gMDubGNEQOFKp7M8WgZpsO5gwPt3BtvexXsHGmODZb2WTgZ9OQw8rsZquG1BJyyDPd02K_8qsvOy4z71BxoVThEDAlEgbwFEmcUw">

**Note: From this point forward, we will only be modifying the v2 branch of API. V1 stays as is to document the existing state of the API. If future instructions say to modify any of the requests or examples, assume they are under the V2 folder structure. In fact, to make things easier, collapse the v1 folder hierarchy so that you do not accidentally modify the wrong version**

#### Create the V2 API by adding AI params

##### Step 1 - Update the params

We need to update the params to reference the AI subscribed customerId we setup earlier

- Navigate to the Get product recommendations request
- Update the following Params to these values:
    - customerId – Value: 1003
    - limit – Value: 10

<img src="https://lh7-us.googleusercontent.com/DD_uc5r9Rq43IXmzDwWCgF18FzFkyW5-Vkj3cn-yMNCkf28prLmKF-0-RfnNcB4udS1y5XBZVIVUYGkkBO2Bqw6aNbW-4hNNDqNdUD_BOA-GBo-k38PpeAeRDDofB2RCTfS5NheN3KZz_lzPHUyHbiM">

##### Step 2 - Make the V2 API easier to work with

We are going to convert the relevant aspects of our API into [variables](https://learning.postman.com/docs/sending-requests/variables/variables/)

- Double click each Param Value and click on the Set as variable:
    

<img src="https://lh7-us.googleusercontent.com/MjAnWFcM_c7sjZH6zO1-kKEvNYfTCvow1ObOUEb4iBtYl-JnmaPwkr3JqsvXMqNro5mypOnCDqwp3z5LyYR3dyDQUnhfudGkztffLPduxqIIg9lM53JqzcAD_Gt1_VHTZ_wVDmUXXW3KeFUEUz3NjpU">

- Select Set as new variable
- For both the customerId and the limit, fill out the resulting pop up with following values, ensuring that the scope is set to Collection:
    

<img src="https://lh7-us.googleusercontent.com/2xsPSdgYJZZkbYBeEndQp1eQiqQYbS-kTjV1zYcmlwc_VVrzupgvxsgqHb7WihTSOs-P5CGP8m-d3VDwyXrZx30urzsQtF_TSIJQNCz1RDqY9cWHpOLDp7L7m925bR5Vp-DrK-hTTrLlMA8_ED7BH8A" width="342" height="272">

<img src="https://lh7-us.googleusercontent.com/nYmKB9nKbbVvsTKyTXvydwG7C0tb8sTGzD6cXE4Yxwj2gt2S6i-c9GViGJb3LTMkCnqhXvo3LMBCBWmeJH5pAqN872Yjmd-LeVG9Epf1V8vgQCOmG081qSXbe0olUi4t_MR4aL_S1ee8OASx8ig7qzA" width="344" height="265">

- You will notice that the values are replaced everywhere with the {{ }} placeholders
    

<img src="https://lh7-us.googleusercontent.com/kFEvZvZ6RomfneeKMX28IF52ll1sDzn9Vu1WQFpp9Rn2RHvv_SW1Is8iopxu_vIPTuy7UjmtXSTTxwVZ5f23WH2XP39IIz7wPGqa47FkLx6o9YAYJfEdYyuOnBk7iuCC5Qx5jdvMtBKVlzHfRNDFwgk">

- Ensure you save your work
    

##### Step 3 - Add a new parameter to invoke the AI features

- Add a new query parameter called aiFeatures with a value of generatedDescriptions,sentimentAnalysis
- Set the description to: The AI Features the user can request. generatedDescriptions and sentimentAnalysis are currently supported (in Beta)
    

<img src="https://lh7-us.googleusercontent.com/81KYuyoiuSJ2et7Q77XfJ5TUr_zaXF0uCY7HQAuQ4RaCTFFwmKxJTB2qVrb3AuCrIJ8jJQ1ICIIsebDptD6DCjJ7o4pifre4Gv861MzIvODQC-9HcmV5OfL3d4CLpp1e4n7qftugLAD8wadlacjFStc">

- Convert this new Param to a collection variable as we did the others in the last step
    

<img src="https://lh7-us.googleusercontent.com/x9t4FQ5ZtTPbt_t1olBZw82xonAibVD-qH5s95_fqxTRIdbGoRvykYNdwnW0etEU50vlfOs-1CyzMc3HPYquqmBiZUXsODDjrEIe3Nk1YVjNRhTM6dRXv-D3juZxC9rXAhfxBWZo5HfBozKUtmY1ThM">

- If you want to change one of the collection variables or view them, simply select the Product Recommendations API collection name from the left column, and click on the Variables tab
    

<img src="https://lh7-us.googleusercontent.com/jeZ1QW4ULtQy-nk_WGEIJ6obIOd6GFVfz634-i12ZfMk_r_6jAUX2gAwY_nsvodqxOL72ZIM8pPdJUoAvo04EaJAATZrIrTfsuXoUUEFzLE-5rUabptLUEy4AMAzFzVPiZ8VCsadv0VjoDdZdXe000M">

- Ensure you save all of your work and any changes
    

#### Update the Examples

##### Step 1 - Update the params

We need to update the params to the variables we added earlier

- Expand the Get product recommendations request
- For all 3 examples, change the url to:
    

```
{{baseUrl}}/v2/recommendations?customerId={{customerId}}&limit={{limit}}

 ```

- Save each of the examples as you modify them
    

##### Step 2 - Update the Response

Postman allows you to randomize the request/ mock responses through [dynamic variables](https://learning.postman.com/docs/writing-scripts/script-references/variables-list/) and [template helpers](https://learning.postman.com/docs/designing-and-developing-your-api/mocking-data/creating-dynamic-responses/#using-template-helpers). We will add this capability to our first example

- Navigate to the first example, A list of product recommendations
- Copy and paste the following into the example’s response body:
    

``` json
[
  {
    "id": "{{$randomUUID}}",
    "name": "{{$randomProductName}}",
    "description": "{{$randomWords}}",
    "userRating": "{{$randomInt}}",
    "topReviews": [
      "{{$randomWords}}",
      "{{$randomWords}}"
    ]
  },
  {
    "id": "{{$randomUUID}}",
    "name": "{{$randomProductName}}",
    "description": "{{$randomWords}}",
    "userRating": "{{$randomInt}}",
    "topReviews": [
      "{{$randomWords}}",
      "{{$randomWords}}"
    ]
  }
]

 ```

- Save your work
    

#### Create a New Example

We need a mock server to return an example response including the AI fields. To do this we will create a new example triggered by the addition of the aiFeatures param

##### Step 1 - Copy an existing example

- Click on the three dots … next to A list of product recommendations example and select Duplicate
    

##### Step 2 - Modify to include the AI param

- Update the following in the new copy/duplicate example that Postman made for you
    - Name: A list of product recommendations with AI
    - URL: `{{baseUrl}}/v2/recommendations?customerId={{customerId}}&limit={{limit}}&aiFeatures={{aiFeatures}}`
    - Response Body:

``` json
[
  {
    "id": "{{$randomUUID}}",
    "name": "{{$randomProductName}}",
    "description": "{{$randomProductAdjective}}",
    "generatedDescription": "{{$randomWords}}",
    "userRating": "{{$randomInt}}",
    "sentimentAnalysis":"{{$randomWords}}",
    "topReviews": [
      "{{$randomWords}}",
      "{{$randomWords}}"
    ]
  },
   {
    "id": "{{$randomUUID}}",
    "name": "{{$randomProductName}}",
    "description": "{{$randomProductAdjective}}",
    "generatedDescription": "{{$randomWords}}",
    "userRating": "{{$randomInt}}",
    "sentimentAnalysis":"{{$randomWords}}",
    "topReviews": [
      "{{$randomWords}}",
      "{{$randomWords}}"
    ]
  }
]

 ```

- Notice that this example has sentimentAnalysis and generatedDescription for each recommendation
    

#### Bonus Challenge

Create additional examples of what happens if ‘aiFeatures’ value is ‘generatedDescriptions’ and/or ‘sentimentAnalysis’ instead of ‘generatedDescriptions,sentimentAnalysis’

#### Add Negative Examples

You will notice that the collection also has some examples of non-200 OK examples or error scenarios. Now we want to add an example of what happens when a customer who has not purchased the right subscription attempts to call this API with ‘aiFeatures’ Parameter

- Duplicate the A list of product recommendations with AI example since it already has the right URL
- Update the following fields:
    - Name: customer without AI Subscription
    - Status Code: 401 Unauthorized
    - Body:

<img src="https://lh7-us.googleusercontent.com/VOrmLL7u5YE0t2tX68b8Xkr6MUfaL5ryrdODCsLIPzoIRkT1-IUX_57o4JO0_JK6ZE_TAU87dUnXUYlJVNZAC2EEah94fxTXzgi63eSbJoF92P3K8BkJm7BU8oBE1kW63SgSuMv01qxl9KjqkdsVWtg">

``` json
{
    "error": "Unauthorized"
}

 ```

- Your final result should look like this:
    

<img src="https://lh7-us.googleusercontent.com/W2zfBI6oRvhki-iUEqUc2wum7aBXvM1M-itAcMUI3yv0SC_02T7sChV3hN5s171fgXYGdQuTrQ1Fv3QUOQ4SO89Q-0VKqg0WZzJ4XMhAYP_w-tQnVdyzcuV8zpvpfm-KETsQZm87hmQb0biZZrq9XJk">

- The examples should look like the following
    

<img src="https://lh7-us.googleusercontent.com/_tnBfh1zAmAXjpWDcjhgoHVNfoJrKfu5RtXlbNH0uzbTyYqeaFFl7CaeY4BJmpq14WfV4YTa_St18eyQrCjYD_Mg3LY8wlXosiTzCUIKLI8iiRxRWim0gbMMzgnGBwydTWOnKqsRrYK7_7RE271cmdM">

#### Mock the Collection

Now that we have the examples of the scenarios we want to simulate, let's go ahead and mock the collection.

##### Step 1 - Prepare the collection for mocking

- We want our baseUrl pulled from the environment and not from the collection itself. On initial import from the Open API Spec, Postman set up the baseUrl as a collection variable instead of creating an environment.
- Select the Product Recommendations API collection name from the left column, and click on the Variables tab
- Find the baseUrl variable and hover over the right most corner of the Current value for the delete icon to appear. Select Delete and Save:
    

<img src="https://lh7-us.googleusercontent.com/X37jdAeXhoWEaljKP3uSipSQVBusL1bQnQSSMsPMFkOO4VlafNa0IA4e99h1_zCXjevKMJyfW4wfm1l6QAWkvXZAbvTEkwdxVYKy18HsmEpTdME9QU4k2p1HJuS2sfAAz8RhvAx_Xf2zfVWdTv8GwE4">

##### Step 2 - Create the mock

- Click on three dots next to the Product Recommendation API collection name and select Mock collection:
    

<img src="https://lh7-us.googleusercontent.com/fmaLv-d7pBrPWjAk4QIVjBLcM9jsqmbL51Im9ctTdB-F9o_5Qt_GCoTd2WbRF0dBnY_qgZKjhR_Wy4GRlyh68ikbqLWsn7yTVsfWQVrIxOg-a-O7cNgNtzhHqV_fKJv1VjZB3QEkcXB_du3B_u7kApg" width="460" height="836">

- Name your mock server -Product Recommendations API mock
- Change the Environment to No Environemt
- Select the check box to Save the mock server URL as a new environment variable.
    

<img src="https://lh7-us.googleusercontent.com/ZSVTxqzxFjQRjnG6Xzy1yNV2aKCXMoZNQiUEbzOVkltv1I6_0RjsINr-AAlJtk5V76BwcotNBLMi7rZFgWfrc7Cq_GrZersTV3f3vkvsn8cql31uR7Lb-LT10MBPV63f8BdkjVfkT6O_6s-iRBk7Uos">

- Select Create Mock Server
    

##### Step 3 - Update the mock environment

- Navigate to the new environment
    

<img src="https://lh7-us.googleusercontent.com/iSqfszo3PhvOEZyy19mqaiovt8zqxJEQlf7puTZAhly-ifHPrqDjcHGmkkUTS6SrcsW-g7mZXkPeWJeAZoAqO_PY-TbWa51mCEwIVkm8Ciit5AFi0xSBD7h3qO3b4UjtA_eOlHbWrHchn1HsUCk_dXk">

- Update the following
- Name: `-ProductRecommendations API mock environment`
- Update the variable url to ‘baseUrl’ and leave the value (this is because our urls look for the baseUrl variable)
- Click Save
    

<img src="https://lh7-us.googleusercontent.com/Owauz09L9as5vh1pIQU8mq1ygacVWFg8y8x5r5SG1mvwQnPhkBW5xUp3nU4KvG1wOQ8tjSAGLUkLb01KugVZWwnPrpceu3Bxo5gvPiVLO3F4YtlmhN6PgAL6JHjSk2stbvuGL_Hq69KLdjCi6XBxH0E">

#### Manually Test Different Scenarios

Now that we have the examples of the scenarios we want to simulate, let's go ahead and mock the collection.

##### Step 1 - Get Product Recommendations

- Click on Collections tab and navigate to the V2 Get product recommendations request
- Select the newly created mock environment from the Environment dropbox
- Click on Send a few times to notice the different values for the response
    

##### Step 2 - Modify Product Recommendations to get different example

- Now unselect the aiFeatures Parameter and send a couple of requests. Notice that you get dynamic responses, but the response do not include Generated Descriptions and SentimentAnalysis
- Recheck/Select the aiFeatures param again once finished.
    

##### Step 3 - Trigger an error response

Now let us test what a customer without the AI subscription will see when they use the API.

- Go to the Headers tab and add this header:
    - Key: x-mock-response-name ; Value: customer without AI Subscription
    - Click Send and see the different response

<img src="https://lh7-us.googleusercontent.com/D5Unv5ozeO7o_6xSziasqLMY3gaDvGcdVJ9i3g9EK3_-3QkyqD-4jM8IZxTUcr0szmISnWys_F-w6mqSTXIcWl_Rluh1K1q3NIwVXm_8_eMM2fzVnIoPPfivaadHvYvpbIYyQIjH65wBkglsCYfKRUY">

- Now unselect the header and send a request. You should get the valid 200 OK response
    

#### Share with consumers and get feedback on the mock endpoint

Now that we tested our API with a mock environment, let us share this with potential customers to get their feedback

##### Step 1 - Share the workspace

- Click on the Workspace name and at the far right of the screen, select Workspace Settings
    

<img src="https://lh7-us.googleusercontent.com/A1zaCUl7fKnMbeXDPeoJyFVKcKAfrrdHlkvGrUq68XzWv__YfftgMd5MtWNXNmJmmiQ0jXwX6LDEr-HgTuF8KY8azdTCmDbfTPcTCqZQCJhip6Ju-Ns-XeJqBPKhRXllt8_uz81UqNAXewtZTjuqEvg">

- Click on Invite
    

<img src="https://lh7-us.googleusercontent.com/5Ce5irFNrN-5ofMOopxvCIsGhk3wCFHLIPiLeL5MzzwpMAxFsIy-j-j8aOh3kvmBKMzXj79W80JYX-X14bfiHcFGrvYfqdIIDBYCz4zeaDVLoPxam1CYi7NGbqJl3JVK1psILYNxHB8_57o7y2wRTZU">

- Add the group API Day Instructors as Viewer to this workspace
    

<img src="https://lh7-us.googleusercontent.com/3RCE_HngPq54JQHfM0y5hMqg-Ylcv_I-DRpcn4SRAj66kzVjgBBM3L6PUOauKdWDebyEldyOS5JMPbxYNPPRptCIGiWv7Q71A2rRioTEcB95WY09MwpVeISCNawoqGbbinx7VQJTXBvpB55AFxLuEho">

- Send the Invite
    

##### Step 2 - Ask for reviews

- Leave a comment on your Collection as we did earlier.
- Tag your instructor and leave the comment: Please review the Product Recommendations API V2 and give us your feedback
    

<img src="https://lh7-us.googleusercontent.com/Kp3DY1D9iSlVzJH-F8RHcN10jEQJrqTaRL5-OpHOWe6n10W41v9u5YRSVAaTCHkXscHcgV2LizIhuHjE1yBmdDdSKVA_P3j9u9N9ng7sMolukutDncBInynnAtdq499gjRdtHLyfzkz2L0DfWYFvo_Y">

#### What did you Learn

- Prototyping an API
- Collaborating on the API Design
- Shifting Left in the API Development process
