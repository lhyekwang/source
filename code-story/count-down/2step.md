---
description: '기능 추가 : 최대최소넣기'
---

# 2step

리뷰변경사

* [x] 변수명을 정확하
* [x] 숫자검사부분만 함수로 적용
* [x] 형변환
* [x] parseInt 로 변

기능구현 

* [x] 타입체크
* [x] input 안에 keyup 함수 적용
* [x] 최대최소넣기 
* [ ] 함수 내부에 result, calc 변수 선언시 var, let, const 키워드
* [x] 기능별로 함수 분

이론체크사항

* [ ] JS 데이타 타입 
* [ ] documnet.querySelecotrAll 유사배열 사용시 유의점
* [ ] addEventListnerner click 과 코드비교
* [ ] isNaN으로 제어시 이슈체크\([https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global\_Objects/isNaN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/isNaN)\)
* [ ] 조건문 정리 \(if, 삼항연산자, switch // ==, === 체크타입\) 
* [ ] 할당연산계산법 
* [ ] parseFloat, parseInt 의 차이

```javascript
<script>
    'use strict';
    var result; 
    var calc;
    var calcAll;
    var inputNumber = document.getElementById('inputNum');
    var buttonElement = document.querySelectorAll('button');
    var guideText = document.querySelector('.message');
    var buttonMinus = document.getElementById('buttonMinus');
    var buttonPlus = document.getElementById('buttonPlus');
    var maxLevel = 5;
    var minLevel = -5;
    var state = 1;
    var result = parseInt(inputNumber.value);
    function count(){    
        result = parseInt(inputNumber.value);          
        calc = this.getAttribute('data-type');
        if(calc == 'minus'){ //console.log("뺄꺼야");
                result--;
        }else if(calc == 'plus'){ //console.log("더할꺼야");
            result++;
        }            
        if(state == 0){ //console.log("에러상황");
            result = result;
        }else{                
            inputNumber.value = result;
        }             
        inpuEvent();          
    }  
    function inpuEvent(){
        result = parseInt(inputNumber.value);   
        if(result < minLevel || result > maxLevel ){ 
            guideText.innerHTML = ('숫자범위넘음!');
            state = 0;            
        }else if(isNaN(result)){
            guideText.innerHTML = ('숫자넣으시옹!'); 
            state = 0;
        }else{
            state = 1;
            guideText.innerHTML = ('');
        }            
        if(result == maxLevel && state == 1){
            guideText.innerHTML = ( maxLevel+'보다큰수는안되어요!');
            buttonPlus.disabled = true;
            state = 2;  
        }else if(result == minLevel && state == 1){  
            guideText.innerHTML = ( minLevel+' 보다작은수는안되어요!');
            buttonMinus.disabled = true;
            state = 2; 
        }else{
            for(var i = 0; i<buttonElement.length;i++){                
                buttonElement[i].disabled = false;            
            }
        }         
        
    }
    
    for(var i = 0; i<buttonElement.length;i++){
        buttonElement[i].addEventListener('click',count);            
    }
    inputNumber.addEventListener('keyup', inpuEvent);
    
</script>
```

