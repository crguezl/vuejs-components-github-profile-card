# Lab: GitHub Profile Card

## TODO 

### VueSchool Course Vue.js Components Fundamentals

See the result working in the [GitHub Page of this repo](https://crguezl.github.io/vuejs-components-github-profile-card/index.html)

For this lab you have to watch the video [Build a GitHub user profile component](https://vueschool.io/lessons/build-a-github-user-profile-component) and solve the exercise.

It is convenient to study  these labs first:

* The lab [Vue.js Fundamentals at crguezl/vuejs-fundamentals](https://github.com/crguezl/vuejs-fundamentals#readme)
* The lab [Vue Components Basics at crguezl/vuejs-components-basics-plan-picker-component](https://github.com/crguezl/vuejs-components-basics-plan-picker-component)
* Watch the videos at the [Vue.js Components Fundamentals](https://vueschool.io/courses/vuejs-components-fundamentals) course.

You can check the branch [solution](https://github.com/crguezl/vuejs-components-github-profile-card/tree/solution) if you have doubts

### Writing the Component github-user-card 

* [ ] Create the `index.html` with HTML initial template (Emmet !)
* [ ] Add CDNs for [Semantic UI](#semantic-ui), [Vue](https://es.vuejs.org/v2/guide/installation.html#CDN) and [Axios](#axios)
* [ ] Add the Code of the Semantic UI [Card](#card)
* [ ] Create the Vue app object and link it with the `div` element with `id` `app`
* [ ] Add the call to the component 

  ```html
  <github-user-card username="githubuserlogin"></github-user-card>
  ```
* [ ] Add a template with the id `github-user-card-template` for the component with the HTMl of Semantic UI [Card](#card)
* [ ] Add the code to create the `github-user-card` component specifying the template
* [ ] Add the property `username` and a `user` data to the component
* [ ] Add a [hook](https://crguezl.github.io/learning-vue-geting-started-guide/#instance-lifecycle-hooks) `created` to the component. Inside this [hook](https://crguezl.github.io/learning-vue-geting-started-guide/#instance-lifecycle-hooks) we are going to make the [axios](#axios) call to the [GitHub REST API for the user info](https://docs.github.com/en/rest/reference/users#get-a-user)
* [ ] Using the Vue dev tools check that the request is working and the `user` data has the expected contents
* [ ] Using GitHub REST API [you can get the user info]((https://docs.github.com/en/rest/reference/users#get-a-user)) from <https://api.github.com/users/crguezl>. Here are some of the fields that can be relevant for the `github-user-card` component:

  ```json
  {
    "login": "crguezl",
    "avatar_url": "https://avatars.githubusercontent.com/u/1142554?v=4",
    "gravatar_id": "",
    "url": "https://api.github.com/users/crguezl",
    "html_url": "https://github.com/crguezl",
    "name": "Casiano Rodriguez-Leon",
    "company": "Universidad de La Laguna @tic-ull",
    "blog": "https://crguezl.github.io/",
    "location": "La Laguna. Tenerife",
    "bio": "My Control Version Bio: Started with Unix RCS, then moved to  CVS, then Subversion and finally git ",
    "public_repos": 338,
    "followers": 196,
    "following": 246,
    "created_at": "2011-10-21T07:00:05Z",
    "updated_at": "2022-01-06T13:49:40Z"
    }
  ```
* [ ] Add the relevant information to the template. Use a computed property `githubYear` so that appears only the year in which the user joined GitHub

  ```js
        computed: {
          githubYear() {
            ...
          }
      },
  ```
* [ ] Put all the `github-user-card` components inside a `div` with classes `ui` and `cards` to have them in the same line. See <https://semantic-ui.com/views/card.html#cardsq>

## Semantic UI

### CDN providers

We can search for a lib in [cdnjs.com](https://cdnjs.com/libraries/redux-search). If we click in the lib, it appears the list 
of links to the files composing the lib. There we can search for `semantic-ui`.

See also:

* [cdnjs.cloudfare](https://cdnjs.cloudflare.com/)

### Card

* [Views/Card](https://semantic-ui.com/views/card.html)
  
```html
<div class="ui card">
  <div class="image">
    <img src="/images/avatar2/large/kristy.png">
  </div>
  <div class="content">
    <a class="header">Kristy</a>
    <div class="meta">
      <span class="date">Joined in 2013</span>
    </div>
    <div class="description">
      Kristy is an art director living in New York.
    </div>
  </div>
  <div class="extra content">
    <a>
      <i class="user icon"></i>
      22 Friends
    </a>
  </div>
</div>
```

### Cards

A group of cards.

```html
 35 Friends

Elyse
Coworker
Elyse is a copywriter working in New York.
Joined in 2014 151 Friends
<div class="ui link cards">
  <div class="card">
    <div class="image">
      <img src="/images/avatar2/large/matthew.png">
    </div>
    <div class="content">
      <div class="header">Matt Giampietro</div>
      <div class="meta">
        <a>Friends</a>
      </div>
      <div class="description">
        Matthew is an interior designer living in New York.
      </div>
    </div>
    <div class="extra content">
      <span class="right floated">
        Joined in 2013
      </span>
      <span>
        <i class="user icon"></i>
        75 Friends
      </span>
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img src="/images/avatar2/large/molly.png">
    </div>
    <div class="content">
      <div class="header">Molly</div>
      <div class="meta">
        <span class="date">Coworker</span>
      </div>
      <div class="description">
        Molly is a personal assistant living in Paris.
      </div>
    </div>
    <div class="extra content">
      <span class="right floated">
        Joined in 2011
      </span>
      <span>
        <i class="user icon"></i>
        35 Friends
      </span>
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img src="/images/avatar2/large/elyse.png">
    </div>
    <div class="content">
      <div class="header">Elyse</div>
      <div class="meta">
        <a>Coworker</a>
      </div>
      <div class="description">
        Elyse is a copywriter working in New York.
      </div>
    </div>
    <div class="extra content">
      <span class="right floated">
        Joined in 2014
      </span>
      <span>
        <i class="user icon"></i>
        151 Friends
      </span>
    </div>
  </div>
</div>
```

## Axios

* [Axios Intro](https://axios-http.com/docs/intro)
* [Axios en GitHub](https://github.com/axios/axios)
* [https://unpkg.com/axios](https://unpkg.com/axios)


### Performing a GET request

Want to use async/await? Add the `async` keyword to your outer function/method.

```js
async function getUser() {
  try {
    const response = await axios.get('/user?ID=12345');
    console.log(response);
  } catch (error) {
    console.error(error);
  }
}
```

Or using promises methods:

```js 
const axios = require('axios');

// Make a request for a user with a given ID
axios.get('/user?ID=12345')
  .then(function (response) {
    // handle success
    console.log(response);
  })
  .catch(function (error) {
    // handle error
    console.log(error);
  })
  .then(function () {
    // always executed
  });
```

Optionally the request above could also be done as

```js
axios.get('/user', {
    params: {
      ID: 12345
    }
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  })
  .then(function () {
    // always executed
  });  
```

## Vue Instance Lifecycle hooks 

* See [Instance Lifecycle Hooks](https://crguezl.github.io/learning-vue-geting-started-guide/#instance-lifecycle-hooks) in the teacher [Annotated Reading of the Essentials Section of the Vue.js Guide](https://crguezl.github.io/ learning-vue-geting-started-guide/#annotated-reading-of-the-essentials-section-of-the-vue.js-guide)
  * and the example [Answering your Question with the yesno.wtf API
](https://crguezl.github.io/learning-vue-geting-started-guide/#answering-your-question-with-the-yesno.wtf-api)
* See [Instance Lifecycle Hooks](https://vuejs.org/v2/guide/instance.html#Instance-Lifecycle-Hooks) in the docs


Each Vue instance goes through a series of initialization steps when it’s created - for example, it needs 

* to set up data observation, 
* compile the template, 
* mount the instance to the DOM, and 
* update the DOM when data changes. 
  
Along the way, it also runs functions called *lifecycle hooks*, 
giving users the opportunity to add their own code at specific stages.

For example, the `created` hook can be used to run code after an instance is created and it is a time when can safely do asynchronous network operations

## See Also

* The lab [Vue.js Fundamentals at crguezl/vuejs-fundamentals](https://github.com/crguezl/vuejs-fundamentals#readme)
* The lab [Vue Components Basics at crguezl/vuejs-components-basics-plan-picker-component](https://github.com/crguezl/vuejs-components-basics-plan-picker-component)
