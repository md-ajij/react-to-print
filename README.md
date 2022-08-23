# react-to-print  

```
npm install --save react-to-print
```  
# https://www.npmjs.com/package/react-to-print
# https://linguinecode.com/post/how-to-use-react-useref-with-typescript

# 1.1 TS of useRef Hook  

```
import React, { useRef, useLayoutEffect } from 'react';

const App = () => {
  const h1Ref = useRef<HTMLHeadingElement>(null);

  console.log(h1Ref) // { current: null }

  useLayoutEffect(() => {
    console.log(h1Ref); // { current: <h1_object> }
  })

  return (
    <h1 ref={h1Ref}>App</h1>
  )
}

export default App;
```  


# 1.2 <div> reference type  
  
```
const divRef = React.useRef<HTMLDivElement>(null);
```  

# 1.3 <button> reference type  
  
```
const buttonRef = React.useRef<HTMLButtonElement>(null);
```  

# 1.4 <br /> reference type  
  
  
```
const brRef = React.useRef<HTMLBRElement>(null);
```  

# 1.5 <a> reference type  
  
```
const linkRef = React.useRef<HTMLLinkElement>(null);
```  


1. Print without typescript:-
# index.js

```
import React, { useRef } from 'react';
import { useReactToPrint } from 'react-to-print';

const Home = () => {
  const componentRef = useRef();
  const handlePrint = useReactToPrint({
    content: () => componentRef.current,
    documentTitle:'emp-data',
    onAfterPrint:()=>alert('Print Success')
  });

  return (
    <>
      <div ref={componentRef} style={{width:"100%",height:window.innerHeight}}>
          <h1>Write here the text that you want to print</h1>
          <button onClick={handlePrint}>Print</button>
      </div>
    </>
  );
};
export default Home;
```  
# 2. Print without Typescript:-
# componentToPrint.js
```
 const ComponentToPrint =()=>{
   return(
     <div>
         <p>
            Lorem500
         </p>
     </div>
   
   );
 }
 export default ComponentToPrint;
 ```  
 
 # index.js  
 
```
import React, { useRef } from 'react';
import { useReactToPrint } from 'react-to-print';

import { ComponentToPrint } from './ComponentToPrint';

const Example = () => {
  const componentRef = useRef();
  const handlePrint = useReactToPrint({
    content: () => componentRef.current,
  });

  return (
    <div>
      <ComponentToPrint ref={componentRef} />
      <button onClick={handlePrint}>Print</button>
    </div>
  );
};
```  
# 3. Print with typescript:-

# index.js

```
import React, { useRef } from 'react';
import { useReactToPrint } from 'react-to-print';

const Home = () => {
  //const componentRef = useRef();
  const componentRef = useRef<HTMLDivElement>(null)
  const handlePrint = useReactToPrint({
    content: () => componentRef.current,
    documentTitle:'emp-data',
    onAfterPrint:()=>alert('Print Success')
  });

  return (
    <>
      <div ref={componentRef} style={{width:"100%",height:window.innerHeight}}>
          <h1>Write here the text that you want to print</h1>
          <button onClick={handlePrint}>Print</button>
      </div>
    </>
  );
};
export default Home;
