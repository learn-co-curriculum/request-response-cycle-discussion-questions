# Request Response Cycle Discussion

A very common question in technical interviews for web developers is, "What happens when you type the name of a website like 'google.com' into your browser and press Enter".

It is definitely a good idea to take some time to review all the steps involved. For now, your job is to discuss with your group a high-level overview of that process.

Be sure to frame your discussion in terms of the **Request Response Cycle**.

Some questions to keep in mind:
- In which part of the process is the request made and what is making the request?
- What type of request is being made?
- What sends back the response and what is included in the response?
- What is a status code?
- What does the browser do with the response?

## Creating an Issue with a Post Request

By now you have probably made a GET request to an API to retrieve some data.  We can also make a POST request to an API when we are creating or saving new data.

Your task is to use [Postman](https://www.getpostman.com/) to make a POST request to the Github API to create an issue on a repository of yours. When you are done you should be able to refresh the page of the repository and see the issue you have created.

- **Step 1:** Choose a repository of someone at the table and make sure that in the Settings of that the repo (click the small gear icon at the top) the 'Issues' checkbox is checked.

- **Step 2:** Read the [API Documentation to create an issue](https://developer.github.com/v3/issues/#create-an-issue).  This means that you will be making a POST request to `https://api.github.com/repos/:the-repo-owners-username/:the-repo-name/issues`

- **Step 3:** We'll need to send some additional information along with the request, the API docs tell us that a title parameter is required in the body of the request.  In Postman, click the 'Body' tab of the request and select the the 'raw' format.  Add in the body of your request, it will be something like this:

  `{"title": "My issue Title", "body": "what a large issue"}`

  \*\* *Don't forget to make all the keys and values Strings*
  
  Following the documentation, what other key value pairs can you add to the body of the request?

- **Step 4:** The Github API needs to know who you are. Go to your [Github Account Settings](https://github.com/settings/profile) and click 'Personal Access Tokens'

  Click 'Generate New Token' and give your token 'repo' and 'user' scope. Generate the token and copy the long string

- **Step 5:** Now you will need to add this token to the headers of your request.  In Postman, add a key/value pair to the Headers. The key should be `Authorization` and the value should be `token PASTE-YOUR-TOKEN-HERE`.

That should do it! Check the repository to see the newly created issue, if you get an error try to use the error message to figure out where you need to change the configuration of the request.

With your table discuss how you think Github's servers process your POST request once it is received.  Is anything persisted? Did the databse change?
