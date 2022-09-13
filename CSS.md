# CSS

## Inheritance(繼承)
*  **initial**: *原本屬性CSS屬性預設值*
*  **inherit**: *父親的屬性值(一直找到具有設定值的父親[類似鍊的概念])*
*  **unset**: *如果屬性是繼承的，則使用父級的屬性值，否則使用初始值*
*  **revert**: *瀏覽器的用戶代理樣式表的屬性值*

## 字體單位
* px：絕對單位，代表螢幕中每個「點」( pixel )。
* em：相對單位，每個子元素透過「倍數」乘以父元素的 px 值。
* rem：相對單位，每個元素透過「倍數」乘以根元素的 px 值。
* %：相對單位，每個子元素透過「百分比」乘以父元素的 px 值。

***

## variables

>建立變數:規則 --{變數名稱}:{值} 
```css
--csscoke-red: #f00;
```

>套用變數: 使用var()內建函數將css變數作為參數帶入
```css
.yourclass {
	color: var(--csscoke-red );
}

```
>建立全域變數
```css
:root {
	--csscoke-red: #f00;
}
```
>javascript修改css變數

```javascript
//document.documentElement.style.setProperty('--css變數名', value)
document.documentElement.style.setProperty('--mybgColor', '#333')
```

***

## flex
### 包裹的flex(flex container)

1. align-content: 需搭配flex-wrap: wrap 使用才有效
2. justifify-content: 主軸對齊方式
3. align-items: 次軸對齊方式
4. flex-wrap: 設定換行

### 被包裹的flex元素(flex-item)
1. flex-grow: 預設值0
   
    > 元件的伸展性，是一個數值，當空間分配還有剩餘時的當前元件的伸展性，預設值為 0，如果設置為 0 則不會縮放。(比例/元素數量)*剩餘空間

2. flex-shrink: 預設值1

3. flex-basis
    * **優先權大於width**
    * 預設值auto, 等同於設定的width
    * 如果flex-basis: 寬度大於父容器flex會自收縮flex-shrink預設為1
4. flex: flex-grow(值) flex-shrink(值)  flex-basis(值) 簡寫

***

## img
* object-fit
    1.fill: 默认，不保证保持原有的比例，内容拉伸填充整个内容容器。	
    2.contain: 保持原有尺寸比例。内容被缩放。	
    3.scale-down: 保持原有尺寸比例。内容的尺寸与 none 或 contain 中的一个相同，取决于它们两个之间谁得到的对象尺寸会更小一些。
    4.cover: 保持原有尺寸比例。但部分内容可能被剪切。 
***
## 列印

### 1.列印樣式設定 @meida print
* 用以設定瀏覽器列印背景顏色時的行爲
  * print-color-adjust   
    economy（默認值）：允許瀏覽器自動調整  
    exact：使用你設定好的樣式顏色
* 設定元素跟分頁斷點之間的關係
  * break-after 
  * break-before
  * break-inside
  
```style
    //使用@meida print來設定
    @media print { 

        body{
            margin-right: 100px;
        }  

        * {
            //此屬性用以設定瀏覽器列印背景顏色時的行爲
            -webkit-print-color-adjust: exact !important;
        }

        
        //添加此類的元素不會被列印到
        .noPrint {
            display: none;
        }

        ...anystyle
    }
```
### 2.設定紙張 @page
```style
    //使用@page來設定  
    @page {
        //紙張大小
        size: A4 portrait;
        
        //紙張邊距
        margin-top: 3cm;
    }

    //只設定第一頁樣式
    @page :first {
        margin-left: 4cm;
    }
```