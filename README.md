# SolverAI
SolverAI app is a mini version of PhotoMath(https://photomath.app/en/) mobile app that solves math problems. 
<br/>It is developed in PowerApps+Power Automate

<br/>
<br/>
<h2>Sample Screens</h2>
<img src="https://raw.githubusercontent.com/iberpoint/SolverAI-App/master/ScreenShot.png" width=500 />
<br/><br/>
<img src="https://raw.githubusercontent.com/iberpoint/SolverAI-App/master/ScreenShot-2.png" width=500 />
<br/><br/>
<img src="https://raw.githubusercontent.com/iberpoint/SolverAI-App/master/ScreenShot-3.png" width=500 />
<br/><br/>

<h2>Power Automate Flow</h2>
<br><p>The app uses a flow in the backend that connects to an API to handle math expressions. For this app, I have preferred using MathJS Web API</p>
<p>MathJS Web API can be accessed from here: https://api.mathjs.org </p>
<p>MathJS Home Page: https://mathjs.org </p>

<br/><br/>

<h3>Here's how flow is created and works</h3>
<ul>
  <li>Create a new instant workflow in Power Automate that uses PowerApps button</li>
  <li>Add "Initialize Variable" action. We send the data from AIBuilder service to this flow using parameters and that parameter will be the text of mathematical expression</li>
  <li>Create a HTTP call(GET) to access MathJS Web API to handle math expression and calculate result. It will be using URL encoding for the variable we declared above. Make sure you add the variable as parameter to url encode function. For instance, It should be defined like "encodeUriComponent(triggerBody()['Initializevariable_Value'])" </li>
  <li>Respond the result from HTTP call to the powerapps. Make sure you select the string type and return the "Body" parameter coming from HTTP call</li>
</ul>
