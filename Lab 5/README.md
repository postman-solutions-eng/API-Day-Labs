## Lab 5: Testing user stories and workflows across multiple APIs

#### Duration

40 mins

#### What you will Learn

With the basics done, we can now move on to more advanced topics. Because you have a firm handle on the basics, we won’t be pointing you to exactly where you need to perform tasks. Rather we will lay out some tasks and help you with some scripts. The rest is up to you to accomplish.

With this lab, we will focus on:

- Creating workflows
- Flow Execution Controls
- Examples of Positive and Negative Tests
    

#### What you will do in this Lab

- Create a new collection and build an end to end workflow
- Use scripting to pass context from one variable to another
- Bonus: Write tests for different scenarios
    

#### Create a Collection for the Workflows

##### Step 1 - Create a Collection

- Step 1: In your private workspace, -Recommendations-V2, create a new collection “Recommendations Workflow”\`
    

##### Step 2 - Duplicate requests

- Step 2: Duplicate the request “Get all subscriptions”
- Step 3: Move the copy into the the new collection you created
- Step 4: Duplicate the request “Get product recommendations” and move that to the new collection
    

###### Update Requests

Since we have two different requests from two different services the {{baseUrl}} variable will not work for both

- Step 5: Add the following collection variables (you can copy the values from the other collection)
    

<img src="https://lh7-us.googleusercontent.com/mxT4UKYo4K5_hnlbtt51HmFHLMUa-zMdar0nCFRDcjU_MNtlYEDCgsRzUtf2kZgm2E7t4rxVxNxQc6ptPtojSAIVCj1-D8YIbvpPaET9PRRdlhgPbDsk2Ik0G9phluCB9qG6O8MvoP22axqTtogMgyo">

- Step 6: Update the “Get all subscriptions Copy” to reflect these changes. Use {{subscriptionsBaseUrl}} for the Base URL
    

<img src="https://lh7-us.googleusercontent.com/hjSZ2_XYGI3WCz9HC_sWkfsM83Us6Gnfh-y7PtjX7H56oy_R4A_4DfGQsYOrKEAMoTE0FiqZ2Zgv8BDpThCkmpA1HAM_zenG-ru7XI0ChOifQAqlCmVh0IekvmkzUyrlDoqjxICpRk4iuThuhM8uCQU">

- Step 7: Update the “Get product recommendations Copy” to reflect these changes. Use {{recommendationsBaseUrl}} for the Base URL
    

<img src="https://lh7-us.googleusercontent.com/ELVGQunLIcou9UnN0kReTq6XfEnltoQ5xL2Yro6Xlsc-FCRIX2Mh9Pfr0AM1RvY6PnZFcROYdawcCvTgONlagOBlsaKjm8mlHsCv0Y2ZCI2aL-WnFS8dPXbFEODiA2YBCLj39J2kNcsUev-h0JTbq8s">

###### Create a new Environment

- Step 8: Create a new Environment “Recommendations Workflow” with these values
    - subscriptionsBaseUrl: Copy the value from the Subscriptions environment or the mock server
    - recommendationsBaseUrl: Copy the value from the Recommendations environment or the mock server
    - Make sure that you updated both initial and current values

##### Section 2: Use scripting to pass context from one variable to another

- Step 1: Add the following script to the “Get all subscriptions Copy” in tests tab. This script is capturing the subscription status that we will use in the next request
    

``` javascript
var planStatus = "inactive"
// Iterate over each object in the array
var found = false;
for (var i = 0; i < jsonData.length; i++) {
    // Check if the current object has the expected plan value and status
    if (jsonData[i].plan === expectedPlan) {
        planStatus = jsonData[i].status;
        break;
    }
}
pm.variables.set("planStatus", planStatus)

 ```

- Step 2: Add the following script to the “Get product recommendations Copy” in “Pre-request Script” tab
    

``` javascript
var planStatus = pm.variables.get("planStatus");
if ("inactive" === planStatus) {
    pm.request.headers.add({
        key: "x-mock-response-name",
        value: "customer without AI Subscription"
    })
}

 ```

- Step 3: Run the collection with two different values for the “customerId” collection variable (1001 and 1002), and notice the difference
    

Having the ability to control the execution through scripts, variables and mock servers will allow you to write different positive and negative tests

##### Bonus: Write tests for different scenarios

- Step 1: Add a collection variable: “expectedResponseCode” and default that to 200
- Step 2: Add an environment variable “sdlcStage” default it to “mock”
- Step 3: Add tests in “Get product recommendations Copy” and make them conditional based on the criteria below
    - If expectedResponseCode is 200, check for 200 Response Code
    - If expectedResponseCode is 401, check for 401 Response Code
    - If expectedResponseCode is 403, check for 403 Response Code
- Step 4: Add a condition to the Pre-request Script to only execute if the sdlcStage is mock
- Step 5: In dev and higher environments, we expect the code to handle the logic of returning the correct Response Code
- Step 6: Instead of running the collections two times with two different values for the customerId, create a JSON file with two sets of data and run the collection with iteration data. [Follow the instructions here](https://learning.postman.com/docs/collections/running-collections/working-with-data-files/)
    

#### What did you Learn

- Creating workflows
- Flow Execution Controls
- Examples of Positive and Negative Tests
