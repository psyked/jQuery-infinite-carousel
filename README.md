jQuery-infinite-carousel
========================

A copy of [Stephane Roucheray's infinite carousel](https://code.google.com/p/jquery-infinite-carousel/), with some bugfixes.

Add an infinite carousel on your site, the easy way. See a [Demo here](http://sroucheray.org/blog/samples/jquery-infinite-carousel/)

###Features

- Really easy way to insert a quality HTML carousel on your site
- Loop infinitely over items when clicking next or previous button
- Avoid animation flickering due to multi-clicks on next and previous buttons

###Some HTML
  <div id="viewport">
  <ul>
          <li>1</li>
          <li>2</li>
          <li>3</li>
          <li>4</li>
          <li>5</li>
  </ul>
  </div>
  <a id="previous">Previous</a>
  <a id="next">Next</a>
  
  <!-- 
  ul/li structure can be replaced by any other html structure as div/div, div/span... 
  -->

### Some CSS
  /* Comments on styles purpose in the source code */
  #viewport{
          width: 240px;
          overflow:hidden;
  }
  #viewport ul{
          position: relative;
          padding: 0;
  }
  #viewport li{
          width: 100px;
          height: 50px;
          float: left;
          list-style: none;
  }

### Some JavaScript : the magic
  $('#viewport').carousel('#previous', '#next');

### Tips
If you need to activate auto-scrolling on your carousel, simply simulate a click :

  //The auto-scrolling function
  function slide(){
    $('#simpleNext').click();
  }
  //Launch the scroll every 2 seconds
  var intervalId = window.setInterval(slide, 2000);
  
  //On user click deactivate auto-scrolling
  $('#previous, #simpleNext').click(
   function(event){
    if(event.originalEvent){
     window.clearInterval(intervalId);
    }
   }
  );
