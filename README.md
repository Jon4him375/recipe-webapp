# recipe-webapp
A project that I'm currently working on. I'm using React/TypeScript for the frontend and NodeJS for the backend. 

I utilized the Google Custom Search API to bring in millions of search results that are specifically only recipes. Using those results, I take the 1st page urls, send it to the NodeJS service, where it scrapes each site for only the important information (e.g ingredients, directions). As every site is unique, rather than hardcoding each website structure, I created several algorithms that generally work for all the websites. Using these methods, I'm able to extract the important data from around 99% of all the recipe sites. This all takes about 300ms to complete (although I hope to get it down much lower), where I then send all this data back to the React App in JSON format, where I fit it all into custom types. 

In the React App, I have a kind of "middle-system", using TypeScript, where I take the raw JSON and convert it to TypeScript types, where it can be easily used by the rest of the app for whatever. After this is done, I'm left with only one array of "Recipe" types, each item having a name, description, url, etc., but also including an array of Ingredient types. I take this one array of recipes, and put it into an application-wide Redux store for my React components to display this data in simple way. All of this, including the web-scraping, takes around 450-500ms to happen. 

I'm currently working on taking each ingredient and extracting the unit, amount, and food item into separate variables in the Ingredients type. That way, I can convert from imperial to metric, easily change the serving size, and have a shopping-list/meal-planner using the different grocery store APIs. 

