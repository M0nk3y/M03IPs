    MO3IP: <to be assigned>
    Title: API or widget for websites 
    Author: Matt Topham 0x752607dc81e0336ea6ddccced509d8fd28610b54 @thetopham thetopham@gmail.com
    Status: Draft
    Created: 2017-11-20
    Permalink:

## Simple Summary
The creation of an easy to use API or widget for websites to display token amounts and other optional functions.

## Abstract
An api or widget is needed in order to display current token amounts on websites in real time.

## Motivation
I was searching for a way to add the PRE token amount to display on a website automatically in real time without manual updates and I couldn't find the tool I was looking for. We must make it easy and simple to display blockchain information on websites in order to further enhance industry growth.

## Specification
Easy to use API or widget for websites
Display Preminer PRE total received on websites in real time
Track Preminer performance - inputs and output totals for given time period to generate performance %

## Rationale
API and widget development helps promote industry creativity and further adoption of m0nk3y by allowing creators to create more easily. It would be beneficial to the community to track preminers and m0nk3y tokens on a website. In order to do so, an API or widget needs to be created. With API and widgets, the community can create informative websites about m0nk3y tokens and preminers with ease.

## Implementations
Get balance of ico preminer 
https://api.etherest.io:8080/v1/main/0x30765406d51091ed78ff13c107731daf3be5ef16/balanceOf/0x73122C1b5DAE1E0b900460a96E1F05b8B1A433ab/

<!DOCTYPE html>
<html>
  <head>
    <title>topham sucks at javascript</title>

    <script type="text/javascript">
        
        
    function div(num) {
        for (var i =0; i < 18; i++)
        {
            num = num / 10;
        }
        return num;
    }

    var xhr = new XMLHttpRequest();

    
    function getbalance(){
        
        
        xhr.open("GET", "https://api.etherest.io:8080/v1/main/0x30765406d51091ed78ff13c107731daf3be5ef16/balanceOf/0x73122C1b5DAE1E0b900460a96E1F05b8B1A433ab/", true);
        xhr.setRequestHeader("Content-type", "application/json");
        xhr.send();
        
        xhr.onreadystatechange = setbalance;
        
    }
       
    function setbalance(e) {
        if (xhr.readyState == 4 && xhr.status == 200) {
             
             var response = JSON.parse(xhr.responseText);
             document.getElementById("lol").innerText = div(Number(response.response));
        }
      }
             
        </script>
    </head>
    <body onload="getbalance()">
    <div id="lol">lol</div>
    </body>
</html>

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
