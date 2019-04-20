# 1step

```markup
<input type="text" id="num" class="inp_txt"> 
 <button data-cl='minus'>-</button>
 <button data-cl='plus'>+</button>
```

```javascript
<script>
    var num = document.getElementById('num');
    var bs = document.querySelectorAll('button');
    var n = Number(1);
    num.value = n;
    function count(){        
        result = num.value; 
        calc = this.getAttribute('data-cl');
        if(isNaN(result)){
            //console.log(parseFloat(result));
            result = parseFloat(result);
            alert('숫자만뽑아줄께');
        }else{    
            if(calc == 'minus'){             
                //console.log("뺄꺼야");
                result--;
            }else if(calc == 'plus'){
                //console.log("더할꺼야");
                result++;
            } 
        }   
              
        num.value = result;
    }
    for(var i = 0; i<bs.length;i++){
        bs[i].addEventListener('click',count);
    }
 </script>
```

