### *Dominic Perkins - Statistics 220 - Assignment 1*
## **Code for my meme**
```
library(magick)

# square one
nerd <- image_read("http://calculatedbravery.files.wordpress.com/2014/01/nerd.jpg") %>%
  image_scale(500)

# square 2
nerd_text <- image_blank(width = 500, height = 500, color = "#000000") %>%
  image_annotate(text = "Working diligently to \nkeep on top \nof lectures \nand assignments" , color = "#F13810" , size = 50, font = "Impact" , gravity = "center")

# square three
gigachad <- image_read("https://pbs.twimg.com/profile_images/1433507587241259016/tp_977hd_400x400.jpg") %>%
  image_scale(500)

# square four - Different font size used to fit in box
chad_text <- image_blank(width = 500, height = 500, color = "#000000") %>%
  image_annotate(text = "Getting caught \nin the vicious \ncyle of procrastination" , color = "#F13810" , size = 48 , font = "Impact" , gravity = "center")

#square five 
omegachad <- image_read("https://i1.sndcdn.com/avatars-xfkhlKFALUQbGh2J-uFQ1sQ-t500x500.jpg") %>%
  image_scale(500)

#square six
Omegachad_text <- image_blank(width = 500, height = 500, color = "#000000") %>%
  image_annotate(text = "Doing absolutely \nnothing and failing \nthe year" , color = "#F13810" , size = 48 , font ="Impact" , gravity = "center")

#Bringing it all together (testing both methods)
nerd_vector <- c(nerd, nerd_text)
top_row <- image_append(nerd_vector)
middle_row <- image_append(c(gigachad, chad_text))
bottom_row <- image_append(c(omegachad, Omegachad_text))

Meme <- c(top_row, middle_row, bottom_row) %>%
  image_append(stack = TRUE) %>%
  image_scale(800)

Meme

image_write(Meme, "Stats_meme_new.png")
```
## **Code for my gif**
```
#Background image
Bubble_image <- image_read("https://www.freepnglogos.com/uploads/bubbles/transparent-bubble-clip-art-creation-creatures-4.png") %>% image_scale(500)

#first frame - "It's fun to stay at the..."
frame1 <- Bubble_image %>%
  image_annotate(text = "It's fun to \nstay at the...", color = "#000000", size = 75, gravity = "center") %>%
  image_scale(100) %>%
  image_extent("500x500")

#second frame - "Y"
frame2 <- Bubble_image %>%
  image_annotate(text = "Y", color = "#000000", size = 300, gravity = "center") %>%
  image_scale(200) %>%
  image_extent("500x500")
  
#Third frame - "M"
frame3 <- Bubble_image %>% 
  image_annotate(text = "M", color = "#000000", size = 300, gravity = "center") %>%
  image_scale(300) %>%
  image_extent("500x500")

#Fourth frame - "C"
frame4 <- Bubble_image %>%
  image_annotate(text = "C", color = "#000000", size = 300, gravity = "center") %>%
  image_scale(400) %>%
  image_extent("500x500")
  
#Fith frame - "A"
frame5 <- Bubble_image %>%
  image_annotate(text = "A", color = "#000000", size = 300, gravity = "center") %>%
  image_scale(500) %>%
  image_extent("500x500")

#Village people image
frame6 <- image_read("https://ichef.bbci.co.uk/news/976/cpsprodpb/48EF/production/_106217681_village_people_getty.jpg") %>% image_scale(500)

#Using vector for gif creation
frames <- c(frame1, frame2, frame3, frame4, frame5, frame6)

#Pulling it all together
image_morph(frames) %>%
image_animate(fps = 100)
```
This meme that I have created is an ironic meme comparing three different styles of learning, all of which become largely apparent during online school. The top panel suggests that people who actively stay on-top of their lectures and assignments are nerds (not me). The middle panel suggests that those who get overwhelmed and end up procrastinating heavily are [gigachads](https://knowyourmeme.com/memes/gigachad) (me) and the bottom panels suggest that those who just give up entirely are on a complete other level. It was heavily inspired by the ["Average Fan vs. Average Enjoyer"](https://knowyourmeme.com/memes/average-fan-vs-average-enjoyer) format. 


Learning reflection

Something I am very curious about learning with data technologies is the origin of it all. I want to understand what created the code that I am typing this message on, and what created that code and so on and so forth until I get to the origin which I suspect might be binary? Even then I would like to understand what coding allows a computer to read that. In the end I guess I want to see what the origin of code is.

# **A few extra laughs for ya troubles**
### How it feels when multiple errors come up in your R code
![](https://c.tenor.com/-wrmUJrUbeoAAAAC/emoji-disintergrating.gif)

### How it feels when it finally comes together
![BBL Drake](https://i.pinimg.com/474x/6a/fd/4a/6afd4af06854321192e957e895adad0f.jpg)
