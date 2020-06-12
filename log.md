# #301DaysOfCode - Log
The daily log of my **#301DaysOfCode** challenge.

## Log 1

### Day 1: [4th June 2020]

**Today's Progress: I have been learning React , intermediate level for the past few days from Scrimba, and I really find it much easier after practising  on the scrimba platform. Today, I learnt how to do a basic React form, and practised it in my codepen file**

**Thoughts:*Hope, by the end of this challenge, I become a React expert as I love React but sometimes I find it intimidating to do without googling, hehe*

**Link to work:*This is my codepen link to my practice session on React Form, very basic and just a practice stuff based on what I am learning on scrimba. Here is the link : https://codepen.io/meeramenon07/pen/YzymZrQ*





## Log 2

### Day 2: [5th June 2020]

**Today's progress: I am learning my React form lessons on scrimba and in this practise session, I learnt a lot about making different types of input types such as radio and checkbox in React Forms.**

The code for this lesson:
class App extends Component {
    constructor() {
        super()
        this.state = {
            firstName: "",
            lastName: "",
            age: "",
            gender: "",
            destination: "",
            isVegan: false,
            isKosher: false,
            isLactoseFree: false
        }
        this.handleChange = this.handleChange.bind(this)
    }
    
    handleChange(event) {
        const {name, value, type, checked} = event.target
        type === "checkbox" ? 
            this.setState({
                [name]: checked
            })
        :
        this.setState({
            [name]: value
        }) 
    }
    
    render() {
        return (
            <main>
                <form>
                    <input 
                        name="firstName" 
                        value={this.state.firstName} 
                        onChange={this.handleChange} 
                        placeholder="First Name" 
                    />
                    <br />
                    
                    <input 
                        name="lastName" 
                        value={this.state.lastName}
                        onChange={this.handleChange} 
                        placeholder="Last Name" 
                    />
                    <br />
                    
                    <input 
                        name="age" 
                        value={this.state.age}
                        onChange={this.handleChange} 
                        placeholder="Age" 
                    />
                    <br />
                    
                    <label>
                        <input 
                            type="radio" 
                            name="gender"
                            value="male"
                            checked={this.state.gender === "male"}
                            onChange={this.handleChange}
                        /> Male
                    </label>
                    
                    <br />
                    
                    <label>
                        <input 
                            type="radio" 
                            name="gender"
                            value="female"
                            checked={this.state.gender === "female"}
                            onChange={this.handleChange}
                        /> Female
                    </label>
                    
                    <br />
                    
                    <select 
                        value={this.state.destination} 
                        name="destination" 
                        onChange={this.handleChange}
                    >
                        <option value="">-- Please Choose a destination --</option>
                        <option value="germany">Germany</option>
                        <option value="norway">Norway</option>
                        <option value="north pole">North Pole</option>
                        <option value="south pole">South Pole</option>
                    </select>
                    
                    <br />
                    
                    <label>
                        <input 
                            type="checkbox"
                            name="isVegan"
                            onChange={this.handleChange}
                            checked={this.state.isVegan}
                        /> Vegan?
                    </label>
                    <br />
                    
                    <label>
                        <input 
                            type="checkbox"
                            name="isKosher"
                            onChange={this.handleChange}
                            checked={this.state.isKosher}
                        /> Kosher?
                    </label>
                    <br />
                    
                    <label>
                        <input 
                            type="checkbox"
                            name="isLactoseFree"
                            onChange={this.handleChange}
                            checked={this.state.isLactoseFree}
                        /> Lactose Free?
                    </label>
                    <br />
                    
                    <button>Submit</button>
                </form>
                <hr />
                <h2>Entered information:</h2>
                <p>Your name: {this.state.firstName} {this.state.lastName}</p>
                <p>Your age: {this.state.age}</p>
                <p>Your gender: {this.state.gender}</p>
                <p>Your destination: {this.state.destination}</p>
                <p>Your dietary restrictions:</p>
                
                <p>Vegan: {this.state.isVegan ? "Yes" : "No"}</p>
                <p>Kosher: {this.state.isKosher ? "Yes" : "No"}</p>
                <p>Lactose Free: {this.state.isLactoseFree ? "Yes" : "No"}</p>
                
            </main>
        )
    }
}

ReactDOM.render(<App />, document.getElementById("root"));




**Thoughts:*Hope, by the end of this challenge, I become a React expert as I love React but sometimes I find it intimidating to do without googling, hehe*

**Link to work:*This is my codepen link to my practice session on React Form, very basic and just a practice stuff based on what I am learning on scrimba. Here is the link : https://codepen.io/meeramenon07/pen/JjGoLXy?editors=1010*


## Log 3

### Day 3: [6th June 2020]

**Today's progress: I am learning my React form lessons on scrimba and in this practise session, I learnt about the Container and Component Architecture in React for making the React Forms. Special thanks to Bob Ziroll for these lessons by Bob Ziroll in React lessons, Scrimba**
Writing down the code in my codepen file so that I can retrieve later for my projects:
The html : <div id="root"></div>
The javascript :

import React from "react"

function FormComponent(props) {
    return (
        <main>
            <form>
                <input 
                    name="firstName" 
                    value={props.data.firstName} 
                    onChange={props.handleChange} 
                    placeholder="First Name" 
                />
                <br />
                
                <input 
                    name="lastName" 
                    value={props.data.lastName}
                    onChange={props.handleChange} 
                    placeholder="Last Name" 
                />
                <br />
                
                <input 
                    name="age" 
                    value={props.data.age}
                    onChange={props.handleChange} 
                    placeholder="Age" 
                />
                <br />
                
                <label>
                    <input 
                        type="radio" 
                        name="gender"
                        value="male"
                        checked={props.data.gender === "male"}
                        onChange={props.handleChange}
                    /> Male
                </label>
                
                <br />
                
                <label>
                    <input 
                        type="radio" 
                        name="gender"
                        value="female"
                        checked={props.data.gender === "female"}
                        onChange={props.handleChange}
                    /> Female
                </label>
                
                <br />
                
                <select 
                    value={props.data.destination} 
                    name="destination" 
                    onChange={props.handleChange}
                >
                    <option value="">-- Please Choose a destination --</option>
                    <option value="germany">Germany</option>
                    <option value="norway">Norway</option>
                    <option value="north pole">North Pole</option>
                    <option value="south pole">South Pole</option>
                </select>
                
                <br />
                
                <label>
                    <input 
                        type="checkbox"
                        name="isVegan"
                        onChange={props.handleChange}
                        checked={props.data.isVegan}
                    /> Vegan?
                </label>
                <br />
                
                <label>
                    <input 
                        type="checkbox"
                        name="isKosher"
                        onChange={props.handleChange}
                        checked={props.data.isKosher}
                    /> Kosher?
                </label>
                <br />
                
                <label>
                    <input 
                        type="checkbox"
                        name="isLactoseFree"
                        onChange={props.handleChange}
                        checked={props.data.isLactoseFree}
                    /> Lactose Free?
                </label>
                <br />
                
                <button>Submit</button>
            </form>
            <hr />
            <h2>Entered information:</h2>
            <p>Your name: {props.data.firstName} {props.data.lastName}</p>
            <p>Your age: {props.data.age}</p>
            <p>Your gender: {props.data.gender}</p>
            <p>Your destination: {props.data.destination}</p>
            <p>Your dietary restrictions:</p>
            
            <p>Vegan: {props.data.isVegan ? "Yes" : "No"}</p>
            <p>Kosher: {props.data.isKosher ? "Yes" : "No"}</p>
            <p>Lactose Free: {props.data.isLactoseFree ? "Yes" : "No"}</p>
            
        </main>
    )
}
export default FormComponent
import React, {Component} from "react"
import FormComponent from "./FormComponent"

class Form extends React.Component {
    constructor() {
        super()
        this.state = {
            firstName: "",
            lastName: "",
            age: "",
            gender: "",
            destination: "",
            isVegan: false,
            isKosher: false,
            isLactoseFree: false
        }
        this.handleChange = this.handleChange.bind(this)
    }
    
    handleChange(event) {
        const {name, value, type, checked} = event.target
        type === "checkbox" ? 
            this.setState({
                [name]: checked
            })
        :
        this.setState({
            [name]: value
        }) 
    }
    
    render() {
        return(
            <FormComponent
                handleChange={this.handleChange}
                data={this.state}
            />
        )
    }
}
export default Form

import React, {Component} from "react"
import Form from "./FormContainer"

function App() {
    return (
        <Form />
    )
}
export default App

ReactDOM.render(<App />, document.getElementById("root"))


As seen above, it is worth remembering and noting down that the FormComponent.js goes at the top of the code, below that is the FormContainer.js and below that is the App.js
While writing the code in scrimba, the import and export of the files in js are to be mentioned but it is not required in the codePen since the export and import of the js files are automatically done behind the hoods by the codePen files.



**Thoughts:*Hope, by the end of this challenge, I am slowly becoming a React somebody from nobody, without googling, just need to refer to my notes, hence documenting here, very handy indeed, hehe*

**Link to work:*This is my codepen link to my codepen file with the above code that I learnt from Bob Ziroll, Scrimba React.j. Here is the link : https://codepen.io/meeramenon07/full/VweLeOL*





Day 4- Day 5: [7th June 2020- 8th June 2020]
Two days, I was just into revision of this lesson not much of progress: I am learning my React form lessons on scrimba and in this practise session, I learnt about the Container and Component Architecture in React for making the React Forms. Special thanks to Bob Ziroll for these lessons by Bob Ziroll in React lessons, Scrimba Writing down the code in my codepen file so that I can retrieve later for my projects: The html :

The javascript :
import React from "react"

function FormComponent(props) { return (


            <input 
                name="lastName" 
                value={props.data.lastName}
                onChange={props.handleChange} 
                placeholder="Last Name" 
            />
            <br />
            
            <input 
                name="age" 
                value={props.data.age}
                onChange={props.handleChange} 
                placeholder="Age" 
            />
            <br />
            
            <label>
                <input 
                    type="radio" 
                    name="gender"
                    value="male"
                    checked={props.data.gender === "male"}
                    onChange={props.handleChange}
                /> Male
            </label>
            
            <br />
            
            <label>
                <input 
                    type="radio" 
                    name="gender"
                    value="female"
                    checked={props.data.gender === "female"}
                    onChange={props.handleChange}
                /> Female
            </label>
            
            <br />
            
            <select 
                value={props.data.destination} 
                name="destination" 
                onChange={props.handleChange}
            >
                <option value="">-- Please Choose a destination --</option>
                <option value="germany">Germany</option>
                <option value="norway">Norway</option>
                <option value="north pole">North Pole</option>
                <option value="south pole">South Pole</option>
            </select>
            
            <br />
            
            <label>
                <input 
                    type="checkbox"
                    name="isVegan"
                    onChange={props.handleChange}
                    checked={props.data.isVegan}
                /> Vegan?
            </label>
            <br />
            
            <label>
                <input 
                    type="checkbox"
                    name="isKosher"
                    onChange={props.handleChange}
                    checked={props.data.isKosher}
                /> Kosher?
            </label>
            <br />
            
            <label>
                <input 
                    type="checkbox"
                    name="isLactoseFree"
                    onChange={props.handleChange}
                    checked={props.data.isLactoseFree}
                /> Lactose Free?
            </label>
            <br />
            
            <button>Submit</button>
        </form>
        <hr />
        <h2>Entered information:</h2>
        <p>Your name: {props.data.firstName} {props.data.lastName}</p>
        <p>Your age: {props.data.age}</p>
        <p>Your gender: {props.data.gender}</p>
        <p>Your destination: {props.data.destination}</p>
        <p>Your dietary restrictions:</p>
        
        <p>Vegan: {props.data.isVegan ? "Yes" : "No"}</p>
        <p>Kosher: {props.data.isKosher ? "Yes" : "No"}</p>
        <p>Lactose Free: {props.data.isLactoseFree ? "Yes" : "No"}</p>
        
    </main>
)
} export default FormComponent import React, {Component} from "react" import FormComponent from "./FormComponent"

class Form extends React.Component { constructor() { super() this.state = { firstName: "", lastName: "", age: "", gender: "", destination: "", isVegan: false, isKosher: false, isLactoseFree: false } this.handleChange = this.handleChange.bind(this) }

handleChange(event) {
    const {name, value, type, checked} = event.target
    type === "checkbox" ? 
        this.setState({
            [name]: checked
        })
    :
    this.setState({
        [name]: value
    }) 
}

render() {
    return(
        <FormComponent
            handleChange={this.handleChange}
            data={this.state}
        />
    )
}
} export default Form

import React, {Component} from "react" import Form from "./FormContainer"

function App() { return ( ) } export default App

ReactDOM.render(, document.getElementById("root"))

As seen above, it is worth remembering and noting down that the FormComponent.js goes at the top of the code, below that is the FormContainer.js and below that is the App.js While writing the code in scrimba, the import and export of the files in js are to be mentioned but it is not required in the codePen since the export and import of the js files are automatically done behind the hoods by the codePen files.

**Thoughts:Hope, by the end of this challenge, I am slowly becoming a React somebody from nobody, without googling, just need to refer to my notes, hence documenting here, very handy indeed, hehe

**Link to work:This is my codepen link to my codepen file with the above code that I learnt from Bob Ziroll, Scrimba React.j. Here is the link : https://codepen.io/meeramenon07/full/VweLeOL





**Link to work:*This is my codepen link to my practice session on React Form, very basic and just a practice stuff based on what I am learning on scrimba. Here is the link : https://codepen.io/meeramenon07/pen/JjGoLXy?editors=1010*




## Log 6

### Day 6: [9th June 2020]

**Today's progress: Started with the next lesson on scrimba on the making of a Meme generator, right from scratch! It is really fun! I am learning a lot of stuff by learning and re-learning and un-learning what I had learnt last time, so, along the way, I make mistakes and learn all the way along! Have not yet completed this lesson and thought of continuing it for tomorrow!

The code for today is:

index.js
import React from "react"
import ReactDOM from "react-dom"
import App from "./App"

ReactDOM.render(<App />, document.getElementById("root"))

Header.js

import React from "react"

function Header(){
    return(
        
          <header>
          <h1><img src="https://www.pngitem.com/pimgs/m/96-966418_happy-face-meme-png-transparent-rage-faces-png.png"/></h1>
          </header>
        
    )
}
export default Header


MemeGenerator.js

import React, {Component} from "react"

class MemeGenerator extends React.Component{
    constructor(){
        super()
        this.state={}
    }
    render(){
        return(
            <h1>MEME GENERATOR SECTION</h1>
        )
    }      
        
     
    
}

export default MemeGenerator


App.js

import React from "react"
import Header from "./Header"
import MemeGenerator from "./MemeGenerator"

/**
 * Create 2 new components - Header and MemeGenerator
 * Header will only display things
 * MemeGenerator will be calling to an API and holding on to data
 * Each should be in their own file of the same name
 */

function App() {
    return (
        <div>
         <Header />
         <MemeGenerator />
        </div>
    )
}

export default App

**Thoughts:*I am beginning to love React and feeling much more confident now*




## Log 7

### Day 7: [10th June 2020]

**Today's Progress: I have been learning React , intermediate level for the past few days from Scrimba, and I really find it much easier after practising  on the scrimba platform. Today, Continuing with my capstone project of building a meme generator**

**Thoughts:*Hope, by the end of this challenge, I become a React expert as I love React but I cannot do it all in one day, going to do it over a few more days in this way, this way by taking it slowly, i will remember and understand much better*




Log 8
Day 8: [11th June 2020]
Today's Progress: I have been learning React , intermediate level for the past few days from Scrimba, and I really find it much easier after practising on the scrimba platform. Today, Continuing with my capstone project of building a meme generator

**Thoughts:Hope, by the end of this challenge, I become a React expert as I love React but I cannot do it all in one day, going to do it over a few more days in this way, this way by taking it slowly, i will remember and understand much better





## Log 9

### Day 9: [12th June 2020]

**Today's Progress: When things get challenging, it is better to take a step backward and re do steps and this is what I am doing today, start from scratch all over again for my capstone project of making the meme generator**

So, I did my Header and MemeGenerator components for my App and decided to stop here for today and proceed from here tomorrow so that my Muscle Memory will not get strained and retain the code even better! Following is the code I did for today:

index.js

<html>
    <head>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <div id="root"></div>
        <script src="index.pack.js"></script>
    </body>
</html>


index.js

import React from "react"
import ReactDOM from "react-dom"
import App from "./App"

ReactDOM.render(<App />, document.getElementById("root"))


import React from "react"

function Header(){
    return(
        <h1> HEADER</h1>
    )
}

export default Header


import React, {Component} from "react"
MemeGenerator.js
class MemeGenerator extends Component{
    constructor(){
        super()
        this.state={
            
        }
    }
    render(){
        return(
            <h1>MemeGenerator</h1>
        )
    }
}


export default MemeGenerator


App.js
import React from "react"
import Header from "./Header"
import MemeGenerator from "./MemeGenerator"

/**
 * Create 2 new components - Header and MemeGenerator
 * Header will only display things
 * MemeGenerator will be calling to an API and holding on to data
 * Each should be in their own file of the same name
 */

function App() {
    return (
        <div>
         <Header />
         <MemeGenerator />
        </div>
    )
}

export default App

**Thoughts:*Rome was not built in one day and I am dead SURE that I am going to get expert on this React so that I dont need to google for any react coding! I want to get this right without googling!*

