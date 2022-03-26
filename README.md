# recordCollection

This is to record my process of solving the record collection challenege on FreeCodeCamp. To solve this I used the VS Code rather than the built-in browser provided. 

## Initial thoughts: 

4 conditional statements provided by freeCodeCamp, this will require focusing on the array sections of JS and if statements. My plan is to create if-else statements for the 4 conditions indiviudally and then decide on the best course of action to collate them into one updateFunction (). 
<hr> 

## Rule 1 - If prop isn't tracks and value isn't an empty string, update or set that album's prop to value -- Done!

For this rule the below code is created, by following The Odin Proejcts problem solving instructions I am breaking down the rules int othe simplest of functions then will configure the best way to add them together.

        if (prop !== tracks && value !== "") {
            if (recordCollection.id.hasOwnProperty(prop)){
                recordCollection.id.prop = value;
            }  else recordCollection.id.prop = value;
         } else null;

The idea behind this is, if the value is not equal "tracks" and is not an empty string, then the code shall be updated or included. FCC has taught me that updating code, and inputting code (key Value Paris) are the same. 

EDIT: I now realised that the above is null and void, as if the CD doesn't have the proeprty, one will be created, thus negating the need to check if one exists in the first place. Reviewed code below. 

        if (prop !== "tracks" && value !== "") {
            recordCollection[id][prop] = value;
          } else return "false"
          }
