

## selectors
- p {  
	
  }
- `.` -> class  
	```css
	.class-name{

	color: red;
	}
	```
- `#` ->  id 
	```css
	.class-name{

	color: red;
	}
	```
-  with attribute name
	```css
	input[type=email]{

	background-color: blue;

	}
	```

## Border
- we should write 3 element to correctly define border
	- border-width
	- border-color
	- border-style
	```css
		border-width: 15px;
		border-color: black;
		border-style: solid;
	```
- or we can write it (مفيش ترتيب )
  ```css
  border: 15px black solid ;
  ```

	![[Pasted image 20240714155741.png]]
## Fonts
```css
	 p{
	
	font-family: Arial, Helvetica, sans-serif; /*browser chooses first , if not supported chooses second one , etc ..*/
	
	font-size: 25px; /* smaal | medium or with px */
	
	font-weight: 500; /*100 -> 900*/
	}
```

	 ![[Pasted image 20240714162315.png]]
```css
	p{
	line-height: 35px;
	letter-spacing: 10px;
	}
```
	![[Pasted image 20240714162521.png]]


## COLORS
- background-color: value;
  - red  , black
  - rgb(0,0,0) (0-255)
  - rgba(0,0,0,0) last one is alpha (trasparency)
  -  hex #000000 (max if ff) (#ff0000 = red)
- background-size: url("path") ;
- background-size: 
  - auto (default one )
     ![[Pasted image 20240714173258.png]]
  - cover (exact height but crop width)
	    ![[Pasted image 20240714173316.png]]
  - contain (natural size but if div is greater it duplicate)
	  ![[Pasted image 20240714173438.png]]
 - width  height (if greater -> duplicate , smaller -> crop)
	  ![[Pasted image 20240714173615.png]]  here div height and width is double photo height and width
- background-repeat : 
  - repeat (default)
  - no-repeat (photo top left)
  - repeat-x (horizontal)
  - repeat-y (vertical)
- background-position : 
  - left top (default) 
  - center bottom 
  - 10px 0px (10 from left and 0 from top) 
	    ![[Pasted image 20240714174548.png]]
- 10% 50% (left top) 
	  ![[Pasted image 20240714174712.png]]
## Padding VS Margin 
- Padding : (ازاحه داخليه )
  - padding-direction
	  - padding-left: 10px;
	  - padding-right: 10px;
	  - padding-top: 10px;
	  - padding-bottom: 10px;
  - padding : 10px (padding 10 px from all directions)
  - padding : 10px 15px 5px 2px (top right bottom left)
  - padding : 10px 5px (10 top and bottom && 5 right and left)
- Margin (ازاحه خارجيه ) + (ينطبق عليه زي padding)
  - margin-left : 25% (لو اصلا السايز 50% بتاع الديف هيكون متسنتر  )
  - margin-left: auto ; 
    margin-right: auto;  (always in the center)
  - margin : auto ;   (always in the center) 
## Fonts
