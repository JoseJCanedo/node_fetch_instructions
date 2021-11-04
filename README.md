#  Nodejs fetch

For the remainder of the app we will cover node fetch. For node fetch we will use the [node-fetch](https://www.npmjs.com/package/node-fetch) npm package. 

Start by installing node-fetch:
```console
npm install node-fetch
```

Once it is installed you can follow through the instructions on the npm page in the link above. Youll have to import the package in your index file at the top. 

Now create a new path that is a get method for the ending url '/zip'.

Youll need to also create a html page to return back to the front end within the views folder. This will be another EJS file. Within that file I want you to create a page that has a heading that says "Select a country and enter a zip code"

Below that heading I want you to create a form that takes 2 parameters. A dropdown with a list of 10 countries outlined by the API listed below and an input that takes number entry only. Youll need to run validation on this before submitting the form.

When you submit the form youll have to hit a post on the back end again. So youll have to go back to the index file and create a post route. You can make it '/zip' also, but make sure it is a post. 

Within that post youll write your fetch statement like you did with the mongo db calls for the to-do list. The app will use fetch to get data and then redirect to the get after it has set a global variable with the data.

Remember youll get 2 pieces of information from the front end. The first is the country code from the dropdown. The second is the numbers (zipcode) from the input. 

Use those two pieces of data to call the api sing fetch. As you see in the fetch documentation you can use await to fetch, or get, from a url end point. We will not be using await as we want to run sequentially.

For that to be the case you will want to write the fetch a little differently. You will follow the basic outline
```javascript
fetch('your URL with parameters goes here')
    .then(res => res.json())
    .then(data => {
        // set the response to your global variable here
        // redirect to the /zip page
    });
```

Return the html page from the the get call, but pass the data to it so you can see the information below the input form. So you should have the heading, a form with 2 imputs (select and a text input), a button to submit the form, and only after a submit the information returned back from the api.

The api you will use for this, as you have guessed based on the inputs is a zipcode API [(https://api.zippopotam.us/)](https://api.zippopotam.us/). 

### Submission Information
The completed node app
- To-do portion with the 4 methods, fetch, delete, update, create
- App connected to your mongo db instance
- Add a css sheet. Style the form and center it. 
- A second page that takes the zipcode and country and returns the data if there is any
- Second page should also be styled. You can use the same styling as the to-do page.
