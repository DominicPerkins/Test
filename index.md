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
