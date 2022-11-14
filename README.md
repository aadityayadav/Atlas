## How to use Atlas?
1) Go to "Try me" from the side navigation bar. The search box there, takes in an address. Clicking on the "Add" button adds it to a table. It also adds a marker onto the map below, created by the Maps Embed API. Add as many or as few addresses as you want, our algorithm doesn't have an upper limit to how many calculations it can do!

2) Once you're done inputting all the addresses, simply click on "Generate Centroid" and it's as simple as that! Your centroid will be generated, marked by the purple marker.

3) If you'd like a list of things to do around the location, click on "Generate Places" and it'll show you everything that you can do around the centroid within a default radius of 500m, marked with blue markers.

## API Used
**Geocoding**: Used to convert entered addresses to geocodes

**Maps Embed**: Used to display the map on the website

**Places**: Used for placing markers on the map and generate a list of social places surrounding the centroid

## How does the Algorithm work?
1) As the user input’s the addresses it gets appended into an array. These locations get converted into geocodes and get appended into another array with initialized weight of 1, resulting in the creation of a 3d array with latitude, longitude and weight. Real time conversion prevents us from placing multiple API calls at once and avoid reaching the browser limit for the total number of concurrent requests. Additionally it reduces latency by limiting the number of requests to the server during calculations of centroid or places.

2) When the ‘Generate Centroid’ button is called our software iterates over the 3d array of geocodes. It takes the first two points and finds the center (in respect to the weights). The first 2 points get popped from our array and the center is appended into out array with a weight assignment of weight of point one plus weight of point two. We continue this process till the time we have just 1 element left in our array. Which is the Centroid of the entire cluster of points. The total number of iterations is n-1, where n is the number of elements in our array.

3) When the ‘Generate Places’ button is called we first find the centroid if that has not been found. Then we use the places API to find relevant locations, surrounding the centroid, within a user inputted radius (default is 500).

## What inspired us
We wanted to build a software that was focused on connecting people. During Covid-19, a lot of us lost our ability to socialize, and as a result, we saw loads of people experiencing loneliness and depression. We wanted to fix that. In comes Atlas, a project that aims to do exactly that. We want people to go out and meet each other again, we want friends to reconnect, we want new connections to be made. We want to build a community. 

## What we learned
As a two member team, one of the members being a novice at hackathons and coding in general, and the other member being heavily experienced in hackathons, we learnt to work to each others strengths. Aaditya Y. picked up where Aditya S. was struggling, Aditya S. provided Aaditya Y. new perspectives on problems whenever he found himself at a stump. Both of us found that we contributed equally as much, and we created a healthy and supportive collaborating environment for both of us to thrive and work in. 

## The challenges we faced
As with the spirit of hackathons, we faced an immense time crunch, leaving it to the last second to do absolutely everything! We put immense stress upon ourselves, learnt how to develop a website from scratch, learnt how to work with APIs for the first time for Aditya S. We felt dejected and unsure about whether or not we could complete the project on time, but we kept persevering. We kept pushing each other because this was important for both of us. We are proud to have come up with such an idea, and be able to execute it.

## Going forward...
We wish to add more features to the Atlas website. We want to display even more use cases for this highly versatile algorithm. The only thing stopping us is our imagination! 
