# Entry 6
## 05/11/2025
## Context
In my previous blog, I discussed the tool I would use, `animation.css`, for my SEP10 Freedom Project. My SEP teacher told us that now that we have our content from parts A and B and our tool, we can make a prototype or bare minimum on how the website will look using our wireframe we made earlier.

## Challange
When starting this project, I was on a school trip, so timing was not on my side much, and many other errors needed polishing. For a quick background, `hovering` is also considered an animation when the background color of the button changes when the mouse is hovering over the button. The idea was to have it in the section of hardware section cards, but the only issue is that the bootstrap components do have buttons, but only a different code, such as this:

```
<p class="d-inline-flex gap-1">
 <a class="btn btn-primary" data-bs-toggle="collapse" href="#collapseExample" role="button" aria-expanded="false" aria-    controls="collapseExample">
    Link with href
  </a>
 <button class="btn btn-primary" type="button" data-bs-toggle="collapse" data-bs-target="#collapseExample" aria-expanded="false" aria-controls="collapseExample">
    Button with data-bs-target
  </button>
</p>
```
 
It was later on when I tried to use `animation` on the button class of `btn btn-primary`, which is just a button with a different usage, but only works with a normal button. So I started tinkering around to see if there is a way that the button to still work but be able to get highlighted by the color of my choice. In the bootstrap, there are two ways to have the button work, using a herf or another one using `role=button`. I started with tinkering with the herf by changing the class to button1 or just button, and once I did, I added the `@keyframes` in the `CSS` to see if it would highlight, but it didn't. And once I figured that a herf wasn't going to work, I tried the one with the button class, when I changed the button `btn-primary` to button, then made the following `@keyframes`:

```
 .button1 {
    border-radius: 5px;
    color: #D4B99E;
    background-color: #928997;
    padding: 5px 10px 8px 10px;
    margin-left:15px;
  }

  button:hover {
    animation-name: card1color;
    animation-duration: 500ms;
  }
  @keyframes card1color{
  100%{
  background-color:#826791;
  }

  }
```
It was able to work, but the only tiny little issue was that it wouldn't stay highlighted forever, but I just forgot to look at my notes and add the animation code:
`  animation-fill-mode:forwards;`


A reason why i added a number at the end of the button was because if all the buttons had the same class, then all the buttons with same class would go with all the buttons using the same class even if your not hovering over that own button.


Another issue I ran into was mainly how responsive the website was. For example, I would have two columns in a row, and one column would have an image, and the other one would have a border, and within the border was the text. But the issue was that everytime the window would shrink, the text within the border would overflow and go outside the border, making the words overlapping the following content below, one of the images would overlap the coloum beside it cause of its the size and the other images wouldn't because of their small size. With the image, At first i try to see if the width was an issue because of my prevoius website project, SHABAR, a similar issue and the code to help it was by making the width:100% but i didn't want that because it would make the image the same, so i decrease the percent to 50% but it wouldn't work or to small, So i thought maybe changing the coloum size to a `col-sm` it would do but nope, So finally i asked Mr.Muller and he was supposed to give me hints but he just gave me the answer by the accident, and it was the answer i forgot about, the code `img-fluid` which makes the image 100% width when the size is shrink or decrease, so it makes the image responsive. 

But the 2nd issue remained, so first I checked how much space is being taken within that column. The first idea that came up was adding `padding` by `5px` and around `10px` on the left so the `<li>` aren't on the side too much. And it's something, but it was still overflowing, but interesting enough, the first row was the only one overflowing and the other didn't, so i checked the CSS of it, and turns out, the height was set around `578px` because at that time i want the image and border to match up but after adding the image fluid the size changed so i never got to change the container with the content size, and once i removed it, i added `height:100%` to make it responsive and then it stop overflowing. Also, when searching up what happened, just in case it didn't work, there was a code that was called `break-word` which just changes when the line of content is shrunk or increased, and it wasn't necessary since I found out the issue but its something to keep in mind next time.

## Takeaways
A takeaway I can take is worrying about the little stuff later and the essential things now, and it sounds cliche but sometimes when i asked some questions to Mr.Muller it would be tiny teeny details that you wouldn't notice if you were the view, and i feel like that made my work a bit more time consuming espically with being away for a bit. 


[Previous](entry05.md) | [Next](entry07.md)

[Home](../README.md)
