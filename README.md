# BBC Count Me Up

## Feature: Counting Votes:
"As a BBC television presenter I want to see the counts for candidates within a given time frame. So that I can announce the winner of the competition"

## Acceptance Criteria:
- Count Me Up should be accurate. So if there is a total count of 100 votes and 60% are given to candidate-1 then Count Me Up should return 60 as the count of votes for candidate-1.
- The same user can vote multiple times, up to a maximum of 3 times for the same candidate or for different ones. Count Me Up should not count a vote if the same user already exceeded the maximum allowed number of votes (that is should not count user-1 vote for candidate-5 if user-1 already voted for candidate-1, candidate-2 and candidate-3). This is the reason why candidate-5 for example received "only" 3M votes instead of 4M.
- Count Me Up should be fast. Count Me Up will be used as a close to real-time tool to constantly show the results of the competition, so it should be invoked every second or so to show progress. It follows that it should respond in less than 1 second.

## Data
All data is stored locally with ember pouch, however it can easily link and sync to a noSQL database such as CouchDB. 

To generate 5 random candidates, select the "Populate with 5 candidates" link in the bottom left of the application. To start from scratch and clear all data, click the "Reset Application (Clears all data)" link in the top right under the login/logout button. These links are not shown in the screenshots below.

## Screenshots

### Displays winner in given time frame
![Screenshot 1](http://www.giovannilenguito.co.uk/countMeUpScreenShots/8.png)
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2FGiovanniL19%2Fbbc_count_me_up.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2FGiovanniL19%2Fbbc_count_me_up?ref=badge_shield)

### Displays all time winner (no time frame set)
![Screenshot 2](http://www.giovannilenguito.co.uk/countMeUpScreenShots/4.png)

### Adding a new candidate
![Screenshot 3](http://www.giovannilenguito.co.uk/countMeUpScreenShots/7.png)

### Logged in user with the ability to vote
![Screenshot 4](http://www.giovannilenguito.co.uk/countMeUpScreenShots/6.png)

## Prerequisites
You will need the following things properly installed on your computer:
* [Git](http://git-scm.com/)
* [Node.js](http://nodejs.org/) (with NPM)
* [Bower](http://bower.io/)
* [Ember CLI](http://ember-cli.com/)
* [PhantomJS](http://phantomjs.org/)

## Installation
In terminal type the following:
* `git clone <repository-url>` this repository
* `cd count-me-up`
* `npm install`
* `bower install`

## Running / Development
To run the application, type the following in the terminal in the project directory:
* `ember serve`

In your browser:
* Visit your app at [http://localhost:4200](http://localhost:4200).

### Code Generators

Make use of the many generators for code, try `ember help generate` for more details

### Running Tests

* `ember test`
* `ember test --server`

### Building

* `ember build` (development)
* `ember build --environment production` (production)


## Further Reading / Useful Links

* [ember.js](http://emberjs.com/)
* [ember-cli](http://ember-cli.com/)
* Development Browser Extensions
  * [ember inspector for chrome](https://chrome.google.com/webstore/detail/ember-inspector/bmdblncegkenkacieihfhpjfppoconhi)
  * [ember inspector for firefox](https://addons.mozilla.org/en-US/firefox/addon/ember-inspector/)


## Errors That I Came Across
Some errors occurred with regards to making everything real time. However, these were solved with observers. As the user makes changes, the UI automatically updates, Ember JS makes this easy. There were also glitches where the percentages would display "Infinity" rather than a value, this occurred when a property was undefined or null. The fix was to check if the property exists, if it doesn't then return 0.

## Development Process
I start off with writing the requirements in bullet points on paper, I then designed the UI from these requirements showing where all these actions will be present. Once the design was complete I started developing the code. Once I finished development, I tested the code with Ember testing. Any complex logic involved, I would write down onto paper the steps needed to produce the expected result, this helped when coding the actual the logic.


## License
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2FGiovanniL19%2Fbbc_count_me_up.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2FGiovanniL19%2Fbbc_count_me_up?ref=badge_large)