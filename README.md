## What is it?

It's a part of the interview process for the Berlin blockchain startup for the role of Senior Software Engineer (Feb 2019). With this test task, I passed the interview.

## To run app locally:

### In client:
* yarn install
* yarn start

### In server:
* yarn install
* yarn server

open in http://localhost:8080/

## How to test:

  App has 4 tabs: Bitcoin, Litecoin, Ethereum, and Results. On tabs Bitcoin, Litecoin, Ethereum you will find a bar chart and card with contribution information. On bar click information on the card will be updated. On the Results tab, you will find a header with the total amount for each cryptocurrency and slider. Also, the Results tab contains all contributions cards and it is possible to filter by the slider.

## Technical thoughts:

 I made feature folders structure for the frontend. In case we want to add a new feature we just doing a new folder with this feature and adding our own containers, components, actions, reducers, and sagas in this folder. In the common folder, we store tools that can be shared between features. To reduce redux boilerplate I am using redux-actions. To work with side effects I’m using redux-saga because it is easy to test and it works well with complex side effects. For building UI is used styled-components lib (I feel ok with CSS in js). For charts is used chart.js because, in my opinion, it's easy to use it's configurable.

 For backend is used express as a framework because it is easy to use and well known.

## UI/UX:

 Content of the app is written by containers and on every tab click, we do request to update values. To reduce repeated containers code I made a container builder.

## CI:

 For CI I’m using Travis. I check the test coverage and in case it’s ok Travis builds docker images and after it makes deployment to AWS Elastic Beanstalk. To check tests is used docker spec file. It is easy to add pipelines for Eslint if it's needed.

## Dockerize and Deployment:

 I have docker files for the client, for the server, and for Nginx. I dockerized all this to make deployment to AWS Elastic Beanstalk easier.

## Testing:

  For testing, I’m using jest + 3rd party libraries for rendering and for testing redux-saga. Also, I’m using snapshot testing.


