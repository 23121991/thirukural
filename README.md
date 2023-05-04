<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>திருக்குறள்</title>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Thirukural</h1><br>
    <div class="container">
        <input id="kural" type="number" class="d-flex w-50 mx-auto" placeholder="Enter kural number">
        <button class="btn" type="button">Search</button><br>
            <div class="container-fluid">

            </div>
    
    </div>
   
    <script src="script.js"></script>
</body>
</html>









}async function kural(){
    var number = document.getElementById('kural').value
     var result = await fetch(`https://api-thirukkural.vercel.app/api?num=${number}`);
      var datas = await result.json()
      console.log(datas)
    var result=document.querySelector('.container-fluid')
    
      result.innerHTML=`
      <div class="section"><h2> ${datas.sect_tam}-${datas.chapgrp_tam}</h2></div>
      <div class="section"><h4>அதிகாரம்:${datas.chap_tam}🍁</h4></div><br>
      <div class="section"><h4> குறள்:</h4></div>
      <div class="section"><h5>${datas.line1}</h5></div>
      <div class="section"><h5>${datas.line2}</h5></div><br>
      <div class="section"><h4>பொருள்:</h4></div>
      <div class="section"><h5>${datas.tam_exp}<h5></div><br><hr>

      <div class="eng"><h2>${datas.sect_eng}-${datas.chapgrp_eng}</h2></div><br>
      <div class="eng"><h4>Chapter:${datas.chap_eng}🍁<h4></div><br>
      <div class="eng"><h4>Kural:</h4></div>
      <div class="eng"> <h5>${datas.eng}</h5></div><br>
      <div class="eng"><h4>Explanation:</h4></div>
      <div class="eng"><h5>${datas.eng_exp}</h5></div><br><hr>
     
      `
      
     }
  
  kural()
  
  var button = document.querySelector('.btn')
  button.addEventListener('click',kural)





#style.css

body{
    background-image:url(images1.jpg);
}
div{
    color: rgb(25, 16, 18);
    text-align: center;
}
h4{
    background-color: aliceblue;
}
h2{
    background-color: antiquewhite;
}
h5{
    background-color: yellow;
}
.btn{
    border-radius: 5px;
    background-image: linear-gradient(to left,rgb(224, 210, 14),rgb(4, 103, 146));  
    color: white;
    height: 30px;
}
#kural{
    background-image: linear-gradient(to left,rgb(83, 12, 59),rgb(33, 8, 117));  
    color: white;
}
h1{
    color: rgb(237, 233, 228);
    text-align: center;
}
