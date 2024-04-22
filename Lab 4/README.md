## Lab 4: Publishing V2 of the Recommendation API

#### Duration

20 mins

#### What you will Learn

After Lab 3, you have a prototype collection with a mock backend that others can take for a test drive and give you and your team feedback. After you iron out any bugs or process gaps, you can convert this collection to an OpenAPI Specification, generate code, and promote the API through the entire SDLC. During this process, Postman continues to provide value by being a centralized landing zone for your:

- API Documentation
- API Testing
- Debugging
- Demos
    

However, for this workshop, we are going to skip that process and get to the point where your API is ready for broader consumption by your colleagues in alpha, beta or even GA.

You now want to move your API Documentation from the private workspace that you are now working on to a “Team Workspace” and eventually to the enterprise Private API Network to make your API discoverable by other enterprise teams.

With this lab, we will focus on:

- API Publishing for consumability and re-use
- Collaborating on a published API
- Organizing APIs through Private API Network
    

#### What you will do in this Lab

- Migrate your API to a Team workspace
- Publish your Postman Collection on the Enterprise Private API Network
- Bonus Challenge: Make changes to your collection
    

#### Migrate your API to a Team Workspace

You’ve created a pretty solid V2 spec for your API and since other teams are waiting on the spec to deliver their user stories, it is time to change the visibility of the Product Recommendation API to Team visibility.

**Note: Since we’ve already prefixed the collection and environment with a unique handle (i.e. erds-Product Recommendation API), there should be no collision in the team workspace.

##### Step 1 - Fork the Collection

- Navigate to your private workspace and select your Product Recommendation API. Select Fork from the top menu:
    

<img src="https://lh7-us.googleusercontent.com/jCHXAG1OB3WWER42suf_V__AL9WebeUJoR6lx2U4rGY2HWFHCQMJqAEOh_Eq_3qJw4ZmmaGxUqs-UC0CfbdoIF0fQrjtlj3fHXhc0iYrh0hGpmjc8-UwTv17U4w8eYJfDbgLh4gQYgrlD2FbFtXcTZw">

- For workspace, select Retail Services
    

<img src="https://lh7-us.googleusercontent.com/kf3hX9lvg1xgbsThQM823oSCvxtNLoY-8qnTVJoPpL8Ug-_Hgm7vpekDx4mMqXrYrEdSuwzFR4meyJekPFI3wBbHgzNwWgBJVvLmK0MrNYnYdpnRPZyhrrP-ySv8bIuY7mdRRloiN1Rxf1cTaIySROs">

- Click on Fork Collection, and Postman will take you to the new fork in the Retail Service workspace:
    

<img src="https://lh7-us.googleusercontent.com/2htF10sIsbg0_xqMAm-tyrbrbywRd1IWWJK3gnP2Q3_wdou_3V_PfU47FYGAep_r0VUAAF7GmxetERm3qsoJdqKhwSpCFDZvA9CIBek09zLe5-djsfkzSuTHF2KVsgqtQ0PUlbCmyBmc_eo9PuwbUG8">

##### Step 2 - Fork the Environment

- Navigate back to your Private workspace
- Select the Environments tab and find the Product Recommendation API mock environment which is prefixed with your handle
- Go ahead and fork this environment to the Retail Services workspace
- In the Retail Services workspace, assign your forked environment to your forked collection and test out your API
    

#### Publish your Collection to the Private API Network

- Make sure you are in the Retail Services workspace
- Select the top level of your Product Recommendation API collection to bring up the collection overview
- On the right side of the overview, you will see the Request to Add button, click on it
    

<img src="https://lh7-us.googleusercontent.com/CwxENr_jKja3oRNxBZJAPbanR6-SM0d63wYn3nh8t4CzhbOVNDf8KLNRZPgfb5VFEZhUXXGRc_refur3-6seWU-62VygrBgatgWKn0hyBkwyO1HcYJXn7ReE7QYYgsL8KDjXDCnTRlVuzBKD1tUuaPk">

- Since you only have rights to publish to the Retail Services folder of the Private API Network, you will see the generic Request to Add for all folders except the Retail Services. If you wanted to publish to an area that you do not have access to, you would click on Request to Add and a Private API Network admin would review your request and decide on whether to publish or not.
- We want to publish to the Retail Services folder, so select that from the list. The button will change to Add Collection, because we have publish rights to that folder.
    

<img src="https://lh7-us.googleusercontent.com/-FQsQg4eXTARwavd-PSppn0taJhcP4lm1ZJ-Bf89RubvznE_iH6-mWBG0UQHSGew52VIh5BGkGJy3f6wdjcLGsoV9mV7BMdumDiGVr7rVkuMYrUFs7PVTese55c8oH7ugtasrSMKRiEao3RNqryh16M">

- Click Add Collection
- Navigate to the Private API Network as we did in Lab 1, and review your addition to the internal network
    

#### Bonus Challenge: Make Changes to your Collection and Publish

##### Step 1 - Update your private collection

- Navigate to your private workspace
- Make a change to the Product Recommendations API. Please note that this will not have any impact on the published collection
    

##### Step 2 - Publish your changes

- Go to the Retail Services workspace and Team workspace and “Pull Changes”
    

<img src="https://lh7-us.googleusercontent.com/Yomj0v3FMlQ2811Ge6ocLflOnWB83NVZepw9gsl1Wd3LPUDZnikoYiTM1EYK2hNI6daeprAB0nzNDBVXczGz3KSkFFvU37dsRwqyqkVRpp-fd3nE4zrsSg1Tz-88k2TUurxHOt7PaLWMpVrDg9nKk9I">

- Step 3: Notice that the Collection in the Private API Network gets updated
    

#### What did you Learn

- API Publishing for consumability and re-use
- Collaborating on a published API
- Organizing APIs through Private API Network
