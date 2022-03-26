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

EDIT: I now realised that the above is null and void, as if the CD doesn't have the property, one will be created, thus negating the need to check if one exists in the first place. Reviewed code below. 

        if (prop !== "tracks" && value !== "") {
            recordCollection[id][prop] = value;
          } else return "false"
          }
<hr> 

## Rule 2 - If prop is tracks but the album doesn't have a tracks property, create an empty array and add value to it -- Done!

This rule confused me somewhat as it did not click with the syntax of how to use the hasOwnProperty along with the ID number. Also in this rule i had to research about creating a key value pair, that created na array, rather than a string attribute. This is done by specifying the input in square brackets. 

          if (prop == "tracks" && recordCollection[id].hasOwnProperty("tracks") != true ){
            recordCollection[id][prop] = [value];
         } else "null";
         
<hr>

## Rule 3 - If prop is tracks and value isn't an empty string, add value to the end of the album's existing tracks array.

This rule actually made alot of sense and was easiest to create after having completed the second rule. I tested this in code-pen with the given FCC arrays and allowed me to ensure the syntax was created correctly, and returned the correct result. I am still unsure as of yet, how how these rules will fit together but it shouldn't be too much of an issue. 

After testing the below code statement in Code-pen it seems to be good to go. This interprets the "prop" to ensure it is "tracks" and then if the value is not an empty string, it pushes (.push()) the value ont ot he end of the existing array. Point to note! if you use push([]), this will create a NEW array, remove the square brackets to ensure that it adds it onto the existing array. 

         if (prop == "tracks" && recordCollection[id].hasOwnProperty(prop) !== ""){
           recordCollection[id][prop].push(value);
         }

<hr>


## Rule 4 - If value is an empty string, delete the given prop property from the album.

For this I built upon rule 3 wit hthe below code statement. Again, tested on code-pen to ensure it works! 

         if (prop == "tracks" && recordCollection[id].hasOwnProperty(prop) !== ""){
           recordCollection[id][prop].push(value);
         } else if (prop == "tracks" && recordCollection[id].hasOwnProperty(prop) == ""){
           delete recordCollection[id][prop];
         }
         
<hr>

## Update 5 - Testing the code block. 

To begin i simply pasted each statement underneath eachother and ran it through FCC. One passed most failed, cool back to the drawing board, I tested each statement indiviudaly, until I realised a spelling error and i was using recordCollection vs records, I corrected this and ended up with a few more passes. 

Still could not identify the error so made the decision to look at the solution on FCC, to compare what i had got to, to the actual result. First is my final code after a few bug fixes, the second is the one i reached that passed. 


        if (prop !== "tracks" && value !== "") {
            recordCollection[id][prop] = value;
          } else if (prop == "tracks" && recordCollection[id].hasOwnProperty("tracks") === false ){
            recordCollection[id][prop] = [value];
         } else   if (prop == "tracks" && value !== ""){
           recordCollection[id][prop].push(value);
         } else if (prop == "tracks" && value == ""){
           delete recordCollection[id][prop];
         } retrun records;

<hr>

         
            if (prop !== 'tracks' && value !== "") {
              records[id][prop] = value;
            } else if (prop === "tracks" && records[id].hasOwnProperty("tracks") === false ){
              records[id][prop] = [value];
           } else if (prop === "tracks" && value !== ""){
            records[id][prop].push(value);
          } else if (value === ""){
            delete records[id][prop];
          }
          }
            return records;
          
         
<hr>

## Comparison - Where did i go wrong? 
