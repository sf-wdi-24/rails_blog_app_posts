# <img src="https://cloud.githubusercontent.com/assets/7833470/10899314/63829980-8188-11e5-8cdd-4ded5bcb6e36.png" height="60"> Rails Blog App Continued: User `has_many` Posts

**Objective:** Use Rails to build a full-stack blog application. You will be building this app over the course of three evenings.

**Your objective for this evening is to add a one-to-many relationship between `users` and `posts` and incorporate the Rails asset pipeline.**

## Getting Started

1. Make a new branch in your <a href="https://github.com/sf-wdi-24/rails_blog_app" target="_blank">rails_blog_app</a> called `posts`.
2. Implement the minimum requirements below.

## Minimum Requirements

* RESTful routes for the `posts` resource. Your app should have the following routes:
  * `GET /posts`
  * `GET /posts/new`
  * `POST /posts`
  * `GET /posts/:id`
  * `GET /posts/:id/edit`
  * `PUT /posts/:id` and/or `PATCH /posts/:id` (Rails `resources` generates both)
  * `DELETE /posts/:id`
* Controller actions for each of your RESTful routes that implement CRUD for `posts`.
* A `Post` model and corresponding database table with the minimum attributes `title` and `content`.
* A one-to-many relationship between `users` and `posts`.
* Model validations on `Post`:
  * `title`: presence, minimum 3 characters
  * `content`: presence, minimum 10 characters
* Error-handling in the `PostsController` that redirects the user if they submit invalid form data and shows a flash message with the error.
* Use the asset pipeline instead of CDNs to include Bootstrap in your application. You can either download the files or use the <a href="https://github.com/twbs/bootstrap-sass" target="_blank">bootstrap-sass</a> gem. See today's <a href="https://github.com/sf-wdi-24/modules/tree/master/week-07-rails-continued/day-03/module-02" target="_blank">Asset Pipeline</a> module for guidance. No need to precompile your assets in development :)

**If you get stuck at any point or need extra guidance, feel free to look at the <a href="https://github.com/sf-wdi-24/rails_blog_app/tree/solution-posts" target="_blank">solution-posts branch</a> or follow along with the <a href="https://www.railstutorial.org/book" target="_blank">*Ruby on Rails Tutorial* by Michael Hartl</a>.**

## Bonus

* Use a partial to DRY up the code in `app/views/posts/new.html.erb` and `app/views/posts/edit.html.erb`.
* *Authorize* your site by only letting users update and delete their own posts. **Hints:**
  * You'll need to check for the `current_user` in the view to determine whether or not to show the edit and delete buttons for individual posts. You'll also need to check for the `current_user` in any controller method you want to authorize.
  * If `current_user` is the same `@user` found by the `id` in the URL params, the user is authorized to update and delete.
* Move any CSS you wrote in `app/assets/stylesheets/application.css` to a `main.css` file (`main.scss` if you're using bootstrap-sass), and use the asset pipeline to include that file in your application. Again, no need to precompile assets in development.

## Super Bonus

* Implement commenting on your blog. A `comment` should belong to both a `user` and a `post`. Users should be able to:
  * Add a comment to any post, including their own.
  * View all comments related to a post on the `posts#show` page.
  * Only `update` and `delete` their own comments.

Refer to the <a href="https://github.com/sf-wdi-24/rails_blog_app/tree/solution_posts_comments" target="_blank">solution_posts_comments branch</a> for guidance.

## Submission

* As you make code changes, frequently commit and push to GitHub.
* Once you've finished the assignment and pushed your work to GitHub, make a pull request from **your `posts` branch** to the original repo.
