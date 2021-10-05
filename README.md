# DataMax

## Installing Vue CLI and Axios
I started this project by installing the development server (Vue CLI). After Installing Vue CLI, I installed Axios from my Git Bash so as to use it to fetch data from the API I was given by DataMax. 

## Fetching the data from API
After the successful installation of the Axios package, I created a component named "BooksList". 
In this component, the API given to me was fetched using Axios. I did this by using a method I named "getUser".
This method fetches the data from the API but if the data is not fetched succesfully probably due to technical errors or poor connection, 
an error is rendered to the screen which states "Failed to fetch data, try again later". I then mounted the method used to fetch data from the API.  

## Rendering the data
After succesfully fetching the data, the next step I took was to render the fetched data on DOM. I did this by using v-for to loop through the data in "users" and I used a Bootstrap table 
to render the  looped data. The header of each coulumn was placed in an html element called table head and various names, ISBN, Authors, country, number of pages, were placed in  an table data 

## Filtering the data

The first step I took was to create a form component where the user can enter the name of what neeede to be serached. I then used v-model.trim to get the input the user entered and remove excess spaces that the user might have entered.
After collecting the input, the next step was to filter the "users" based on the input. I did this by using the computed property I named "filteredUsers". This filteredUsers computed property returns new "users" looping through each "user" 
and returns a user where the user.name matches the input that was searched for. I also ensured that if the data you are searching for is not available, "No result found" is rendered on the DOM


## Footer

I created a component named "the-footer" to show the pages of entries and I worked on the CSS to replicate the design that was sent by DataMax. I did this by using a dynamic class "active" that changes upon the button that is clicked

## Other features I ensured

 I ensured the responsiveness of the page by using CSS flex  and Bootstrap. I also added a loading html tag so the user is aware when the data is being fetched from the API.

 
 
