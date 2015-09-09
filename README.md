# journal
A unix/linux command line utility that creates a new journal text file with today's date on your computer.

##Instructions to install:
Determine where you want to store your journal entries on your file system. Let's call this entiresDirectory.

1. Copy the slug.txt file into your entriesDirectory.
2. Add the following variable and alias to your `.bashrc` file
3. Replace /home/david/Documents/Journal in the following line with your entriesDirectory.
```
# Create current date variable.
_now=$(date +%Y_%m_%d)
# Copy slug.txt, rename it with today's date, and open it in vim in insert mode.
alias journal="cd /home/david/Documents/Journal; cp slug.txt $_now.txt; vim -c 'startinsert' $_now.txt"
```
That's it. Now, just restart your terminal. Type journal and hit return.

##Request for help
Please check out [issues](https://github.com/davidkneely/journal/issues) for ways you can help refine this script.
