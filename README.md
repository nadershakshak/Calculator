# Calculator
Project for GSG Code Academy
<!DOCTYPE html>
<html>
<head>
 <title>Calculator</title>

<link rel="stylesheet" href="index.css">
<link rel="preconnect" href="https://fonts.gstatic.com">
<link href="https://fonts.googleapis.com/css2?family=RocknRoll+One&display=swap" rel="stylesheet">
</head>
<body>
 <div class="main">
  <form name="form">
   <input type="text" name="textview" class="textview">
  </form>

  <div class="clearfix">
   <div class="col-3"><input type="button" value="C" class="button top-button2" onclick="clean();"></div>
   <div class="col-3"><input type="button" value="&#8756;" class="button top-button"></div>
   <div class="col-3"><input type="button" value="Del" class="button top-button1" onclick="back();"></div>
   <div class="col-3"><input type="button" value="&#247;" class="button operator" onclick="insert('/')"></div>
  </div>

  <div class="clearfix">
   <div class="col-3"><input type="button" value="7" class="button" onclick="insert(7);"></div>
   <div class="col-3"><input type="button" value="8" class="button" onclick="insert(8);"></div>
   <div class="col-3"><input type="button" value="9" class="button" onclick="insert(9);"></div>
   <div class="col-3"><input type="button" value="&#215;" class="button operator" onclick="insert('*');"></div>
  </div>

  <div class="clearfix">
   <div class="col-3"><input type="button" value="4" class="button" onclick="insert(4);"></div>
   <div class="col-3"><input type="button" value="5" class="button" onclick="insert(5);"></div>
   <div class="col-3"><input type="button" value="6" class="button" onclick="insert(6);"></div>
   <div class="col-3"><input type="button" value="&#8722;" class="button operator" onclick="insert('-');"></div>
  </div>

  <div class="clearfix">
   <div class="col-3"><input type="button" value="1" class="button" onclick="insert(1);"></div>
   <div class="col-3"><input type="button" value="2" class="button" onclick="insert(2);"></div>
   <div class="col-3"><input type="button" value="3" class="button" onclick="insert(3);"></div>
   <div class="col-3"><input type="button" value="&#43;" class="button operator" onclick="insert('+');"></div>
  </div>

  <div class="clearfix">
   <div class="col-3"><input type="button" value="." class="button" onclick="insert('.');"></div>
   <div class="col-3"><input type="button" value="0" class="button" onclick="insert(0);"></div>
   <div class="col-6"><input type="button" value="&#61;" class="button equal" onclick="equal();"></div>
  </div>
  
 </div>

 <!-- Javascript Functions -->
 <script>
  function insert(num){
   var myString = document.form.textview.value;
   var lastChar = myString[myString.length - 1];
   if (myString.length < 30) {
    if (!isNaN(lastChar) || lastChar == null || !isNaN(num)) {
     document.form.textview.value = myString + num;
    }else if(num != lastChar){
     document.form.textview.value = myString.replace(lastChar, num);
    }
   }
  }
  function equal(){
   var sum = document.form.textview.value;
   if (sum) {
    document.form.textview.value = eval(sum);
   }
  }
  function clean(){
   document.form.textview.value = '';
  }
  function back(){
   var exp = document.form.textview.value;
   document.form.textview.value = exp.substring(0,exp.length - 1);
  }
 </script>

</body>
</html>
