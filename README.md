        function alphaCount (alphabet, text) {
            //declare an object
            var results = {};
            //ABC -> abc
         var lowerCaseAlpha = alphabet.toLowerCase();    
            //["a","b","c"]
         var newAlpha = lowerCaseAlpha.split("");
            //abc -> abc
        var lowerCaseText = text.toLowerCase();
            //["a", "b", "c"]
        var newText = lowerCaseText.split("");
         //new array
         var arr = [];
         
         //filtering out newAlpha
         newAlpha.filter(function(item){
             //using forEach to check each elements in the text array
            newText.forEach(function(i){
                //if they match push it into the array
                if(item === i){
                    arr.push(i);
                }
            });
         });
         //if array length is greater than 1
         if(arr.length > 0){
             for(var i = 0; i < arr.length; i++){
                 //if the elements inside the array already exist
                 if(results[arr[i]]){
                     // add one to it
                     results[arr[i]]++;
                 } else {
                     // if it doesn't add 1
                     results[arr[i]] = 1;
                 }
             } 
             
         } else {
             //this will appear if no matches was found. 
             return "no matches";
         }
        //initilize a string
         var  resultString = "";
         //object loop
            for( var property in results){
                //get the property to string
                resultString += property;
                //add :
                resultString += ":";
                //get the value of the property to string and add ,
                resultString += results[property]  + ",";
            }
            //trim the last ,
          var newResultsString = resultString.slice(0, -1);
          return newResultsString;
        }
        
        alphaCount ("abc", "aabbccdd");
