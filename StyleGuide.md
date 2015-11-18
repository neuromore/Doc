#Introduction

Explain what this chapter is about. This chapter is about how to extend the documentation. We will first walk through how to create a new markdown file and how to embed it into the documentation structure and then move on to a style guide for the markdowns.

#Creating a chapter

Create a new markdown file and name it after your indended documentation chapter. For example "GettingStarted.md" or "HowToCreateClassifiers.md". If the documentation chapter belongs to neuromore Studio, put it into the "neuromoreStudio" subfolder. Don't put a documentation markdown file into the GitHub root directory (other than this one).

After creating the markdown file, we need to embed it to the "Files.json" so that the online documentation knows there is a new file. Each time we access the documentation, this json file is parsed and the markdown files are added as chapters. Add a new json object to the "Files.json". The "name" is the visual name in the online documentation and "relative" is the relative filename starting at the GitHub root folder. After saving the "Files.json" it might take some minutes until your new chapter is actually visible in the documentation.

#Writing your chapter

Let us assume we want to write a "Getting Started" chapter for our neuromore Studio documentation section. In this case we create a markdown file called "GettingStarted.md" in the "neuromoreStudio" subfolder and adjust the "Files.json" accordingly. As the name of the chapter is already embedded into the "Files.json" as well as the filename, we don't put that into the markdown file as main headline anymore. Else we will see the same headline three times in the documentation.

#Writing your introduction

You can do a brief introduction section (#) about what this markdown file is. Always put one new line between a section and the text and afterwards again.

#Documentation continued

This is another section (#).

##Subsection on how to do headlines

Begin the very first word in headlines with a capital letter.

This is a subsection (##).

###Subsubsection and text blocks

This is a subsubsection (###). Only go to this hierarchy level. If you need further splitting up use lists like this:

- This is about group A
- This is about group B
- This is about group C

Always have an empty line before and after lists, like with the chapter names. Just always have an empty line before and after any text block, image, list etc.

This is a new text block where we want to embed an image. The image has to have a new line before and afterwards.

![Extract](neuromoreStudio/Images/Installation/01.png)

The image is located right to this text. So always put images before the text where it refers to. Use relative paths starting at the GitHub/Doc repository as root folder. For some of the markdown files this might mean first going up "../../" to the GitHub/Doc root folder before browsing down the hierarchy again. Here is an example of that: "../neuromoreStudio/Images/Installation/01.png". The file is located inside the "neuromoreStudio" folder, so we could skip this part "../neuromoreStudio/". It still needs to be done so that we can preview the files on the GitHub website while also our online documentation is able to locate the images.

Put all images into an "Images/XX/" subfolder. You can either name the subfolder after your documentation chapter (if the images are very specific for the chapter) or use a more generic subfolder name (in case the images could be reused for other chapters).

###This is another subsubchapter

And here comes some text blocks with some more words. This might be an introductary sentence for the following text blocks.

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed ultrices justo at quam dictum, id ultrices lorem dignissim. Phasellus at vulputate dui. Cras dapibus quis lorem quis rhoncus. Nam mi felis, bibendum a justo vel, venenatis posuere turpis. Vestibulum ut arcu eget mi vestibulum tincidunt id ut sem. Aenean efficitur ipsum sed felis interdum fringilla quis quis orci. Donec rutrum placerat dui quis scelerisque. Morbi ut faucibus erat. Maecenas ac quam laoreet, venenatis quam et, lobortis ligula. Integer dignissim nibh justo, at pretium quam pellentesque et. Nunc id sapien tincidunt, malesuada nibh a, porttitor tellus. Proin laoreet nibh eu quam tincidunt, eu dictum neque fermentum. Praesent dictum erat risus, eu elementum diam varius vitae. Donec elit ligula, pellentesque ac lacus nec, sollicitudin tincidunt dui. Vivamus nec lorem a enim consequat tincidunt.

Fusce nec felis euismod nulla finibus consequat. Cras imperdiet arcu a mi commodo, vel suscipit nisi dictum. Aliquam et tellus molestie, lobortis tellus ut, faucibus sem. Integer enim mi, placerat quis lorem tempor, aliquet interdum lacus. Nulla consectetur eu purus vitae pellentesque. Vivamus aliquet quam tortor, vitae finibus nibh faucibus non. Duis sit amet enim tellus. In consectetur lacus sem, vel ornare leo sagittis quis. Nunc eget auctor turpis. Vivamus ut nibh hendrerit, rutrum quam non, rutrum leo. Sed aliquet leo eu luctus dapibus. Vivamus augue ante, tincidunt a nisl a, aliquet tristique nisi. Maecenas aliquam fringilla risus sed semper. Integer metus nulla, aliquam at turpis sit amet, vulputate elementum mauris.

Sed congue commodo nisl ac facilisis. Etiam vehicula lectus eget dui faucibus efficitur. Nam a mi a mi congue faucibus ut ac dui. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Nulla vel convallis leo, nec vehicula tortor. Maecenas eget eros faucibus, pulvinar diam et, tristique tellus. Integer quis mi convallis, tincidunt tortor id, egestas mauris. Aliquam rutrum nunc ut ipsum efficitur, quis auctor purus volutpat. Nulla eget enim a eros facilisis rhoncus eu sed turpis. Nunc eleifend fermentum auctor. Mauris eleifend semper velit ac tempor. Fusce feugiat, dolor suscipit finibus faucibus, risus nisl maximus arcu, nec rutrum neque dui congue est. Ut dapibus, est nec porta venenatis, velit nisl malesuada turpis, et malesuada erat leo quis magna. Sed posuere elit in sapien vehicula, nec iaculis quam accumsan. Phasellus efficitur eros tincidunt, porttitor nisl eu, bibendum nisl.

Nulla egestas mattis lorem tempor mollis. Curabitur a lacus odio. Interdum et malesuada fames ac ante ipsum primis in faucibus. Vivamus quis dolor iaculis ex vulputate semper at ac purus. Maecenas tincidunt euismod magna eu dictum. Mauris augue neque, cursus ac auctor ac, bibendum a arcu. Phasellus ultrices mattis orci vitae viverra. Aliquam gravida ante non luctus dictum. Nullam sed interdum lectus.

Fusce tortor leo, tincidunt in nisi vel, hendrerit fringilla dolor. Nam vestibulum tortor at risus mollis, quis egestas tellus porta. Sed ut nisi sed nunc consectetur maximus a eget lectus. Maecenas luctus congue odio eget lacinia. Cras euismod lobortis nisi in tempus. Donec egestas ut diam id bibendum. Nullam elementum vehicula tempor. Sed eu lectus non magna ultricies suscipit ut eget quam. Donec faucibus lacus in libero efficitur venenatis. Sed vestibulum id tellus nec convallis. Mauris nec sodales metus. Cras nec lobortis dui. Suspendisse potenti. Mauris eu orci sagittis, viverra enim non, semper mi. Ut condimentum nulla ac nisi vulputate venenatis. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.