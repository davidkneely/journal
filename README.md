# journal
A unix/linux command line utility that creates a new journal text file with today's date on your computer.

##Instructions before using:
This code makes a call to my quote script that pulls a random quote from a list of quotes. The quote is prepended to the journal entry.

##Instructions to install:
Determine where you want to store your journal entries on your file system. Let's call this entiresDirectory.

1. Copy the slug.txt file into your entriesDirectory.
2. Add the following variable and alias to your `.bashrc` file
3. Replace `/home/david/Documents/Journal` in the following line with your entriesDirectory.
4. If you prefer to use an editor other than `vim` change the `EDITOR` variable to your editor of choice in the code below.

```
# Journal
function journal {
  EDITOR=${EDITOR:-"vim -c startinsert"}
  JOURNAL_DIR=/home/david/Documents/Journal
  _now=$(date +%Y_%m_%d)
  if [ -f ${JOURNAL_DIR}/${_now}.txt ]; then
    $EDITOR  ${JOURNAL_DIR}/${_now}.txt
  else
    cp ${JOURNAL_DIR}/{slug,$_now}.txt
    $EDITOR -c 'startinsert' ${JOURNAL_DIR}/${_now}.txt
  fi
}

function journal {
   EDITOR=${EDITOR:-"vim -c startinsert"}
   JOURNAL_DIR=/Users/davidneely/Documents/
   _now=$(date +%Y_%m_%d)
   if [ -f ${JOURNAL_DIR}/${_now}.txt ]; then
     $EDITOR  ${JOURNAL_DIR}/${_now}.txt
   else
     cp ${JOURNAL_DIR}/{slug,$_now}.txt
     quote | cat - ${JOURNAL_DIR}/${_now}.txt > temp && mv temp ${JOURNAL_DIR}/${_now}.txt
     $EDITOR -c 'startinsert' ${JOURNAL_DIR}/${_now}.txt
   fi
 }
```

That's it. Now, just restart your terminal. Type journal and hit return.

##Request for help
Please check out [issues](https://github.com/davidkneely/journal/issues) for ways you can help refine this script.
