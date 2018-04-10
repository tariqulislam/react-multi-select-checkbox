#Multiple checkbox handling by React JS#
React is most popular front end development framework. For our application development purpose we have build different complex web component to fullfill business requirment. Multiple checkbox selection is important UI feature for standard front end development. Today i have provide you some example about multiple checkbox selection with react js using the state of react js. 
First i have use create react app for react js application boilerplate to start my example projects
> npm install -g create-react-app (npm command)
After complete the installation, i have create the project by provide the command
```> create-react-app react-multi-select-checkbox```
When finish setup project, then i have to remove generated default htm code code from App.js create the state for checkbox group component



I will create state at constructor named fruites . we can create the state by call this.state = {} in constructor . fruites is the array of fruite items checkbox group. render is the function for wrap the html and javascript or es6 or es7 code and render into browser. For react js you must return the fully qualified dom element within return statement.
Create the Chield Checkbox with click event which is bind inparent component App.js we can discuss it later.



In CheckBox component all the porperties are comes from parent. this component is called dump or presentational component. onClick event is used for handle the checked or unchecked state when click on checkbox in checkbox group.
then i will create checkbox group and Check/ Uncheck All checkbox in App.js file



In this code snippet, i have add the html code which will contains Check/ Uncheck All checkbox. i have use javascript map() function to iterate through the fruites state and return CheckBoxelement each iteration. Pass All the properties from App component to CheckBox component by {...fruite} statement with in CheckBox component. Then all the properties are accessible at CheckBox element by props argument. I have change some css at App.css file that’s are. I have add the css style by call import ./App.css to App component.



After complete the design, output of the react application will be
Output design Check All Examplethen i have to add the action handler for Check/ Uncheck All and Individual checkbox add App component and pass it to chield component CheckBox for functional the Check/ Uncheck All and CheckBox click event.



Full code for App.js 

```filehandleAllChecked = (event) => {
   let fruites = this.state.fruites
   fruites.forEach(fruite => fruite.isChecked = event.target.checked)
   this.setState({fruites: fruites})
}```

this function is arrow function, for arrow function react by default bind this to component , no need to bind this at constructor . for first list let fruites = this.state.fruites , we use this statement to get the fruites state to local variable and then use forEach() function to iterate and manipulate the isChechecked properties true or false of fruite element. then set or change the state by this.setState({}) function. this function will checked or unchecked all the checkbox from checkbox group.

```handleCheckChieldElement = (event) => {
   let fruites = this.state.fruites
   fruites.forEach(fruite => {
     if (fruite.value === event.target.value)
       fruite.isChecked =  event.target.checked
     })
   this.setState({fruites: fruites})
}```

this function is used for check the individual checkbox from group of checkbox. this function is like previous one, execption is, i have check the checked element value is matched with element value of state. if matched it will change the state of that individual CheckBox . then i have to pass the element handler to chield component (`CheckBox.js`) by add handleCheckChieldElement function to props arguments by:

```<CheckBox handleCheckChieldElement={this.handleCheckChieldElement} {…fruite} />```
