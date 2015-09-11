# journal
A unix/linux command line utility that creates a new journal text file with today's date on your computer.

##Instructions to install:
Determine where you want to store your journal entries on your file system. Let's call this entiresDirectory.

1. Copy the slug.txt file into your entriesDirectory.
2. Add the following variable and alias to your `.bashrc` file
3. Replace `/home/david/Documents/Journal` in the following line with your entriesDirectory.
```
# Journal
function journal {
  JOURNAL_DIR=/home/david/Documents/Journal
  _now=$(date +%Y_%m_%d)
  if [ -f ${JOURNAL_DIR}/${_now}.txt ]; then 
    vim ${JOURNAL_DIR}/${_now}.txt
  else
    cp ${JOURNAL_DIR}/{slug,$_now}.txt
    vim -c 'startinsert' ${JOURNAL_DIR}/${_now}.txt
  fi
}
```
That's it. Now, just restart your terminal. Type journal and hit return.

##Request for help
Please check out [issues](https://github.com/davidkneely/journal/issues) for ways you can help refine this script.
