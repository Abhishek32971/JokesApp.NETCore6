# JokesApp
## Jokes App with ASP.NET MVC

This document outlines the architecture of a Jokes App built using ASP.NET MVC. Users can log in, upload jokes with answers, and search for jokes.

### Technologies Used

-   ASP.NET MVC (**Model-View-Controller**): Provides a structured approach for building web applications.
-   Entity Framework: used for data access and manipulation (database interactions).
-   Identity Framework :used for user authentication and authorization.

### Architecture

The application consists of the following core components:

-   **Models:** Represent data entities like users, jokes, and answers. These classes typically have properties that map to database columns (if using Entity Framework).
-   **Views:** Represent the user interface (UI) elements displayed in the browser. They consist of HTML templates with placeholders for dynamic content.
-   **Controllers:** Handle user requests, interact with models to retrieve or update data, and select the appropriate views to display. They often use data binding techniques to connect models and views seamlessly.

### User Stories

-   **User Login:** Users can register and log in to the application. (Requires Identity Framework)
-   **Joke Management:** Logged-in users can:
    -   Upload new jokes with answers.
    -   View a list of all jokes or search for jokes by keywords.

![Screenshot 2024-06-12 224636](https://github.com/Abhishek32971/JokesApp.NETCore6/assets/97088891/a965c852-56ea-4fea-946e-73ec1333d3f7)

### Data Model (Example)

**Models might include:**

-   `User` model: Stores user information like username, email, password (hashed).
-   `Joke` model: Stores joke details like title, content, and user ID (foreign key to User).
-   `Answer` model: Stores answer details like content and joke ID (foreign key to Joke).

### Example Controller Actions

-   `LoginController.cs`: Handles user login attempts and redirects to the appropriate view (e.g., dashboard after successful login).
-   `JokesController.cs`: Handles user requests for:
    -   Uploading new jokes (processes form data and saves to database).
    -   Displaying a list of all jokes or search results (retrieves data from database and passes to view).
![Screenshot 2024-06-12 224647](https://github.com/Abhishek32971/JokesApp.NETCore6/assets/97088891/f23826f3-1567-4acd-81a8-9044bca54d02)

### Example View (Simplified)

**Index.cshtml (Displays a list of jokes):**

HTML

```
<h1>Jokes</h1>
<ul>
  @foreach (var joke in Model.Jokes)
  {
    <li>
      <h3>@joke.Title</h3>
      <p>@joke.Content</p>
      <p>By: @joke.User.Username</p>
    </li>
  }
</ul>

```

Use code [with caution.](/faq#coding)

content_copy

This is a basic example. You would likely have separate views for login, joke creation, and potentially user profiles.
![Screenshot 2024-06-12 224751](https://github.com/Abhishek32971/JokesApp.NETCore6/assets/97088891/6547039c-ae04-4865-91eb-d239f153131b)


### Deployment 

The application can be deployed to a web server like IIS or Azure App Service to make it accessible online.

**Note:** This is a high-level overview of the architecture. The actual implementation details will depend on your specific requirements and chosen technologies.
