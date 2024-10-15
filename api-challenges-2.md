# API practice challenges part 2

In the [previous section](https://github.com/LearningNerd/intro-apis-workshop/blob/master/api-challenges-1.md), we tested out a couple of silly APIs to learn about reading API documentation, viewing headers and sending our own, requesting different data formats, and supplying our own query parameters.

So far, we've only tried out ***public APIs*** that don't require you to set anything up to identify *who you are*. But many APIs, if not *most* of them, do require you to identify yourself using an **API key** or a **personal access token**, which is basically a very long password that *only you* have access to.

So next, let's try out an APIs that requires an API keys!

<hr/>

## Challenge 1: Try one of NASA's APIs with their demo API key

Some APIs will let you test out their API using a fake API key; they just limit how often you can use their API while in this "testing" mode. To get full access to their API, you still need to create an account with them and get a real API key. [**NASA's APIs**](https://api.nasa.gov/) are one example of this pattern. Let's try it out!

**Your challenge:** Request some fun astronomy facts from NASA!

  1. First, use cURL to access NASA’s Astronomy Picture of the Day by requesting this URL: `https://api.nasa.gov/planetary/apod` ***Uh oh, it didn’t work!*** Why not?

  2. Look at [their API documentation](https://api.nasa.gov/) to figure out how to get this to work. The response body should contain JSON formatted data with some fun astronomy facts!

<br/>

## Challenge 2: Use more than one query parameter

We've used *one* query parameter in our previous API practice challenges, but you'll often need to provide *more than one* parameter to request more specific information.

To provide multiple query parameters in a URL, end of the URL looks like this: `?param1=value1&param2=value2`

**Your challenge:** Look at NASA's API docs again and figure out how to grab the info for NASA's Astronomy Picture of the Day for **December 31st, 2023**. Do this in cURL.

<br/>

## Challenge 3: Look at JSON data in your web browser

As we saw in previous challenges, web browsers know how to display data formatted as HTML -- that's what all websites look like under the hood! Browsers can also show images if you navigate directly to an image file (which cURL doesn't know how to do). Well, it turns out browsers can also display all sorts of other data formats / file types, including JSON data!

**Your challenge:** Use your web browser to access the same URL from the previous challenge. What does it look it?

<br/>

## Challenge 4: About the weather

Browsers are almost magical and can display many types of data. You've already seen that APIs often offer options to request data in a specific format (JSON, HTML, XML, ...).

Go to [wttr.in](https://wttr.in/) to check the current weather, because who wouldn't want that? But does the location match your location? There's a good chance it doesn't...

<br/>

## Challenge 5: Options!

Go to the [wttr.in help page](https://wttr.in/:help) and look at the possible options.

1. What would be the URL for the weather and forecasts in Groningen?
2. What would be the URL for only the *current* weather in Groningen (so without the forecasts)?
3. What would be the URL for only the *current* weather in Groningen, but displayed in French?
4. The help page only gives a limited number of options; on the project page, you can see how to request the data in [JSON format](https://github.com/chubin/wttr.in?tab=readme-ov-file#json-output). What do you need to add to the last URL to request the weather in JSON format?

<br/>

## Challenge 6: The weather in the terminal

You've used cURL before to call APIs. On the [wttr.in help page](https://wttr.in/:help), you also see (under *Localization*) a number of cURL example commands. What happens if you execute the following there?

`curl wttr.in/Groningen?0`

This is the same as what you saw earlier in the browser, but now as text! The site determines based on the User-Agent sent with the request (cURL in this case) that we're likely using a terminal and returns a text version of the weather report that can be displayed in a terminal (including the colors)!

<br/>

## Challenge 7: Use the `POST` HTTP method to create a repo on GitHub

We've mostly been sending `GET` requests to these APIs. Remember, the `GET` method is used to ask for some information, *without modifying any of that information.* The `POST` method, on the other hand, is used to ***create*** something new on the server that you're communicating with.

In cURL, we use the `--data` flag followed by a string of data (enclosed in quote marks) to send information in the ***body*** of our request. When cURL sees that flag, it automatically sends this as a `POST` request!

  > **Vocabulary note:** GitHub uses the word "repository" or "repo" for short to refer to your projects hosted on their website. Each project is a collection of files, which would normally be the code for a software application (or something else like a book of poems or whatever you want!)

**Your challenge:** Create a project on GitHub with their API by following the steps below:

   1. First, you need to create a free GitHub account.

   > GitHub is a social network for programmers and also the world's largest collection of source code! It's used for collaboration not just for code, but also for writing fiction, sharing open data, and getting feedback on legislation for local government, among other cool things!

  2. Request a ***personal access token*** by [following GitHub's instructions here](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/).

  > **Remember: treat your personal access tokens like passwords!** Don't share them anywhere or store them in any insecure places!

  3. Copy the cURL command below into your plain text file, and replace **YOUR-TOKEN-HERE** with your actual personal access token:

```bash
curl -H 'Authorization: token  YOUR-TOKEN-HERE' https://api.github.com/user/repos  --data  '{"name": "test-repo"}'
```

  4. Finally, copy and paste that command into your command line and run it!

  5. Check your GitHub profile page to see if it worked! You should see your new repository (in other words, your project) appear in your list of repositories!

  > To get to your GitHub profile page quickly, go to `https://github.com/YOUR-USERNAME-HERE` and replace **YOUR-USERNAME-HERE** with your actual GitHub username.

<br/>

## Bonus challenges:

### Bonus challenge 1:

Look at [GitHub's API documentation for working with repositories](https://developer.github.com/v3/repos/) to figure out how to **edit** the name of the repository you created in the previous challenge!

Which *HTTP method* do you need to use here?

### Bonus challenge 2:

Figure out how to **delete** the repository you created in the previous challenge! And which HTTP method do you need for this?

<hr/>

:trophy: ***Congratulations!*** Now you know the most important basics of using third-party APIs! At this point, the sky's the limit as to what you can create using the countless APIs that other software developers are providing!
