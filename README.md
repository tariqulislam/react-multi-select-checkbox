## Multiple checkbox handling by React JS ##

React is most popular front end development framework. For our application development purpose we have build different complex web component to fullfill business requirment. Multiple checkbox selection is important UI feature for standard front end development. Today i have provide you some example about multiple checkbox selection with react js using the state of react js.

## Installation and Prerequisites

1. You need to Install `create-react-app` package globally by this command `npm install -g create-react-app (npm command)`.
2. Download or Clone the Project from `https://github.com/tariqulislam/react-multi-select-checkbox.git`.
3. Run command on `terminal` or `cmd` `npm install` or `yarn install`.
4. Then Run command `npm start` or `yarn start`

## Available functions to access Parent and Chield Checkbox Component

1. To Access Parent Checkbox Component `onChange` event, example code
```javascript
filehandleAllChecked = (event) => {
   let fruites = this.state.fruites
   fruites.forEach(fruite => fruite.isChecked = event.target.checked)
   this.setState({fruites: fruites})
}
```
2. To Access Chield Checkbox Component `onChange` event, example code

```javascript
handleCheckChieldElement = (event) => {
   let fruites = this.state.fruites
   fruites.forEach(fruite => {
     if (fruite.value === event.target.value)
       fruite.isChecked =  event.target.checked
     })
   this.setState({fruites: fruites})
}
```
# Licences

All the Code and information of this repository free to access. This will be licence under `MIT`. User can modified it and share it and if he/she want to contribute it, Feel to free to contribue.
