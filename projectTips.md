1. Avoid creating a big container that will contain all the content on a page. For this project its fine, but for other projects it might be a problem. Changes will come in the future in certain parts of the container, and editing a container that holds to many sections of the page is going to be very hacky. Rule 1 container per section. 

2.   
.container { 
  --max-width: 1110px; /* From figma file*/
  --padding: 1rem;

  width: min(var(--max-width), 100%);
  margin-inline: auto;


}
The code above actually tells you the width of the container is the smallest number between 1110 or 100%. Meaning if the 100% screen width is larger than 1110px then we will take the 1110 screen width instead and vise versa. This is actually very good as the container is reactive screen width.

Margin-inline sets the margin to the right and left of the property. When you set it to auto, it make sure the margin is equal to the right and left of the container. 
Since we set the width of container to be max 1110, then when the screen hits a value higher than 1110 the margins are going to appear around the container, and both sides are going to be equal. 

2.1 If you look at the code above, container touches the sides of the screen when the view gets smaller, we want to add space to the next of the container from both sides. This is going to be maintained by the margin-inlines. The code is going to be like this now: 


.container { 
  --max-width: 1110px; /* From figma file*/
  --gap: 1rem;

  width: min(var(--max-width), 100% - var(--gap * 2));
  margin-inline: auto;


}