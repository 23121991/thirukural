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





#index.css

div{
    size: 40px;
    text-align:center;
background-color: rgb(142, 234, 142);

}
button{
    background-color: rgb(62, 216, 227);
    color: brown;
    padding-left: 2px;

    
}
h4{

    font-size: 60px;
    font-weight: 100;
    color: rgba(24, 63, 69, 0.427);
    font-style: italic;
    font-feature-settings: "c2pc";
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    background-color: rgb(246, 155, 58);
}



div#domains{
    font-size: 40px;
color: red;
}
div#alpha_two_code{
    font-size: 30px;
    color: chartreuse;
}


input#country{
    color:rgb(43, 49, 226);
    background-color: cornsilk;
}
