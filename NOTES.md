Next:
  -Change the endchain response to false
  (NO MORE endAbility)

  -Handle errors if someone passes something that is not an array into the response list

  IMPROVE DESIGN:
    -Allow for the response list to carry just the names of the responses
    -Add Typing capability

  -Write the basic docs
  -Write the basic wiki
  -Make the generic bot template on sketch
  -Make a super quick page for the skeleton bot

  -add general error handlers
  - change file names for the normal-convention
  -add promises where async is needed
  -make a notes ability





Recap:
Object Oriented Programming:  <--- template with unique instance
object made by functions return
Functional Oriented programming: <--- template with individual process ( no unique instance for later use )
Template created and called every time the function runs

CONCLUSION:
FOP takes less memory & fits this situation. No need to save the memory on a reader - for now.
Reader evolution = fixed set of functions that will either changec completly or not be edited.


Just did:
  Created the basic structure for the bot framework to scale in mode negative abilities
    searches the msg for a command and triggers the appropriate ability for that command.
      It does this by reading the commands array of objects


      1-Make the bot.js script easier to read
        -change self to this
        -Change the name of the commands module to be the abiltity_index... ability nest
      -build the context package

Todo:

  2-Create support for mode heavy functions
    -ex: sender: make note
         bot: what would you like your note to say?
         { bot expects only note info }  
         sender: [note info]
         { bot shows note with "tap to edit mark"}
         bot: Saved
         bot: Done with notes?
         { show options: "done" || "new note" }
  3-Create the sign up/log in features
  4-Create a feature to make the bot useful in the most basic way possible
  5-Create the designs for that bot
  6-Code the backend:
      Bot to Firebase
  7-Code the front-end:
      React + Redux + React native




bin


/*

try{
  context.state.message === "";
} catch(error){ return console.log('message needs to be a string'); }

  function(context){
  try{
    var message = context.state.message,
          from = context.props.sender,
          list = context.state.responseList,
          response = false,
          length = list.length;
  } catch(error){
    console.log('error: ',error);
    console.log("the reader's context failed to provide the propper variables");
  };




  // MATCH COMMAND
  // go trough the available abilities
  for( var i=0; i<length; i++){
    var ability = list[i],
      commands = ability.commands;
    // go trough that abilitie's commands
    for( var index=0; index<commands.length; index++ ){
      // if the command matches, set it's response
      // and pass it the state and save it's returning context
      console.log( 'checking maches' );
      if ( message.match( commands[index] ) ){
          console.log( 'matched' );
          return response = ability.response(context);
      };
    }
  }
}


var triggerResponse = function(){
  // trigger the returned response function
  // from the matching response object
    return response(context);
};



var triggerResponse = function(response){
  // trigger the returned response function
  // from the matching response object
    return response(context);
};

// initialize the reader
var response = findResponse();
var newResponseList = triggerResponse(response);

return newResponseList;
// return the promise with the following responseList
//  resolve(newResponseList);
// reject and report any errors as a Reader Error
//  reject(Error("Reader Error"));


};
