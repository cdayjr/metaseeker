## Meta Seeker ##
Meta Seeker is a simple bash script for pulling data from the *description* and *keywords* **meta tags** from a list of URLs. It also pulls the **title** tag too.

### Usage ###
You can enter either a URL or a file containing URLS (one per line, at the beginning of each line). If you enter a URL, it'll use link-checker to pull all the pages that URL links to and run on each of those URLs. If you give it a list, it'll just run on that list.

It outputs to standard output, but I recommend redirecting the output to a csv file.

#### Examples ####

##### With URL #####

    metaseeker http://www.example.com > example.com.csv
    
##### With List #####

    metaseeker urls.txt > urls.csv

### Limitations ###
I built this for checking out the meta tags on an outsourced website project, so it's made to work with the specific pages I worked with in mind. With that in mind, I figured it was useful enough to publish so others could make use of it if they find use in it and also so I could find it again if I needed it.

It makes the following assumptions:

 - **title** opening and closing tags are on one line
 - **meta** tags are also limited to one line, one tag per line

Many sites out there don't follow those conventions, and if you use this with those kinds of sites, weird stuff will happen! There's probably a fancier way to parse those tags but for my purposes it was unnecessary.

### Dependencies ###
Makes use of [Link Checker][1], Bash, and the GNU CoreUtils. Don't think it uses anything other than that.


  [1]: http://wummel.github.io/linkchecker/
