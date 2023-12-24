# **<span style="text-decoration:underline;">Team B CampusWire ReadMe</span>**


# **The Repository**



* The original repository (where the team created the project) can be found at:
    * [https://github.com/Aryan-Dang/Campuswire-Analytics-team-B](https://github.com/Aryan-Dang/Campuswire-Analytics-team-B)


# **Installation and Running Instructions:**



* **Installation**
    * **GoLang**: Please install and add Go to your PATH from the link below:
        * [https://go.dev/doc/install](https://go.dev/doc/install)
        * Make sure GOPATH and GOROOT environment variables are properly set up when installing
        * Our GoLang version is 1.21.3
        * If any modules break, you can manually install them by running the following with the module link in the “dependencies” section
            * go install {link}@latest
    * **Javascript:** Please make sure Javascript is installed. Modern browsers should come with JS installed, but in the off chance that it is not, please install Google Chrome from the link below:
        * [https://www.google.com/chrome/](https://www.google.com/chrome/)
        * Installation instructions: [https://support.google.com/chrome/answer/95346](https://support.google.com/chrome/answer/95346)
    * **NodeJS**: Please install NodeJS from the link below:
        * [https://nodejs.org/en/download](https://nodejs.org/en/download)
        * Make sure NodeJS is also added to your PATH
* Please open up **two **terminals and **cd **into the folder **“Campuswire-Analytics-team-B”** for both.
* **In Terminal 1: (backend hosted on localhost:8080)**
    * cd backend/fiber-mongo-api-1
    * go get . (installs dependencies)
    * go run .
* **In Terminal 2: (frontend hosted on localhost:3000)**
    * cd frontend
    * npm install (installs dependencies)
    * npm start


# **Dependencies:**

**Backend**



* Golang
    * Fiber
        * Link: [https://github.com/gofiber](http://github.com/gofiber/fiber/v2)
        * “Express inspired web framework built on top of Fasthttp”
        * API connections
    * Mongo Driver
        * Link: [go.mongodb.org/mongo-driver](https://pkg.go.dev/go.mongodb.org/mongo-driver)
        * Database connection and queries
    * strutil
        * Link: [github.com/adrg/strutil](https://github.com/adrg/strutil)
        * String similarity calculations for search
    * GoDotEnv
        * Link: [github.com/joho/godotenv](https://github.com/joho/godotenv)
        * Load .env file for MongoDB connection string

**Frontend**



* Javascript
    * React
        * [https://react.dev/](https://react.dev/)
        * State and component-based library to build the app/web UI
    * TailwindCSS
        * Link: [https://tailwindcss.com/](https://tailwindcss.com/)
        * A utility-based CSS framework to create components and style pages
    * DaisyUI
        * Link: [https://daisyui.com/](https://daisyui.com/)
        * Pre-built, well-designed components built on TailwindCSS
    * Axios
        * Link: [https://axios-http.com/docs/intro](https://axios-http.com/docs/intro)
        * HTTP client that allows us to perform API requests to backend endpoints
    * ChartJS
        * Link: [https://www.chartjs.org/](https://www.chartjs.org/)
        * JavaScript charting library to create vibrant and interactive graphs
    * NPM
        * Link: [https://www.npmjs.com/](https://www.npmjs.com/)
        * Package manager used to install different libraries for the frontend


# **Database:**



* You can find the database on MongoDB Atlas:
* The following credentials are for **both **the** **email account and the database login
    * Link for gmail: [Sign into gmail (if needed)](https://accounts.google.com/v3/signin/identifier?continue=https%3A%2F%2Fmail.google.com%2Fmail%2Fu%2F0%2F&emr=1&followup=https%3A%2F%2Fmail.google.com%2Fmail%2Fu%2F0%2F&ifkv=ASKXGp1JuIZCFmy6exbDFWFgb_up0Rwo8LuDLCR2zzxLbvt1tjrrj5GKaMZvNSLB1r4KGQ1H026ykQ&osid=1&passive=1209600&service=mail&flowName=GlifWebSignIn&flowEntry=ServiceLogin&dsh=S1594242039%3A1702685193673986&theme=glif)
    * Link for database: [Sign in to MongoDB](https://account.mongodb.com/account/login?nds=true&_ga=2.251133894.1530343568.1702685240-1186610899.1702685240&_gac=1.153582922.1702685344.Cj0KCQiAj_CrBhD-ARIsAIiMxT9g2nvR7oSPsGzM7ZzNLKspcJxuItkPCuJpuABYQNCsNCoHIBB-UogaAlDHEALw_wcB)
    * **Username (email): **teambguest@gmail.com 
    * **Password:** Guest@TeamB#MongoDB
* Data Structure (Collections)
    * Day(1-92): The post data from the feed over 92 days
    * MLDay(1-92): ML chosen topic words
    * UpdatedML(1-92): ML collection but includes relevance percentages


# **User Flow:**



* The first tab on the top of the page with the heading eg: “DAY 1 - DAY 54” allows users to switch between a period of dates to get the dashboard updated including graphs, engagement table, etc up to a particular date.
* On the top middle of the dashboard is the **Search Bar** that allows users to search for a specific post, comment, or author using keywords.
    * Clicking on a search result from the dropdown menu opens up a new page with the specific post details.
    * The dropdown menu also indicates on its right if the searched word is mentioned in a post title/author name/comments/etc.
    * Both exact and similar searches are available in order to make sure related information is readily accessible and not overly limited by specific phrasing.
        * String similarity is done using Levenshtein distances
* The **Engagement Table** on the left has a filter that allows the user to sort the engagement data based on the number of posts, comments, postTime, commentTime, or endorsedComments
    * This allows the user to see the top commenters/posters, etc, and gauge the engagement level of the class.
    * Clicking on a specific student on the engagement table opens up a new page with their engagement details– their name, ID, post count, comment count, all the posts they have made in the date range, and an overview of the posts(title, content and view count). Changing the day range on the post details page updates it with the data from the new range.
* The **Recent Posts** table in the middle of the page shows the top 5 posts from the selected day range with name, title, answer count, and view count.
    * When clicked on a specific post, it opens up a new page with the post details including Author, title, content, comments, etc.
* The **Pie Graph** on the bottom left displays answered versus unanswered questions data for the selected day range.
    * It also shows the exact number of posts when hovered over the graph
    * Data can be updated to a new day range by changing the tab at the top of the dashboard
* The first **Bar Graph** next to it displays the number of posts made on a day for the selected day range
    * It also shows the exact number of posts when hovered over the bars
    * Data can be updated to a new day range by changing the tab at the top of the dashboard
* It is a **scrollable graph** that has **line graphs** for unread posts and view counts when scrolled after the bar graph.
    * They have the same features as the bar graph and work in the same way to update the day range.
* The **Trending Topics Table** on the right displays the top 10 trending topics/words from day 1 to the current(selected) day.
    *  Clicking on a topic opens up a new page with all the posts that use the topic word with the post details as a table.
    * There is a search bar on this page that allows users to further filter and search for a specific topic from these posts.
* The color of the app depends on one’s device settings. We designed the UI to be based on light mode (white background), but if desired, changing your device to dark mode will also change the appearance accordingly.

# **Design Choice:**

**Why Golang?**

Our team made the decision to work in GoLang for the backend in order to learn a new language. Nobody on the team, prior to working on this project, had used Go. However, since this class is meant to be a learning experience as well as a simulation of a more professional environment, we decided to use this chance to simulate having to create a project in an unfamiliar language. Golang does not provide any particular advantages for the purposes of this project, and Python is an equally viable, if not better, alternative. However, the learning experience brought by using Go has helped us understand how to work as a team to tackle a challenge as large as learning an entirely new language, and we have definitely learned plenty as a result.

**Why React?**

Our team decided to use React for the front end for the opposite reason of the backend. Considering that we were already challenging ourselves with a brand-new language for the back end, we decided to go with a framework that is well-documented, widely used, reliable, and comfortable for our team. That ended up being React, a language that a large portion of our team had at least seen if not worked with prior to the beginning of the project. A portion of the main members of our team were comfortable and experienced in the language, and it granted us time and effort to spend towards the more fresh language, while also allowing us to create a stylish and professional front-end due to the prior experience.

**Why MongoDB?**

We decided to use MongoDB for our database for a couple of reasons. We had at first considered using an SQL database such as Postgres or MySQL, but we quickly realized that the data we are working with is given to us as a JSON. It is much more difficult and cumbersome to turn a JSON document into one or more relational tables in comparison to leaving them as a document, which is how MongoDB stores its data. Using MongoDB, as such, came as the natural choice due to its reputation and ease of use when working with JSON-style documents (MongoDB uses BSONs, which for all intents and purposes are just more compact JSONs). Additionally, it made the creation of new data easier to store, as we could simply create a new collection to upload the corresponding documents.

**UI Design/Decisions**

Before working on the code, we decided to visually plan out a prototype of how we wanted our product to look and be structured. In order to do so, we met up as a group and got to drawing. We knew that our product would be an analytics platform, so we decided to begin visualizing a dashboard interface. In order to come up with the actual features, we brainstormed various user stories and assigned them points and priorities to determine what we thought was the most important/relevant set of features (engagement, a feed, and graphs for various trends). After choosing the highest priority user stories, we used Figma to create and design a landing page, organizing our features into neat components, and deciding the best format to represent them (e.g.: a table for engagement, a bar graph for post counts, etc). We then designed (in Figma) other pages for more detailed views of a single feature, such as a user info page and a post info page. After that, the front-end team began working on more stylistic choices such as themes and color choices, and the feasibility of the current design.

**JSON Parser**

In order to truly begin our project, we needed the data. As mentioned above, we decided that we wished to use Go for our backend, and MongoDB to store our data. This meant that we now needed to learn how to take the data (a series of JSON files) and store them in MongoDB. Before we did this, we discussed how we would store the data- since each file represented a day, we decided to turn each file (and thus each day) into its own collection. After these decisions came the coding. We needed to learn how to parse a JSON file in order to extract the relevant data from the files and then upload them into MongoDB. The first issue we encountered was defining the JSON into a struct. In order to make sure the attributes for each key: value pair in the JSON are properly extracted, we needed to define a struct to model each Post in the JSON. The struct can be viewed in either Parse.go (backend/JSONParser) or in Models.go (backend/fiber-mongo-api-1/models). After defining the struct and storing the JSONS in the structs, we learned how to connect to MongoDB in Go and then used InsertOne() to upload the data into the collections we created. This knowledge then allowed us to continue on to our next step, querying and processing the data from the database.

**Querying MongoDB**

Golang’s Mongo Driver module has two specific functions for querying documents: Find() and FindOne(). However, these functions are difficult to use and reuse without fully understanding every component of the documentation. As an example, we had trouble figuring out how to use the associated FindOptions and FindOneOptions. The documentation does not go very in-depth on the exact types and ways to set these parameters outside of an example. We had to dig deep into looking directly at the type of implementation to understand what parameters are allowed. Expecting all members of our team, who are all new to the language, to go through all of these struggles didn’t seem feasible and efficient. Thus, we decided that having a wrapper to standardize these functions in a more understandable and friendly way would make writing queries a lot faster.

We created a local module in the file backend/fiber-mongo-api-1/mongodb/mongodb.go. Our Mongo wrapper is based on a class-like implementation, where we define a type Mongo that contains the raw mongo-driver client. We created new functions like QueryAll() and QueryOne() that call the original Find() and FindOne(). We can look at QueryAll() as an example. It takes in the minimum parameters needed to look for documents in the database. You can specify the database, collection, or maximum number of results to get. The query and sort parameters are used to set filters and sort criteria. We decided that only these essential values are needed for most queries, and if someone needed to do anything more advanced, they can directly use the raw mongo-driver client. QueryAll() aggregates the results returned by Find(), and returns a list of posts, a data type that is easier to work with. Without this wrapper function, Find returns a cursor, similar to an iterator, that one would need to manually loop through. Other functions also streamline the process.

**Data Preprocessing**

In the same Mongo wrapper module, we performed some basic data preprocessing. When testing and getting the data using individual API routes, we noticed that some texts in posts and comments begin with the string “zzz .” We assume it is part of Campuswire formatting, but we have no documentation or source to reference. The cleanPostText() function removes these strings to make the content look more as expected. The date strings in the raw data also contain extraneous information down to milliseconds. For our purpose, we decided that it is more user-friendly to display just the date and time. The toDisplayableDate() function processes the dates in this way.

**Fiber Routing**

The Fiber module provides a quick and easy way to build our API in a scalable manner. In backend/fiber-mongo-api-1/routes/routes.go, we easily connect routes to specific functions we call controllers located in backend/fiber-mongo-api-1/controllers/controllers.go. Every capital case function like GetPostById() is a controller function used in an API route, while camelcase functions like sortPostData() are helper functions to break up complicated logic or computation. In Golang, all functions that start with a capital letter are able to be exported. This is similar to private/public functions in other languages like Java. If we needed to add a new route, it is as simple as making a new controller function, and then connecting it in routes.go.

**Machine Learning**

We incorporated Topic Modelling using the Latent Dirichlet Allocation (LDA) model to extract trending keywords that belonged to a certain cohort. The model was chosen because of its interpretability and scalability for data sizes and allowed for streamlined preprocessing. 

For this model, we incorporated preprocessing, feature extraction, filtering, and manual hyperparameter tuning. Preprocessing was done by taking away certain words that would likely not be relevant to the topic extraction such as “the”, “she”, and “a”, etc through defining a list of stopwords using the NLTK library’s stopword list and manually adding more words as needed. We then implemented TF-IDF (Term Frequency-Inverse Document Frequency)  for feature extraction which it determines the relevance and significance of a certain word to the collection, which helps select only the most relevant words and form the most common topics. 

Bigrams and Trigrams were also incorporated to help capture words in groups of two or three, which aids in contextualization and allows for better performance. Documents with less than 4 words were filtered out due to the fact that they likely would not provide any useful insights. Lastly, hyperparameter alpha controlled the distribution of topics over documents and eta controlled the distribution of words over topics, where alpha and eta were set to 0.01 (based on best performance accuracy).

We decided to have all of the data processed by machine learning stored in another set of collections within MongoDB directly via our existing Go API. This was done to streamline the front and back-end integration to a simple and seamless process.


# **Testing and Bugs/Limitations:**

**Testing**



* The feature-based design allows individuals to quarantine issues
* Simulating user flow and testing edge cases
* Creating individual routes to see sample responses
    * Localhost + Postman
    * Ex. localhost:8080/day12/posts to get all posts up to day 12
* Ex. Searching up different names in the search bar
    * Some names were showing up that didn’t match the search
    * The bug was that the function returned the post author instead of the comment author

**GetUsersById (/user/{userID})**



* The implementation allows the user to get raw post/comment data or a compact version using query parameters
* Two different structs: VerbatimUserData and CompactUserData
    * Unlike Python, we cannot dynamically change types
    * We are forced to use duplicate code based on the boolean value of the query parameter “verbatim”
* There is a way to avoid this issue by using interfaces and dynamic dispatching
* We kept the redundant code because changing to interfaces would force us to rewrite the entire UserData type
    * For a small project, we decided that this was fine for the time allocated

**Scrollability of Graphs**



* The bar graph component on the web page is scrollable, meaning that there are other graphs the user can view by swiping (two fingers) to the left and right when on the graph.
    * The bug is that this “scrolling” really only works with the trackpad. You cannot click and drag with your mouse to scroll. You can press the scroll wheel and move to the left or right to scroll, but it is finicky and not particularly intuitive.

**Future additions:**

If we (or you!) were to **expand upon the current product**, these are some of the ideas and directions we had been considering implementing if not for a lack of time:



* A login system (primarily for an instructor or TA) perhaps with different views for different levels of users
* Split rankings: rankings for students and ranking for staff according to differing criteria
* New graphs to display different data or trends
* Expand upon ML to add predictions and other interesting features that cannot be derived simply from the data


# **API Routes:**

We decided to split the routes by day to simulate real-time data. What this means is that all routes are in the format of “**GET /**{**day**} … ”. This allows all of our endpoints to become streamlined, and creates a dynamic setting for our data. 

**<span style="text-decoration:underline;">Note:</span>** The day variable in this case simulates the current day that the campuswire forum is in. This means all resulting data will be **cumulative** to that day. (Day 70 means data from Day1-Day70). Day 70 is also synonymous with the state of the 70th provided JSON file for data.

  

<span style="text-decoration:underline;">Post Routes:</span>


<table>
  <tr>
   <td colspan="4" ><strong>GET</strong> /{day}/post/{postID}
<p>
Gets the post up to a day with the postID.
   </td>
  </tr>
  <tr>
   <td><strong>Path parameter</strong>
   </td>
   <td colspan="3" ><strong>Description</strong>
   </td>
  </tr>
  <tr>
   <td>{day}
   </td>
   <td colspan="3" >The day you want to simulate the data up to. Example: “day20”
   </td>
  </tr>
  <tr>
   <td>{postID}
   </td>
   <td colspan="3" >The postID of the specified post.
   </td>
  </tr>
</table>



<table>
  <tr>
   <td colspan="4" ><strong>GET</strong> /{day}/posts
<p>
Gets all posts up to a day.
   </td>
  </tr>
  <tr>
   <td><strong>Path parameter</strong>
   </td>
   <td colspan="3" ><strong>Description</strong>
   </td>
  </tr>
  <tr>
   <td>{day}
   </td>
   <td colspan="3" >The day you want to simulate the data up to. Example: “day20”
   </td>
  </tr>
  <tr>
   <td><strong>Query string parameter</strong>
   </td>
   <td><strong>Required / Optional</strong>
   </td>
   <td><strong>Description</strong>
   </td>
   <td><strong>Type</strong>
   </td>
  </tr>
  <tr>
   <td>criteria
   </td>
   <td>Optional
   </td>
   <td>The criteria for sorting the list of posts. All possible criteria are views, uniqueViews, answers, publishedAt, answeredAt, modAnsweredAt, comments, titleLength, and bodyLength. The default is views.
   </td>
   <td>String
   </td>
  </tr>
  <tr>
   <td>limit
   </td>
   <td>Optional
   </td>
   <td>The maximum number of posts returned by the route. The default is 1.
   </td>
   <td>Integer
   </td>
  </tr>
  <tr>
   <td>reversed
   </td>
   <td>Optional
   </td>
   <td>Whether the sorting order is ascending or descending. The default is false (descending).
   </td>
   <td>Boolean
   </td>
  </tr>
</table>



<table>
  <tr>
   <td colspan="4" ><strong>GET</strong> /{day}/posts/unique
<p>
Gets all posts published only on this day.
   </td>
  </tr>
  <tr>
   <td><strong>Path parameter</strong>
   </td>
   <td colspan="3" ><strong>Description</strong>
   </td>
  </tr>
  <tr>
   <td>{day}
   </td>
   <td colspan="3" >The day you want to simulate the data up to. Example: “day20”
   </td>
  </tr>
</table>



<table>
  <tr>
   <td colspan="4" ><strong>GET</strong> /{day}/recent
<p>
Gets Name, Author, AnswerCount, and viewCount of all posts from the past 7 days up to the day.
   </td>
  </tr>
  <tr>
   <td><strong>Path parameter</strong>
   </td>
   <td colspan="3" ><strong>Description</strong>
   </td>
  </tr>
  <tr>
   <td>{day}
   </td>
   <td colspan="3" >The day you want to simulate the data up to. Example: “day20”
   </td>
  </tr>
</table>


<span style="text-decoration:underline;">Dashboard Routes:</span>


<table>
  <tr>
   <td colspan="4" ><strong>GET</strong> /{day}/dashboard/engagement
<p>
Gets a ranking of users sorted by a criteria.
   </td>
  </tr>
  <tr>
   <td><strong>Path parameter</strong>
   </td>
   <td colspan="3" ><strong>Description</strong>
   </td>
  </tr>
  <tr>
   <td>{day}
   </td>
   <td colspan="3" >The day you want to simulate the data up to. Example: “day20”
   </td>
  </tr>
  <tr>
   <td><strong>Query string parameter</strong>
   </td>
   <td><strong>Required / Optional</strong>
   </td>
   <td><strong>Description</strong>
   </td>
   <td><strong>Type</strong>
   </td>
  </tr>
  <tr>
   <td>criteria
   </td>
   <td>Optional
   </td>
   <td>The criteria for sorting the engagement ranking. All possible criteria are posts, comments, postTime, commentTime, and endorsedComments. postTime and commentTime refer to the most recent time a post or comment was published. The default is posts.
   </td>
   <td>String
   </td>
  </tr>
  <tr>
   <td>limit
   </td>
   <td>Optional
   </td>
   <td>The maximum number of posts returned by the route. The default is 1.
   </td>
   <td>Integer
   </td>
  </tr>
  <tr>
   <td>reversed
   </td>
   <td>Optional
   </td>
   <td>Whether the sorting order is ascending or descending. The default is false (descending).
   </td>
   <td>Boolean
   </td>
  </tr>
</table>



<table>
  <tr>
   <td colspan="4" ><strong>GET</strong> /{day}/dashboard/graph/postCount
<p>
Gets data for a graph mapping a range of dates to the number of posts made on that day.
   </td>
  </tr>
  <tr>
   <td><strong>Path parameter</strong>
   </td>
   <td colspan="3" ><strong>Description</strong>
   </td>
  </tr>
  <tr>
   <td>{day}
   </td>
   <td colspan="3" >The day you want to simulate the data up to. Example: “day20”
   </td>
  </tr>
  <tr>
   <td><strong>Query string parameter</strong>
   </td>
   <td><strong>Required / Optional</strong>
   </td>
   <td><strong>Description</strong>
   </td>
   <td><strong>Type</strong>
   </td>
  </tr>
  <tr>
   <td>range
   </td>
   <td>Optional
   </td>
   <td>The number of dates up to the current day. The default is 7.
   </td>
   <td>Integer
   </td>
  </tr>
</table>



<table>
  <tr>
   <td colspan="4" ><strong>GET</strong> /{day}/dashboard/graph/viewCount
<p>
Gets data for a graph mapping a range of dates to the number of post views on that day.
   </td>
  </tr>
  <tr>
   <td><strong>Path parameter</strong>
   </td>
   <td colspan="3" ><strong>Description</strong>
   </td>
  </tr>
  <tr>
   <td>{day}
   </td>
   <td colspan="3" >The day you want to simulate the data up to. Example: “day20”
   </td>
  </tr>
  <tr>
   <td><strong>Query string parameter</strong>
   </td>
   <td><strong>Required / Optional</strong>
   </td>
   <td><strong>Description</strong>
   </td>
   <td><strong>Type</strong>
   </td>
  </tr>
  <tr>
   <td>range
   </td>
   <td>Optional
   </td>
   <td>The number of dates up to the current day. The default is 7.
   </td>
   <td>Integer
   </td>
  </tr>
  <tr>
   <td>unique
   </td>
   <td>Optional
   </td>
   <td>Whether to use all views or only unique views. The default is false.
   </td>
   <td>Boolean
   </td>
  </tr>
</table>



<table>
  <tr>
   <td colspan="4" ><strong>GET</strong> /{day}/dashboard/graph/answerData
<p>
Gets data for a pie graph of answered to unanswered posts up to that day.
   </td>
  </tr>
  <tr>
   <td><strong>Path parameter</strong>
   </td>
   <td colspan="3" ><strong>Description</strong>
   </td>
  </tr>
  <tr>
   <td>{day}
   </td>
   <td colspan="3" >The day you want to simulate the data up to. Example: “day20”
   </td>
  </tr>
</table>



<table>
  <tr>
   <td colspan="4" ><strong>GET</strong> /{day}/dashboard/graph/unread
<p>
Searches through all the days up until the specified date to check for whether this post has been read. Iterates through all the posts checks whether the post has been read and makes sure there are no answers to the post.
   </td>
  </tr>
  <tr>
   <td><strong>Path parameter</strong>
   </td>
   <td colspan="3" ><strong>Description</strong>
   </td>
  </tr>
  <tr>
   <td>{day}
   </td>
   <td colspan="3" >The day you want to simulate the data up to. Example: “day20”
   </td>
  </tr>
  <tr>
   <td><strong>Query string parameter</strong>
   </td>
   <td><strong>Required / Optional</strong>
   </td>
   <td><strong>Description</strong>
   </td>
   <td><strong>Type</strong>
   </td>
  </tr>
  <tr>
   <td>range
   </td>
   <td>Optional
   </td>
   <td>The number of dates up to the current day. The default is 7.
   </td>
   <td>Integer
   </td>
  </tr>
</table>



<table>
  <tr>
   <td colspan="4" ><strong>GET</strong> /{day}/dashboard/topics
<p>
Uses an ML algorithm to determine the trending topics as words and their relevance as a percentage, using the state of the feed from the parameterized day. To increase computation speed and consider that we are using static data, these results have been stored in a separate collection with the relevant data precomputed.
   </td>
  </tr>
  <tr>
   <td><strong>Path parameter</strong>
   </td>
   <td colspan="3" ><strong>Description</strong>
   </td>
  </tr>
  <tr>
   <td>{day}
   </td>
   <td colspan="3" >The day you want to simulate the data up to. Example: “day20”
   </td>
  </tr>
</table>



<table>
  <tr>
   <td colspan="4" ><strong>GET</strong> /{day}/search
<p>
Searches for some terms inside the titles and bodies of posts and comments. Also searches inside full names. Both exact and similar matches are returned. String similarity is done using Levenshtein distances.
   </td>
  </tr>
  <tr>
   <td><strong>Path parameter</strong>
   </td>
   <td colspan="3" ><strong>Description</strong>
   </td>
  </tr>
  <tr>
   <td>{day}
   </td>
   <td colspan="3" >The day you want to simulate the data up to. Example: “day20”
   </td>
  </tr>
  <tr>
   <td><strong>Query string parameter</strong>
   </td>
   <td><strong>Required / Optional</strong>
   </td>
   <td><strong>Description</strong>
   </td>
   <td><strong>Type</strong>
   </td>
  </tr>
  <tr>
   <td>token
   </td>
   <td>Optional
   </td>
   <td>The token we want to search for. The default is an empty string.
   </td>
   <td>String
   </td>
  </tr>
  <tr>
   <td>deleteCost
   </td>
   <td>Optional
   </td>
   <td>The cost of deleting a character. Used to calculate Levenshtein distance. The default is 1.
   </td>
   <td>Integer
   </td>
  </tr>
  <tr>
   <td>insertCost
   </td>
   <td>Optional
   </td>
   <td>The cost of inserting a character. Used to calculate Levenshtein distance. The default is 1.
   </td>
   <td>Integer
   </td>
  </tr>
  <tr>
   <td>replaceCost
   </td>
   <td>Optional
   </td>
   <td>The cost of replacing a character. Used to calculate Levenshtein distance. The default is 1.
   </td>
   <td>Integer
   </td>
  </tr>
  <tr>
   <td>similarityThreshold
   </td>
   <td>Optional
   </td>
   <td>The threshold for deciding two strings is similar. Values range from 0, which says that all strings are similar, to 1, which says that no strings are similar. The value is calculated using Levenshtein distance. The default is 0.6.
   </td>
   <td>Integer
   </td>
  </tr>
  <tr>
   <td>similarityDistance
   </td>
   <td>Optional
   </td>
   <td>The maximum Levenshtein distance we allow for two strings to be similar. The default is 3.
   </td>
   <td>Integer
   </td>
  </tr>
  <tr>
   <td>similarityMethod
   </td>
   <td>Optional
   </td>
   <td>The method used to judge string similarity. Values can be either distance or threshold. Default is the threshold.
   </td>
   <td>String
   </td>
  </tr>
</table>


<span style="text-decoration:underline;">User Routes:</span>


<table>
  <tr>
   <td colspan="4" ><strong>GET</strong> /{day}/user/{userID}
<p>
Gets data on a user with the specified userID. All posts and comments are aggregated. Extra statistics are calculated like the latest post time or whether the person is a student or staff.
   </td>
  </tr>
  <tr>
   <td><strong>Path parameter</strong>
   </td>
   <td colspan="3" ><strong>Description</strong>
   </td>
  </tr>
  <tr>
   <td>{day}
   </td>
   <td colspan="3" >The day you want to simulate the data up to. Example: “day20”
   </td>
  </tr>
  <tr>
   <td>{userID}
   </td>
   <td colspan="3" >The userID of the user you want to get the data from.
   </td>
  </tr>
  <tr>
   <td><strong>Query string parameter</strong>
   </td>
   <td><strong>Required / Optional</strong>
   </td>
   <td><strong>Description</strong>
   </td>
   <td><strong>Type</strong>
   </td>
  </tr>
  <tr>
   <td>verbatim
   </td>
   <td>Optional
   </td>
   <td>Whether to return raw post/comment data or a compact version. The default is false.
   </td>
   <td>Boolean
   </td>
  </tr>
</table>



<table>
  <tr>
   <td colspan="4" ><strong>GET</strong> /{day}/engagement
<p>
Gets a ranking of users sorted by a criteria. This route is for a possible engagement page. It is currently a duplicate to explicitly separate dashboard and page features, even if they use the same data.
   </td>
  </tr>
  <tr>
   <td><strong>Path parameter</strong>
   </td>
   <td colspan="3" ><strong>Description</strong>
   </td>
  </tr>
  <tr>
   <td>{day}
   </td>
   <td colspan="3" >The day you want to simulate the data up to. Example: “day20”
   </td>
  </tr>
  <tr>
   <td><strong>Query string parameter</strong>
   </td>
   <td><strong>Required / Optional</strong>
   </td>
   <td><strong>Description</strong>
   </td>
   <td><strong>Type</strong>
   </td>
  </tr>
  <tr>
   <td>criteria
   </td>
   <td>Optional
   </td>
   <td>The criteria for sorting the engagement ranking. All possible criteria are posts, comments, postTime, commentTime, endorsedComments. postTime and commentTime refer to the most recent time a post or comment was published. The default is posts.
   </td>
   <td>String
   </td>
  </tr>
  <tr>
   <td>limit
   </td>
   <td>Optional
   </td>
   <td>The maximum number of posts returned by the route. The default is 1.
   </td>
   <td>Integer
   </td>
  </tr>
  <tr>
   <td>reversed
   </td>
   <td>Optional
   </td>
   <td>Whether the sorting order is ascending or descending. The default is false (descending).
   </td>
   <td>Boolean
   </td>
  </tr>
</table>

