##Lab 1: Consuming an API created by a different team in your company

#### Duration

30 mins

#### What you will Learn

This lab gets us setup for completing the rest of the labs in this session. These steps will help you become more familiar with the Postman UI and a suggested way of collaborating with your fellow team members. However, there are many ways to accomplish these tasks and as your team members become more adept at using Postman in their daily development tasks, you will find the workflow that works best for you.

With this lab, we will focus on:

- Finding APIs using the Postman Private API Network
- Fundamentals of collaborating with team members on your Postman Enterprise instance
- Creating workspaces
- Commenting, Forking, Watching
    

#### What you will do in this Lab

We have a new user story to get started on, so we’re going to explore some of the existing APIs in our enterprise and then set up a workspace so we can get started with API development. More specifically, we will:

- Explore the Internal Private API Network
- Collaborate with the API owners via Postman
- Create a workspace for the API work
- Fork a collection and Watch for updates
    

#### Exploring the Internal Private API Network

Our new user story is all about injecting our new AI Service into an existing Product Recommendation Service that is being developed by a contracted third party. To effectively work on this new API, we will need to ensure that our Subscription Service tells us if our end customer has subscribed to the AI Service and we will need to create a new version of the Product Recommendation API to add on AI parameters and fields. Let’s see what we have to work with by exploring our enterprise APIs through Postman.

##### Step 1 - Locate your enterprise’s curated API catalog and explore an API

- Find the API Network menu in the top upper left corner of the application and expand it
    

<img src="https://lh7-us.googleusercontent.com/IT02PJPmMcLsQ6K8KNnaUf0bgBv1EXieqHeMb7_z14pYjPVGXZcuUyeaX86lPWdA1G12mFpsdBijC6Gp7X50qymhTtbh6jNXAUmbn93Ykl8YI1B3a0K4hTEY0UDekdHfIvoDshjLizG4-bSHi5F1eZY">

- Select View internal APIs to find your enterprises curated list of APIs
    

<img src="https://lh7-us.googleusercontent.com/VI6EySvZK4nZ101CJ_huo7cmsKbo1dKg2QpKis9_how-On4UMHL7mEnrXUCXvYEKKa1HKBNlMfIpZn1H0wA_Iw3ZJtJJOYUL52M7LJypUZ42UPLqg10rlr6aKbNk3q77Swl8cBKJQx4xgOkWk6jfUB4" width="524" height="613">

- From our user research, we know that the Subscription Service we are looking for is one of the core Shared Services. Browse the Private API Network and locate the Subscription Service and we’ll need to look up subscriptions by Customer ID to find if the customer has paid for the add-on AI features. Find an API that seems appropriate, and let one of the instructors know what you’ve found.
- The code language for request samples is defined at the top of the page. Select other languages and see how the documentation page changes
    

<img src="https://lh7-us.googleusercontent.com/cKXp_vtyawh9e-6KB40pdsaLGedkP3VF4mpm84RHcFsf_hLWxWDIbLLS7OmXXY0CKmIiwIhJ5W_0ZNdV_atppUdZRi-_AO6BbbWS_Y2ODGXVH22HIMbVa996apLJOJucUpvi8EmTOZiNInWFi0grc80">

- You can view different example responses that the API can return. Next to the Examples, you will find a drop down to change the type of response received. Go ahead and select different example types and see how the responses change.
    

<img src="https://lh7-us.googleusercontent.com/p5Fs3XUf4hSXvdnHa77O2PPs1_Kd6VpNhwm0bUvpNa75EqleJ-XAxo4cNgxvpKUdD0kgpXfblXTiUmE9wlW4TQWS-xsyBCzAJ9KGlfQbhz1YAgAtPNn10VAUgyV1Z7fw5awr0PlnrqAk64JwypXy1jA">

##### Step 2 - Try the API

- Once you’ve found an API that looks interesting, you can try it out directly from Postman. You’ll notice that many of the endpoints use {{ }} notation as placeholders. This allows you to seamlessly swap variables in and out of the placeholders, such as trying the API in dev vs test, etc..
- In order to fill those placeholders, you’ll need to tell Postman which Environment you’d like to use. Typically the API developer will provide different environments for the API consumer to use. In this case, you’ll find a dev environment to test out the API. At the top of the document you’d like to test, look for the Environment drop down:
    

<img src="https://lh7-us.googleusercontent.com/NO9SDDCSccUAKHLy8Cn9bUdTVXKe0g0TekYFvepfmOTNGKWg3c7uml0QTTfmrba8yAxNGdbeyuRp5GikA_QxFoKgh6Lo2uC5DyMFo0xsjzZ02fCaECEHZegGNp_gJa5qGNAnh5G5HmyqKWghRB058pM">

- Change from No Environment to Subscription Service - Dev:
    

<img src="https://lh7-us.googleusercontent.com/aM3F1hFS4osiCC0fJL2B1Ht7bJN5m-nvpQGN3oKIjJLz56Uvez3EMEKfNVaXRCJI3sZLj9zBjJAzlUgNxyUOyKwKsdi7MuNvT1KKsnpio5bb3342C0Dm8bX7dsv2_2Sa2TBhgPmvtRSODO4xTJfo4rY">

- You’ll notice that the documentation will update with the placeholders now containing the values saved in the environment. In this case, the url may look a bit odd. In fact, this API environment is using one of Postman’s features to generate a mock endpoint to test traffic. We’ll dive into that in a later lab.
    

<img src="https://lh7-us.googleusercontent.com/VI_UJUzl4i_tP5DQwFOZZSC8l5KurbeayNNNco3dtLckFde3Fmiy-VNfRhO643WpfmfG12KoFewHr1mzgQOla5CYa11_0SmrR3xzrlpJQV5VuflDrXPgAK_0d0hhuJpF9qK3f-RdXioODML08G_lSOU">

- Go ahead and try out the request by clicking on the Try Request link or the Try Example link which will take you to the workspace containing the collection. You can think of the internal Private API Network as a curated list of pointers to the underlying collections:
    

<img src="https://lh7-us.googleusercontent.com/LCDC5r5HcM_JR11DCFTSv-Y4gOjLhnwN09hAGGf1ZgIGiccbHCdN99Hk2t-9BzYRz3cmZwCVbhmX1nJAKYcRoznMitxnoWndNs82WuddTeZsUWyMrNpdZZ-ARGOxHDcZ7lyHSK2u3wGFU3NOqfJclVI">

<img src="https://lh7-us.googleusercontent.com/eZ5kRiNfF9MbMmxyc3vLBF_sh3BwW0pmdZwISjHVtgTLpY2pqAbMQlZm3MX9-EqRX7Zujy3G2EsISMu1i0219RbXSs4caC-kKxOtg6SvjczEJlSXr2gsXKezUC0dMqJIN9negBRU_IQk8H_GbT9FAzU">

- In the new tab you will notice that the environment you selected earlier is carried over. Go ahead and select Send and look for the response at the bottom of the page.
    

<img src="https://lh7-us.googleusercontent.com/jllcuyvwSfgOliKWBX8vD8kj9qkSyItg_8X-0kW2gcnDyeWsTq2VNM9VC4njkILCMxqQf80CFI4mF-GIDc0W_xGp3wMBRdP-5rk2_Wn4DRRio-boQ08ZIzKHrU3CdikP18UUgOPlqOifgsBXugLqutM" width="458" height="488">

- You should also note that the {{ }} placeholders are not replaced by the environment on the individual request view. Instead, if you hover your mouse over the placeholder, you will see the value of the injected variable:
    

<img src="https://lh7-us.googleusercontent.com/97JhlPrP8jLZ-OKHvSGXCbKe2uKl8THioWsdnA8eVphwhuGVUV_JOXRxKePuhC4kWBTDPrpFrXy53S7exkY7L7eKJUli3CF1CLtF1re17wohSpHr0MzoCfIlWOqJA_Lxl7DU4yGxdlTq7pwUCdGpGlI">

#### Collaborate with the API owners via Postman

##### Step 1 - Learn about Examples

The Recommendations API we will develop in subsequent labs should only work for customers with a subscription to an advanced plan of your API. Unfortunately the current live version of the API does not have a customer with active subscription to the AI Services. This prevents us from doing any integration testing for our user story.

What we really would like initially, is a mock response that returns active as a status to our AI subscription SKU. So let’s take a look at how the Examples could help us out here. Go to the Shared Services workspace and find the Subscription Service - API Documentation collection. Expand the collection and find the Get all subscriptions request. Select it to expand the request. It should look like this:

<img src="https://lh7-us.googleusercontent.com/UIXhhQ7wPxaIwO2RXHPh7UxE3qXoRvBVpI8UgfmlBONghhBHoDqq4baMX_LlDjIGTvnQCGnp2Thut9dgZ14LRBRGO6yrdRSlux5TDgJxF6-C2JGK_3QNjjukqAU5M0FUuUi7xbqWNWXYfTW_kur2W_A" width="422" height="449">

In the center panel of the app, you will see the details of the request. Go ahead and click on Send. As long as you have an environment selected (as we should from the previous exercise), you will see a response that contains multiple customer Ids with subscription products. Take a look at the params (Query Parameters) and see that customerId is in the list but not selected:

<img src="https://lh7-us.googleusercontent.com/jNF-vpk9Fj0iRRiha_AOuqnEw3W4_hpm58D6cJlLrHJ8A9S-WLFmp_mIjUlCu9vHlh5sp22xPfR-TRd3i2bM9XszLDVGli35qpNH28oOeKy2jZ1f26paBzmIGCf9tfaG5MRCPsqk_BBV5yY1Z8VJRjY" width="436" height="311">

Now do the same exploration for the examples under the request:

- A list of subscriptions - Shows no query params and shows the example response as containing all the subscriptions
- Subscriptions By Simple Customer - has an active (checked) query param and has a value of 1001. The example response shows a list of subscriptions for only customerId 1001 (1 in the list).
- Subscriptions By Advanced Customer - has an active (checked) query param and has a value of 1002. The example response shows a list of subscriptions for only customerId 1002 (2 in the list).
- Internal Server Error - has no query param, but clicking on Headers shows that it has a Header that none of the other examples have. X-mock-response-code with a value of 500, and a completely different response.
    

Now go back to the original request, Get all subscriptions, and turn on the customerId param with a value of 1001. Try it again with a value of 1002. When using Postman’s Mock Service to mock an endpoint, Postman will match query params to examples and return the example’s response instead of the generic response. Pretty cool!

##### Step 2 - Collaborate with the API developer and propose an addition to the examples

We know that we are only going to offer AI content to those customers who have subscribed to the AI service. Therefore, we could use the examples we learned about above to return a customer with an active AI Service subscription.

However, this collection is View Only. We cannot make any modifications to it. Let’s shoot a comment over to the developers for some help.

- Select an example that is close to what we want added. “Subscriptions by Advanced Customer” should do the trick as it already has a response with 2 subscriptions
- In the upper right hand corner you will see the icon for comments. Click on it to expand the comments section:
    

<img src="https://lh7-us.googleusercontent.com/1xIoGNg1i2jbDnthGJcbHFwyjZ7SgVh9SQtxXpWr3sFRSlx-uxnNPGpomr41lJSY8lh7_3JEaQ06tORDetakMjWuMGe0WkO8dmowMyByExBvg_PqxmmUsqEKnVxxTS6Iw15OjoJVoQ4hwKbXzbG9H-E" width="528" height="450">

- Before adding the comment, think about what we want. We want a new example with the following features:
    - Name: Subscriptions for an AI Customer
    - Trigger: Customer Id of 1003
    - Similar to the advanced example, however we want the response to contain this JSON:

``` json
{
  "id": "fb461d30-871f-4eaf-9436-892d21e09e75",
  "customerId": "1003",
  "plan": "ADW-MSTS-ADV-AI-SERVICES",
  "status": "active"
}

 ```

- Go ahead and leave a comment with the details above. Make sure you tag an instructor on the comment.
    

#### Setting up to work on the API

Well, we heard back from the devs and they won’t be able to create a new example for us for a few weeks (and yes this is a bit contrived, but go with it). We can get started without them by forking the repository so we can save our changes in our own workspace. From that fork, we can do our own testing and dev workflow as well as potentially issue a pull request to the original developers so they can incorporate our changes into their API. We won’t be going through the PR flow today, but it is a fairly easy to see where it is done. Let’s get started

##### Step 1: Create a new workspace

We’ll create a new workspace for our internal team to collaborate on our user story and build out v2 of the Recommendations Service with AI support. We’d normally name our workspace to facilitate others finding information about our API, however in this case, since we are in a classroom setting, we’ll tweak that slightly and prefix our workspace name with a personal identifier. For instance, if I am building a Recommendations V2 service and go by the nickname erds, when naming the workspace in this classroom setting, I'd use `erds-Recommendations-V2` as the workspace name.

Since our internal team will be collaborating on this API and it's not fit for general consumption yet, we’ll set the visibility of this workspace to Private during its creation. You’ll also need to come up with a summary for the workspace. Follow the steps here to [Create a new Postman workspace](https://learning.postman.com/docs/getting-started/first-steps/creating-your-first-workspace/) with the Blank Workspace template and the parameters above.

##### Step 2: Fork the collection to your Private Workspace

Now we need to fork the Subscription Service we were looking at earlier in order to make the example modifications for our integration testing.

- Navigate back to the Subscriptions Service - API Documentation collection we found earlier in the Shared Services workspace
    

<img src="https://lh7-us.googleusercontent.com/io_kGgPoXItK4ojgupo63KsqRf4Lck7xu3bv1sDQNHm4Gz-gXtwj2MWE4uIkooqhtcw1WLhS6_7boKrAtisLQotsgSNcftqMGIRwBy09L2qF8_7SXocC7V_UGOdSUzXJBeHulgGXkYERxaTisMcKvwE">

- Select Fork in the upper right corner
    

<img src="https://lh7-us.googleusercontent.com/yJ3LFkpCGDKNWuMZu1rS-d2OE0tXBag1ut2NBDboPvwI7XEvtVwQ2xag9TDjAAaK-Yb2XbRn_5Sg_Cy7jU8u70s0laIb9b5FnLQzvbuehphJjVhSQlB__jmYY4MRihux-Qutmd-Q24jq0Oa4j0GFgps">

- Enter a name to identify your fork, and ensure that the Private workspace you created earlier is the destination for the fork. Also ensure that Watch Original Collection is checked so you will be updated on any underlying changes. Once complete, click on Fork Collection
    

<img src="https://lh7-us.googleusercontent.com/Nuqovl91z_wduFk9nwU7pMhrf1NUvMBs_ElfyJTA7ULoKZvHd6nTWRqpX_iEr8EEpPKI3RgaJ1lapMgKN-YwL8mVLdJ9aibqcheN1g2HrxDoAfffwtdPPddSBXmzGE6QPaHDJ-yVRSrPm3ABc7SWkNU">

When fork creation is complete, Postman will navigate to the forked collection in your Private workspace. You can freely make any changes here without impacting the original collection. But let’s hold off on those until the next lab.

##### Step 3: Fork the Environment to your Private Workspace

In the first part of this lab, we saw the power environments with mocks. Unfortunately, those environments are not automatically brought over with the collection fork. In order to maintain use of the mocks from the original collection, let’s go ahead and fork the environment over as well

- Navigate back to the Shared Services workspace we used earlier, and this time select the Environments tab on the left.
    

<img src="https://lh7-us.googleusercontent.com/oHP6LuSuyWnWVeEyYj0sRr4jBzJIC4pD1baNCI6ScaFdwEDKGMojGTGUsLCu98vJp3mxljyTii83GadlkXtT0Rgkozaij8hRJbZduaXHodkWm0SKl083yEzq_C_J4JeAj2nbn5khl0CmTZNuKBHMU20">

- Select the Subscription Service - Dev environment in the list and follow the same forking procedure as we did for the collection
- Back in your private workspace, navigate to the Subscription Service - API Documentation fork you created and expand the drop down and select the Get all subscriptions request.
- Choose the newly forked environment from the dropdown in the upper right:
    

<img src="https://lh7-us.googleusercontent.com/UXj4J5gzCOXYbjsbNbXE6GTgwhf8UowWnWHSUOJMHdeROYbhN4V7_8uQpgPAYeCxt-evAmN7YsMZ_AXB5THEv_3mAmQp49rkW5P4HNp8JlrVgJgPoQiKjY7Gdtz-FsACnl6wNams1SB5Z1gcmr6LI-o" width="462" height="583">

- Click on Send and ensure you get the same mock response you received during the earlier portion of this lab.
    

#### What did you Learn

- Finding APIs using the Postman Private API Network
- Fundamentals of collaborating with team members on your Postman Enterprise instance
- Creating workspaces
- Commenting, Forking, Watching
