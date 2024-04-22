## Lab 2: Validate Behavior

#### Duration

30 mins

#### What you will Learn

We’ll learn how to pull changes to a forked collection and then write some tests to ensure that behavior does not change. We’ll also create and configure a monitor.

With this lab, we will focus on:

- How to use Postman to validate the behavior of the APIs you depend on
- How to continuously monitor the API’s behavior and get notified of any unexpected changes
    

#### What you will do in this Lab

For this lab, you will be working in the workspace you created in [Lab 1: Consuming an API created by a different team in your organization](https://docs.google.com/document/d/1uMkuwgNnMBznZ0Y5Pfko-XXEwBlruXXZZT7Z6lscxeo/edit#heading=h.42fhb4dv4lvf), and there is a surprise! The team working on the Subscription API was able to squeeze in the changes you requested. Specifically, we will:

- Pull changes to see the updated examples
- Write Tests
- Run the entire collection as a monitor
    

#### Pulling Changes

Let’s make sure we pull down those changes that the other dev team worked on

##### Step 1 - Navigate to your Private Workspace

- Find your way back to the workspace you created as part of Lab 1
- Navigate to Subscription Service - API documentation
    

##### Step 2 - Pull the changes

- Click on three dots next to the Subscription Service - API documentation collection name and select Pull Changes.
    

<img src="https://lh7-us.googleusercontent.com/49UR_j_GOSYPY5P_QQVBL06GQvkjM3-iBMRXz0ATp1600ZEtopR7scxXT1NfnSQvS9GaK5zsn0G-nlnDyAoqtRU1AY4wXT-4YdlaqteMq3zxp2xcOQEuk1J4YKFJxuZEfMEd7mLano54BBwutqX_dMg">

- Review the changes in the change log and you will see that 2 of the examples have been changed. The other dev team added the example you requested, plus they updated the return for list all subscriptions to include the content for customer 1003.
- Once you are done reviewing, go ahead and click Pull Changes and review that your forked collection has been updated appropriately
- Navigate to the Get all subscriptions request, and ensure you have the Subscription Service - Dev environment selected and click on Send to see the new return all list
- Enable the query param for customerId and add a value of 1003 and click on Send to see the results from the new example
- Clear the value and deselect the customerId query param
    

#### Test the API

##### Step 1 - Write Tests

Since we depend on this service, let us make sure that we are writing some tests to ensure nothing changes and we can rely on customer 1003 existing and having an active ADW-MSTS-ADV-AI-SERVICES plan.

- Still operating in your private workspace, make sure you have the Get all subscriptions request selected and select the Pre-request Script tab.
    

<img src="https://lh7-us.googleusercontent.com/M4DlhxpkILVMyRGFFWrN1Js0D3_FjOTO-iZn8kP_2jnzwyrpfTqWLbX7BjLsF1i01LzTh10_QxEwrduxIW7UeaxOpFozVktdnXHkwuZOTGKJVN_pwCSt2isww0gMC93A41liKjh4eWqBz6KES-Hi4fI">

- We will eventually instruct Postman to run automated tests of everything in the collection. To ensure that our test is set up properly, we want to ensure that customerId 1003 is added as a query parameter. Therefore, add the following to the Pre-request Script tab and Save your work
    

``` javascript
pm.request.addQueryParams("customerId=1002")

 ```

- Once we have that in place, we can start adding our tests to the Tests tab
    

<img src="https://lh7-us.googleusercontent.com/lqj2AeYBlwocV5R0z9P1_Ylwg5Ken0o3-eudvmfQ0xvGs2Bayk-cHoWM5RWjL8uvHGHOMH6fqfNt8KSIhSmpoaTulWG6HGGkdQLvwEvKsW41sCPz67jpLIdDwQBQeijypUGYf-85t7ESqvroR7unBXw">

- Our first test will ensure we receive a 200 status on the endpoint. Since this is a common test, we can search the tests snippets on the right and click on it to add it to our tests.
    

<img src="https://lh7-us.googleusercontent.com/CM5Vkreyb0DxPZRps79dtOW5NGcr6euA8NqcTLnMhfAx6PzMkF5z3HvkY4n3iUr6-yc2-LeE-vDtg55HqPd3DYadzbFYjef33CsqRGLmG4J4l7lJQ0br96AeEluEVc7R9OKseh-O6o_LcyQOmpLWuSk">

- Let’s add another test to make sure that we get at least two plans that this customer subscribed to. Please add the following in addition to the 200 test:
    

``` javascript
pm.test("Expected number of plans", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData).to.be.an('array').with.length.greaterThan(1);
});

 ```

- As you are adding these tests, feel free to hit the Send button and click on the Test Results tab in the header of the response pane to see the results of the test runs:
    

<img src="https://lh7-us.googleusercontent.com/cHHTu9RXDlrLEc2ciB-FDNGG60lYwisnWf8hLwfRkuhcpicurta_U8joArD6_pi2FRp3-6O_IDaflo8DfVdWybfriDZMWfDk3mjjBssp6a_1mZ2Hakvyo0tDVVQ7IFap-i7yin86J1gRwMpEVXJpgjY">

- So far we have written some simple tests. Now let's take it a step further and write a Postman test to verify that within the response JSON array, at least one object has a "plan" value of "ADW-MSTS-ADV-AI-SERVICES" with a "status" of "active":
    

``` javascript
// Parse the response body as JSON
var jsonData = pm.response.json();
//Let us log the value that is passed to the script
console.log(jsonData);
// Define the expected plan value and status
var expectedPlan = "ADW-MSTS-ADV-AI-SERVICES";
var expectedStatus = "active";
// Iterate over each object in the array
var found = false;
for (var i = 0; i < jsonData.length; i++) {
    // Check if the current object has the expected plan value and status
    if (jsonData[i].plan === expectedPlan && jsonData[i].status === expectedStatus) {
        found = true;
        break;
    }
}
// Assert that at least one element in the array has the expected plan and status
pm.test("At least one element has plan '" + expectedPlan + "' with status '" + expectedStatus + "'", function() {
    pm.expect(found).to.be.true;
});

 ```

- Go ahead and make changes to the expected states and watch how the tests fail in the response window. Before you move on, make sure all tests are green and that you have saved your changes
    

#### Monitor the API

##### Step 1 - Automatically run all the tests to Monitor the Collection

Next, we’ll create a Monitor so that we can be notified if the dev API breaks

- Click on three dots next to the Subscription Service - API documentation collection name and select Monitor Collection:
    

<img src="https://lh7-us.googleusercontent.com/KDpDyq-wdf7ph5bAQ4ht7UIiljeo_UBAyzZY19uOvkAcIwUP_nJoR6NXeLH70ealoOS43SHZ4gNXRT4LE3S3i3yxtwMHI5zDy2CkpHCksZOWlYLkemJsK8JBz4Z6TR6BlVOdBj07qtUT072OXg7y6hE">

- Click on three dots … next to the collection name and select “Monitor collection”
- Fill out the information to stand up your new monitor
    - Choose a descriptive name, but precede it with the same prefix you used for your workspace
    - Choose the environment you forked in Lab 1
    - Update the setting to run the collection every weekday (Monday through Friday)
    - Review the remainder of the settings you can adjust
- When you are finished, select Create Monitor
- Postman will navigate you to the monitor’s view and will inform you that the monitor has not been run yet:
    

<img src="https://lh7-us.googleusercontent.com/BODj1d3APVkxDZNb6Qjl2u0RrqkIVonMgK5tJz6052I9qeIhsg0MX1WDYA1tcn7PizfPw4YsnJRsLCl2ME8AqbHhRPXPi-auVWNbCrvsVOUIeXcPiBS7lDRtnTgADKKp6KghEMyRmlDsLafex6rTG4c">

- Go ahead and click on Run to see the output of your tests. This monitor will continue to run at the frequency you selected and inform you if any tests fail.
    

#### What did you Learn

- How to use Postman to validate the behavior of the APIs you depend on
- How to continuously monitor the API’s behavior and get notified of any unexpected changes
