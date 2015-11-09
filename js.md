Handle email input field
------------------------
```javascript
$("#email-input").keyup(function(e) {
  var regex = /^\w+.*@\w+\.\w+$/;
  var valid = $("#email-input").val().match(regex);
  if (valid) {
    //If there is some icon you want to 'lit up' when typing starts, here's how you could do it
    $("#enter-icn").removeClass("dim");
    if (e.keyCode === 13) {
      //Enter
      var request = $.ajax({
        method: "POST",
        url: "http://your.site/handler",
        data: JSON.stringify({email: $("#email-input").val()}),
        contentType: "application/json; charset=UTF-8",
        dataType: "json"
      });

      request.done(function(msg){
        //Handle successful return from backend here
      });

      request.fail(function(msg, textStatus){
        //Handle unsuccessful return from backend here
        $("#err-msg").removeClass("hidden");
        $("#email-input").prop("disabled", false);
      });
      //To disable input while backend handles input, do this
      $("#email-input").prop("disabled", true);
    }
  } 
  else {
    $("#enter-icn").addClass("dim");
  }
});
```
