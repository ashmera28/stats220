# Hello Everyone!
Welcome to my Website!

## About Me
*I'm a third year uni student majoring in Information Technology and Management.* **I'm a foodie, I love sketching and travelling as well.**

## I also am fond of memes :)
Below is a meme that I made using R package in R studio [{magick}](https://cran.r-project.org/web/packages/magick/vignettes/intro.html).

![my_meme](https://user-images.githubusercontent.com/101610725/158328349-5f01a1a6-a636-418d-b99f-bf63708a372a.png)

A short summary of my inspiration for the meme is that I am an Army(BTS stan), I thought why not make a meme with BTS because I have watched
a lot of their videos and it's always hilarious. I found a picture that shows them basically being goofy and thought why not make it into a meme. 

Below attached is the R code I used to make the meme! Hope you guys like it!
comedian <- image_read("https://i.guim.co.uk/img/media/243076ac810cfe6320445c064c7823bee4bddaf0/0_9_1654_992/master/1654.jpg?width=1200&quality=85&auto=format&fit=max&s=9b03448172aaf9d993fcb2a45312b05d")%>%
  image_scale(500)

bangtan <- image_read("https://i.pinimg.com/originals/8c/55/74/8c5574dde1a68a68fca4060e7e0168f3.jpg")%>%
  image_scale(500)

comedian_text <- image_blank(width = 400, 
                          height = 450, 
                          color = "#000000") %>%
  image_annotate(text = "Why\nDo\nComedians\nExist\n???",
                 color = "#FFFFFF",
                 size = 70,
                 font = "Impact",
                 gravity = "center")

bangtan_text <- image_blank(width = 400, 
                          height = 375, 
                          color = "#000000") %>%
  image_annotate(text = "When\nWe\nHave\nBTS!!",
                 color = "#FFFFFF",
                 size = 70,
                 font = "Impact",
                 gravity = "center")

first_row <- c(comedian, comedian_text) %>%
  image_append()

second_row <- c(bangtan, bangtan_text) %>%
  image_append()

meme <- c(first_row, second_row) %>%
  image_append(stack = TRUE)

image_write(meme, "my_meme.png")


