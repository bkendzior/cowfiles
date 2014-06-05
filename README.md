##cowfiles
========

Additional ASCII cowfiles for cowsay

More information:
http://en.wikipedia.org/wiki/Cowsay

###cowsayfortune
========

If you have [fortune](http://en.wikipedia.org/wiki/Fortune_(Unix)) installed, here is a simple bash function that you can place in your .bashrc that will give you a useful quip from a funky cow.

``` bash
# Fortunes every time you open a terminal!
function cowsayfortune {
  NUMOFCOWS=`cowsay -l | tail -n +2 | wc -w`
  WHICHCOW=$((RANDOM%$NUMOFCOWS))
  THISCOW=`cowsay -l | tail -n +2 | sed -e 's/\ /\'$'\n/g' | sed $WHICHCOW'q;d'`

   #echo "Selected cow: ${THISCOW}, from ${WHICHCOW}"
   fortune | cowsay -f $THISCOW -W 100
}

cowsayfortune
```
