## Loader_in_NextS
This is how to use loader when a route changes.

### _app.js
```

import Router from "next/router";

const MyApp = ({ Component, pageProps }) => {
  const [ loading, setLoading ] = useState(false);

  Router.events.on("routeChangeStart",(url)=>{
    setLoading(true);
  })
  Router.events.on("routeChangeComplete",(url)=>{
    setLoading(false);
  })


  if(loading){
    return <h1> Loading....<h1/>
  }
    
  return <Component {...pageProps} />
  
  }

```
