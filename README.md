# react-to-print  

```
npm install --save react-to-print
```  
# https://www.npmjs.com/package/react-to-print

# 1. Print without typescript:-
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
