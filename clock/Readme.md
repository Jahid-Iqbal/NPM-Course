# Challenge Details

Create a clock that will be keep updating using moment.js

**Implementation Details:**  
* Creating NPM using command `npm init`.
* Install moment using command `npm install moment`
* Creating a folder named `src`
* Creating a file named `index.html`
* Creating files under `src` folder `index.js` and `style.css`
* Copy the code of `moment.js` to `index.js` file.

**Implement below additional code:**  
```js
const display=()=>{
    const time=moment().format("LTS");
    console.log(time);
    const element=document.getElementById("clock");
    element.innerHTML=time;
}

const updateTime=()=>{
    display();
    setTimeout(updateTime,1000);
}

updateTime();
```
