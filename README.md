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


#script.js
var div = document.createElement("div")
div.style.textAlign = "center";

var input = document.createElement("input");
input.setAttribute("type", "text");
input.setAttribute("id", "country");

var button = document.createElement("button");
button.setAttribute("type", "button");
button.innerHTML = "Search";
button.addEventListener("click",foo);

let domains= document.createElement("div");
domains.setAttribute("Id", "domains");
let alpha_two_code = document.createElement("alpha_two_code");
alpha_two_code.setAttribute("Id", "alpha_two_code");
// let state-province= document.createElement("div");
// state-province.setAttribute("Id","state-province");

div.append(input,button,domains,alpha_two_code);
document.body.append(div);

async function foo() {

    let res = document.getElementById("country").value;
    var url = `http://universities.hipolabs.com/search?country/${res}`;

    let result = await fetch(url);
    let result1 = await result.json();
    let index = result1.length-1;
    console.log(result1[index].domains);
    domains.innerHTML =`domains:${result1[index].domains}`;

    console.log(result1[index].alpha_two_code);
    alpha_two_code.innerHTML =`alpha_two_code:${result1[index].alpha_two_code}`;

    // console.log(result1[index].state-province);
    // state-province.innerHTML =`total state-province:${result1[index].state-province}`;







}





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
