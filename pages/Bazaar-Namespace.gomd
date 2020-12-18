
done on vscode

| Namespace          | Owner                          | Host           |Authentication |Rate Limiting |Service Preview Enabled|
|--------------------|--------------------------------|--------------- |--------------|---------------|-----------------------|
| bazaar             | Bazaar Project Team            | aes-demo.com   | Yes          | Yes           | Yes                   |


<br />
<br />
<br />
Authentication:&nbsp;&nbsp;&nbsp;&nbsp;Use the following Filter Policy as template
<br />
<br />
<br />  


apiVersion:&nbsp;&nbsp;getambassador.io/v2     
kind:&nbsp;&nbsp;FilterPolicy  
metadata:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;name:&nbsp;&nbsp;api-filter-policy-$name  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:green"># Update this value.</span>   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;namespace:&nbsp;&nbsp;bazaar  
spec:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;rules:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- host: "aes-labs.com"       
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;path: "/foo/"        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:green"># Update this value.</span>    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;filters:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - name: keycloak-oauth2-filter    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;namespace: bazaar    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;arguments:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;scopes:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- "offline_access"
  





<br />
<br />
<br />
Rate Limiting :&nbsp;&nbsp;&nbsp;&nbsp; A Rate Limiting filter is deployed to this namespace. In order to enforce rate limiting on the service to be deployed, or add to an existing service, modify the mapping of the service per this template.
<br />
<br />
<br />  


apiVersion:&nbsp;&nbsp;getambassador.io/v2  
kind:&nbsp;&nbsp;Mapping  
metadata:  
  name:&nbsp;&nbsp;demo-backend-mapping&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:green"># Update this value.</span>  
  namespace:&nbsp;&nbsp;bazaar  
spec:  
&nbsp;&nbsp;&nbsp;&nbsp;prefix:&nbsp;&nbsp;<span style="color:blue">/backend/</span>&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:green"># Update this value.</span>    
&nbsp;&nbsp;&nbsp;&nbsp;service:&nbsp;&nbsp;<span style="color:blue">'backend</span> .bazaar'</span>&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:green"># Update this value.</span>     
&nbsp;&nbsp;&nbsp;&nbsp;docs:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;path:&nbsp;&nbsp;<span style="color:blue">/.ambassador-internal/openapi-docs</span>   
&nbsp;&nbsp;&nbsp;&nbsp;labels:  <span style="color:green">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;# Add this value.</span>     
&nbsp;&nbsp;&nbsp;&nbsp;ambassador:  <span style="color:green">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;# Add this value.</span>  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- request_label: <span style="color:green">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;# Add this value.</span>   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- &nbsp;&nbsp;5rpm <span style="color:green">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;# Add this value.</span>   