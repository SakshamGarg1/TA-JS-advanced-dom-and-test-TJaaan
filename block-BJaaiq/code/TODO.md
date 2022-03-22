## Quotes on scroll

- Create a infinite scroll quote page using the `scroll` type of event listener
- There is a file in this folder named `quotes.js` use it as a data source
- In the starting it will display only 3 quotes
-  As soon as you start scrolling it will keep adding new quotes at the bottom
- When you are displaying the quotes don't forget to add the author name also
- Using the lifecycle events like `DOMContentLoaded` display a alert message saying the `The content of the DOM is loaded`
- You can use the image given below for help to understand.


![](./terms.png)
let root = document.querySelector('ul');

let max =  6;
let index = 0;

function addQuotes(){
    for(let i = 0; i< max; i++){
        let li = document.createElement("li")
        let blockquote = document.createElement("blockquote")
        let cite = document.createElement("cite")
         blockquote.innerHTML = quotes[index].quoteText;
         cite.innerHTML = quotes[index].quoteAuthor;

         li.append(blockquote, cite)

         root.append(li);
         index++;
    }
}
addQuotes();

document.addEventListener('scroll', () => {
       let scrollTop = document.documentElement.scrollTop;
       let scrollHeight = document.documentElement.scrollHeight;
       let clientHeight = document.documentElement.clientHeight;
       
       if(scrollTop + clientHeight >= scrollHeight){
      addQuotes();
}

});



