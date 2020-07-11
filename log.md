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





## Log 10

### Day 10: 13th June 2020]

**Today's Progress: I am continuing with my meme generator project now- today, I did the next part of the project, which is  carrying out  the following task:   
  fetch data from an api link  
  /**
     * We'll be using an API that provides a bunch of meme images.
     * 
     * Your task:
     * make an API call to "https://api.imgflip.com/get_memes" and save the 
     * data that comes back (`response.data.memes`) to a new state property
     * called `allMemeImgs`. (The data that comes back is an array)
     */**

                         
                         The code for above task is as follows:
     
     Header.js
     
     import React from "react"

function Header() {
    return (
        <header>
            <img 
                src="http://www.pngall.com/wp-content/uploads/2016/05/Trollface.png" 
                alt="Problem?"
            />
            <p>Meme Generator</p>
        </header>
    )
}

export default Header


MemeGenerator.js

import React, {Component} from "react"

class MemeGenerator extends Component {
    constructor() {
        super()
        this.state = {
            topText: "",
            bottomText: "",
            randomImg: "http://i.imgflip.com/1bij.jpg",
            allMemeImgs: []
        }
    }
    
    componentDidMount() {
        fetch("https://api.imgflip.com/get_memes")
            .then(response => response.json())
            .then(response => {
                const {memes} = response.data
                console.log(memes[0])
                this.setState({ allMemeImgs: memes })
            })
    }
    
    render() {
        return (
            <div>
                <form>
                
                
                
                </form>
            </div>
        )
    }
}

export default MemeGenerator

**Thoughts:*Becoming more enlightened on React!*




## Log 12

### Day 12: [14th June 2020]

**Today's Progress: I am continuing with my meme generator project now- today, I did the next part of the project, which is  carrying out  the following task: 
 /**
                         * Create 2 input fields, one for the topText and one for the bottomText
                         * Remember that these will be "controlled forms
                         */
                         /**
     * Create the onChagne handler method
     * It should update the corresponding state on every change of the input box
     */
    /**
     * Create a method that, when the "Gen" button is clicked, chooses one of the
     * memes from our `allMemeImgs` array at random and makes it so that is the
     * meme image that shows up in the bottom portion of our meme generator site
     */
    
     
     The code for above task is as follows:
     
     import React, {Component} from "react"

class MemeGenerator extends Component {
    constructor() {
        super()
        this.state = {
            topText: "",
            bottomText: "",
            randomImg: "http://i.imgflip.com/1bij.jpg",
            allMemeImgs: []
        }
        this.handleChange = this.handleChange.bind(this)
    }
    
    componentDidMount() {
        fetch("https://api.imgflip.com/get_memes")
            .then(response => response.json())
            .then(response => {
                const {memes} = response.data
                this.setState({ allMemeImgs: memes })
            })
    }
    
    handleChange(event) {
        const {name, value} = event.target
        this.setState({ [name]: value })
    }
    
    /**
     * Create a method that, when the "Gen" button is clicked, chooses one of the
     * memes from our `allMemeImgs` array at random and makes it so that is the
     * meme image that shows up in the bottom portion of our meme generator site (`.url`)
     */
    
    render() {
        return (
            <div>
                <form className="meme-form">
                    <input 
                        type="text"
                        name="topText"
                        placeholder="Top Text"
                        value={this.state.topText}
                        onChange={this.handleChange}
                    /> 
                    <input 
                        type="text"
                        name="bottomText"
                        placeholder="Bottom Text"
                        value={this.state.bottomText}
                        onChange={this.handleChange}
                    /> 
                
                    <button>Gen</button>
                </form>
                <div className="meme">
                    <img src={this.state.randomImg} alt="" />
                    <h2 className="top">{this.state.topText}</h2>
                    <h2 className="bottom">{this.state.bottomText}</h2>
                </div>
            </div>
        )
    }
}

export default MemeGenerator

**Thoughts:*Becoming more enlightened on React!*






## Log 13

### Day 13: [15th June 2020]

**Today's Progress: I am continuing with my meme generator project now- today, I did the next part of the project, which is  carrying out  the following task: 
 /**
 * Create a method that, when the "Gen" button is clicked, chooses one of the
     * memes from our `allMemeImgs` array at random and makes it so that is the
     * meme image that shows up in the bottom portion of our meme generator site (`.url`)
     // get a random int (index in the array)
        // get the meme from that index
        // set `randomImg` to the `.url` of the random item I grabbed
                         
     */
     
     The code after including the handleSubmit :
     
     
     import React, {Component} from "react"

class MemeGenerator extends Component {
    constructor() {
        super()
        this.state = {
            topText: "",
            bottomText: "",
            randomImg: "http://i.imgflip.com/1bij.jpg",
            allMemeImgs: []
        }
        this.handleChange = this.handleChange.bind(this)
        this.handleSubmit = this.handleSubmit.bind(this)
    }
    
    componentDidMount() {
        fetch("https://api.imgflip.com/get_memes")
            .then(response => response.json())
            .then(response => {
                const {memes} = response.data
                this.setState({ allMemeImgs: memes })
            })
    }
    
    handleChange(event) {
        const {name, value} = event.target
        this.setState({ [name]: value })
    }
    
    handleSubmit(event) {
        event.preventDefault()
        const randNum = Math.floor(Math.random() * this.state.allMemeImgs.length)
        const randMemeImg = this.state.allMemeImgs[randNum].url
        this.setState({ randomImg: randMemeImg })
    }
    
    render() {
        return (
            <div>
                <form className="meme-form" onSubmit={this.handleSubmit}>
                    <input 
                        type="text"
                        name="topText"
                        placeholder="Top Text"
                        value={this.state.topText}
                        onChange={this.handleChange}
                    /> 
                    <input 
                        type="text"
                        name="bottomText"
                        placeholder="Bottom Text"
                        value={this.state.bottomText}
                        onChange={this.handleChange}
                    /> 
                
                    <button>Gen</button>
                </form>
                <div className="meme">
                    <img src={this.state.randomImg} alt="" />
                    <h2 className="top">{this.state.topText}</h2>
                    <h2 className="bottom">{this.state.bottomText}</h2>
                </div>
            </div>
        )
    }
}

export default MemeGenerator
    
\\\\





## Log 14

### Day 14: [16th June 2020]

Todays progress: None, one of those bad days when you just cant focus, so, I am just gonna stare at my project for ten minutes and re do it tomorrow





## Log 15

### Day 15: [17th June 2020]

**Today's Progress: I am continuing with my meme generator project now- today, I decided to reconstruct the project on my codepen file and arrange all the instructions for the project in one place here, so that later when I refer back to this project, it is much easier for me to remember, so, it is like a revision or revisiting the project from scratch: 

All the tasks from the beginning of the project here:
STEP 1:
**
 * Create the boilerplate to get React to render something on the screen
 * Render an <App /> component, which you'll need to create separately
 */
 
 
 STEP 2:
 
 /**
 * Create 2 new components - Header and MemeGenerator
 * Header will only display things
 * MemeGenerator will be calling to an API and holding on to data
 * Each should be in their own file of the same name
 */

STEP 3:

/**
 * Initialize state to save the following data:
 *      top text
 *      bottom text
 *      random image (intialize with "http://i.imgflip.com/1bij.jpg")
 */


STEP 4:

/**
     * We'll be using an API that provides a bunch of meme images.
     * 
     * Your task:
     * make an API call to "https://api.imgflip.com/get_memes" and save the 
     * data that comes back (`response.data.memes`) to a new state property
     * called `allMemeImgs`. (The data that comes back is an array)
     */
    
    
    STEP 5:
    
    /**
    * Create 2 input fields, one for the topText and one for the bottomText
    * Remember that these will be "controlled forms", so make sure to add
    * all the attributes you'll need for that to work
    */
    
        
    STEP 6:
    
        /**
    * Create the onChagne handler method
    * It should update the corresponding state on every change of the input box
    */
    
    
    STEP 7:
    
        /**
     * Create a method that, when the "Gen" button is clicked, chooses one of the
     * memes from our `allMemeImgs` array at random and makes it so that is the
     * meme image that shows up in the bottom portion of our meme generator site
     */
     
     
     STEP 8:
     
     // get a random int (index in the array)
        // get the meme from that index
        // set `randomImg` to the `.url` of the random item I gra
    
    
    **Thoughts:*Hope, by the end of this challenge, I am slowly becoming a React somebody*
    
    Complete code source for the above task for my codepen file:
    
    The html file:<div id="root"></div>
    
    The css file:
    
    * {
    box-sizing: border-box;
}

body {
    margin: 0;
    background-color: whitesmoke;
}

header {
    height: 100px;
    display: flex;
    align-items: center;
    background: #6441A5;  /* fallback for old browsers */
    background: -webkit-linear-gradient(to right, #2a0845, #6441A5);  /* Chrome 10-25, Safari 5.1-6 */
    background: linear-gradient(to right, #2a0845, #6441A5); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}

header > img {
    height: 80%;
    margin-left: 10%;
}

header > p {
    font-family: VT323, monospace;
    color: whitesmoke;
    font-size: 50px;
    margin-left: 60px;
}

.meme {
    position: relative;
    width: 90%;
    margin: auto;
}

.meme > img {
    width: 100%;
}

.meme > h2 {
    position: absolute;
    width: 80%;
    text-align: center;
    left: 50%;
    transform: translateX(-50%);
    margin: 15px 0;
    padding: 0 5px;
    font-family: impact, sans-serif;
    font-size: 2em;
    text-transform: uppercase;
    color: white;
    letter-spacing: 1px;
    text-shadow:
        2px 2px 0 #000,
        -2px -2px 0 #000,
        2px -2px 0 #000,
        -2px 2px 0 #000,
        0 2px 0 #000,
        2px 0 0 #000,
        0 -2px 0 #000,
        -2px 0 0 #000,
        2px 2px 5px #000;
}

.meme > .bottom {
    bottom: 0;
}

.meme > .top {
    top: 0;
}

.meme-form {
    width: 90%;
    margin: 20px auto;
    display: flex;
    justify-content: space-between;
}

.meme-form > input {
    width: 45%;
    height: 40px;
}

.meme-form > button {
    border: none;
    font-family: VT323, monospace;
    font-size: 25px;
    letter-spacing: 1.5px;
    color: white;
    background: #6441A5;
}

.meme-form > input::-webkit-input-placeholder { /* Chrome/Opera/Safari */
  font-family: VT323, monospace;
  font-size: 25px;
  text-align: cen
}
.meme-form > input::-moz-placeholder { /* Firefox 19+ */
  font-family: VT323, monospace;
  font-size: 25px;
  text-align: cen
}
.meme-form > input:-ms-input-placeholder { /* IE 10+ */
  font-family: VT323, monospace;
  font-size: 25px;
  text-align: cen
}
.meme-form > input:-moz-placeholder { /* Firefox 18- */
  font-family: VT323, monospace;
  font-size: 25px;
  text-align: cen
}
    
    The javascript file:
    
    function Header() {
    return (
        <header>
            <img 
                src="http://www.pngall.com/wp-content/uploads/2016/05/Trollface.png" 
                alt="Problem?"
            />
            <p>Meme Generator</p>
        </header>
    )
}


class MemeGenerator extends React.Component {
    constructor() {
        super()
        this.state = {
            topText: "",
            bottomText: "",
            randomImg: "http://i.imgflip.com/1bij.jpg",
            allMemeImgs: []
        }
        this.handleChange = this.handleChange.bind(this)
        this.handleSubmit = this.handleSubmit.bind(this)
    }
    
    componentDidMount() {
        fetch("https://api.imgflip.com/get_memes")
            .then(response => response.json())
            .then(response => {
                const {memes} = response.data
                this.setState({ allMemeImgs: memes })
            })
    }
    
    handleChange(event) {
        const {name, value} = event.target
        this.setState({ [name]: value })
    }
    
    handleSubmit(event) {
        event.preventDefault()
        const randNum = Math.floor(Math.random() * this.state.allMemeImgs.length)
        const randMemeImg = this.state.allMemeImgs[randNum].url
        this.setState({ randomImg: randMemeImg })
    }
    
    render() {
        return (
            <div>
                <form className="meme-form" onSubmit={this.handleSubmit}>
                    <input 
                        type="text"
                        name="topText"
                        placeholder="Top Text"
                        value={this.state.topText}
                        onChange={this.handleChange}
                    /> 
                    <input 
                        type="text"
                        name="bottomText"
                        placeholder="Bottom Text"
                        value={this.state.bottomText}
                        onChange={this.handleChange}
                    /> 
                
                    <button>Gen</button>
                </form>
                <div className="meme">
                    <img src={this.state.randomImg} alt="" />
                    <h2 className="top">{this.state.topText}</h2>
                    <h2 className="bottom">{this.state.bottomText}</h2>
                </div>
            </div>
        )
    }
}



function App() {
    return (
        <div>
            <Header />
            <MemeGenerator />
        </div>
    )
}



ReactDOM.render(<App />, document.getElementById("root"))
    
    

**Link to work:*This is my codepen link to my codepen file with the above code that I learnt from Bob Ziroll, Scrimba React.j. Here is the link : [*https://codepen.io/meeramenon07/pen/bGEpYXQ*]





## Log 16

### Day 16: [18th June 2020]

**Today's Progress: I am playing around with my code with my meme generator project now- today, I decided to reconstruct the project on my codepen file and arrange all the instructions for the project in one place here, so that later when I refer back to this project, it is much easier for me to remember, so, it is like a revision or revisiting the project from scratch: Here is the revised project with some changes in the css and some changes with the api and images 

**Link to work:*This is my codepen link to my codepen file with the above code that I learnt from Bob Ziroll, Scrimba React.j. Here is the link : [*https://codepen.io/meeramenon07/full/XWXNmpq*]


    
    
    
 ## Log 17

### Day 17: [19th June 2020]

**Today's Progress: I learnt how to write some code in modern React**

**Thoughts:*Hope, by the end of this challenge, I become a React expert as I love React but sometimes I find it intimidating to do without googling, hehe*

This is the general standard of using class based functions in React :

import React, {Component} from "react"

class App extends Component {
    // Change to use class properties
    constructor() {
        super()
        this.state = {
            firstName: ""
        }
        this.handleChange = this.handleChange.bind(this)
    }
    
    // Change to use arrow functions
    handleChange(event) {
        const { name, value } = event.target
        this.setState({
            [name]: value
        })
    }
    
    render() {
        return (
            <main>
                <form>
                    <input 
                        type="text"
                        name="firstName" 
                        value={this.state.firstName} 
                        onChange={this.handleChange} 
                        placeholder="First Name"
                    />
                </form>
                <h1>{this.state.firstName}</h1>
            </main>
        )
    }
}

export default App

AND SOME CHANGES IN MODERN REACT AS MENTIONED BELOW


/**
 * Other modern/advanced React features/topics to learn:
 * 
 * Official React Context API - https://reactjs.org/docs/context.html
 * Error Boundaries - https://reactjs.org/docs/error-boundaries.html
 * render props - https://reactjs.org/docs/render-props.html
 * Higher Order Components - https://reactjs.org/docs/higher-order-components.html
 * React Router - https://reacttraining.com/react-router/core/guides/philosophy
 * React Hooks - https://reactjs.org/docs/hooks-intro.html
 * React lazy, memo, and Suspense - https://reactjs.org/blog/2018/10/23/react-v-16-6.html
 */
 
 
 After changes , the modern React code would like this to replace the above code:
 
 import React, {Component} from "react"

class App extends Component {
    // Change to use class properties
    state = { firstName: "" }
    
    // Change to use arrow functions
    handleChange = (event) => {
        const { name, value } = event.target
        this.setState({
            [name]: value
        })
    }
    
    render() {
        return (
            <main>
                <form>
                    <input 
                        type="text"
                        name="firstName" 
                        value={this.state.firstName} 
                        onChange={this.handleChange} 
                        placeholder="First Name"
                    />
                </form>
                <h1>{this.state.firstName}</h1>
            </main>
        )
    }
}

export default App

 
 
 

**Link to work:*This is my codepen link to my practice session on React Form, very basic and just a practice stuff based on what I am learning on scrimba. Here is the link : https://codepen.io/meeramenon07/pen/YzymZrQ*

 




## Log 18

### Day 18: [20th June 2020]

**Today's Progress: In my scrimba lesson, I learnt introduction to React Hooks and about useState()**

**Thoughts:*React Hooks is pretty easier and more convenient to do than React, by doing away with lots of the conventional coding steps, hehe*

For example, the usual norm of code for React in this simple App using class based App:

class App extends React.Component {
//     constructor() {
//         super()
//         this.state = {
//             answer: "Yes"
//         }
//     }
    
//     render() {
//         return (
//             <div>
//                 <h1>Is state important to know? {this.state.answer}</h1>
//             </div>
//         )
//     }
// }

export default App

The above code will be replaced by the following code for React Hooks:

import React, {useState} from "react"

function App() {
    const [answer] = useState("Yes")
    return (
        <div>
            <h1>Is state important to know? {answer}</h1>
        </div>
    )
}





## Log 19

### Day 19: [22nd June 2020]

**Today's Progress: In my scrimba lesson, I learnt more about  React Hooks and about useState()**

**Thoughts:*React Hooks is pretty easier and more convenient to do than React, by doing away with lots of the conventional coding steps, hehe*

The code here for setting count display on the screen using scrimba:

import React, {useState} from "react"

// Convert the class below to a functional component that uses the useState hook to initalize a count vartiable to 0 and display the count on the screen.
// Don't worry about the part where the button changes the count quite yet, that's what you're here to learn about!

function App() {
    const [count, setCount] = useState(0)
    const [answer, setAnswer] = useState("Yes")
    
    function increment() {
        setCount(prevCount => prevCount + 1)
    }
    
    function decrement() {
        setCount(prevCount => prevCount - 1)
    }
    
    return (
        <div>
            <h1>{count}</h1>
            <button onClick={increment}>Increment</button>
            <button onClick={decrement}>Decrement</button>
        </div>
    )
}

// class App extends React.Component {
//     constructor() {
//         super()
//         this.state = {
//             count: 0,
//             answer: "Yes"
//         }
//     }
    
//     render() {
//         return (
//             <div>
//                 <h1>{this.state.count}</h1>
//                 <button>Change!</button>
//             </div>
//         )
//     }
// }

export default App

index.js

import React from "react"
import ReactDOM from "react-dom"

import App from "./App"

ReactDOM.render(<App />, document.getElementById("root"))





## Log 20

### Day 20: [23nd June 2020]

**Today's Progress: In my scrimba lesson, I learnt more about  React Hooks and about useEffect()
**

**Thoughts:*React Hooks is pretty easier and more convenient to do than React, by doing away with lots of the conventional coding steps, hehe*


The code :

import React, {useEffect, useState} from "react"

import randomcolor from "randomcolor"


function App(){
  const [count, setCount] = useState(0)
  const[color, setColor] = useState("")
  
  function increment(){
    setCount(prevCount => prevCount + 1 )
  }
  
  function decrement(){
    setCount(prevCount => prevCount - 1) 
  }
  
  useEffect(() => {
     setColor(randomcolor())
  
  }, [count])
  
  return(
  <div>
    <h1 style={{color: color}}>{count}</h1>
    <button onClick={increment}>Increment</button>
    <button onClick={decrement}>Decrement</button>

  </div>
  )
  
}

index.js

import React from "react"
import ReactDOM from "react-dom"

import App from "./App"

ReactDOM.render(<App />, document.getElementById("root"))


css

div {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

h1 {
    font-size: 3em;
}

button {
    border: 1px solid lightgray;
    background-color: transparent;
    padding: 10px;
    border-radius: 4px;   
}

button:hover {
    cursor: pointer;
}

button:focus {
    outline:0;
}






## Log 21

### Day 21: [24th June 2020]

**Today's Progress: In my scrimba lesson, I learnt more about  React Hooks and about useEffect()
**

**Thoughts:*React Hooks is pretty easier and more convenient to do than React, by doing away with lots of the conventional coding steps, hehe*


The code :

App.js
import React, {useState, useEffect} from "react"
import randomcolor from "randomcolor"

function App() {
    const [count, setCount] = useState(0)
    const [color, setColor] = useState("")
    
    useEffect(() => {
        const intervalId = setInterval(() => {
            // setCount(prevCount => prevCount + 1)
        }, 1000)
        return () => clearInterval(intervalId)
    }, [])
    
    useEffect(() => {
        setColor(randomcolor())
    }, [count])
    
    return (
        <div>
            <h1 style={{color: color}}>{count}</h1>
        </div>
    )
}

export default App



## Log 22

### Day 22: [25th June 2020]

**Today's Progress: In my scrimba lesson, I learnt more about  React Hooks and Project ideas for practice:
https://medium.freecodecamp.org/every-time-you-build-a-to-do-list-app-a-puppy-dies-505b54637a5d

https://medium.freecodecamp.org/want-to-build-something-fun-heres-a-list-of-sample-web-app-ideas-b991bce0ed9a

https://medium.freecodecamp.org/summer-is-over-you-should-be-coding-heres-yet-another-list-of-exciting-ideas-to-build-a95d7704d36d


**

**Thoughts:*Finally i concluded all the lessons of React in scrimba. Learnt about state, functionand  class methods, and props for passing state between parents and child, JSX, and css styling for react apps, making a to do list, making a form in react, conditional rendering in React and introduction to React Hooks. Going to practise some more projects in React from above links of freecodecamp *


## Log 23

### Day 23: [26th June 2020]

**Today's Progress: As: part of my quest to get more expertise with React, I have just started doing the last React project from the Frond end libraries projects in FreeCodeCamp.org certification projects: BUILD A POMODORO CLOCK

THE PROJECT TASK DESCRIPTION IS AS FOLLOWS:-

Front End Libraries Projects - Build a Pomodoro Clock
Objective: Build a CodePen.io app that is functionally similar to this: https://codepen.io/freeCodeCamp/full/XpKrrW.

Fulfill the below user stories and get all of the tests to pass. Give it your own personal style.

You can use any mix of HTML, JavaScript, CSS, Bootstrap, SASS, React, Redux, and jQuery to complete this project. You should use a frontend framework (like React for example) because this section is about learning frontend frameworks. Additional technologies not listed above are not recommended and using them is at your own risk. We are looking at supporting other frontend frameworks like Angular and Vue, but they are not currently supported. We will accept and try to fix all issue reports that use the suggested technology stack for this project. Happy coding!

User Story #1: I can see an element with id="break-label" that contains a string (e.g. "Break Length").

User Story #2: I can see an element with id="session-label" that contains a string (e.g. "Session Length").

User Story #3: I can see two clickable elements with corresponding IDs: id="break-decrement" and id="session-decrement".

User Story #4: I can see two clickable elements with corresponding IDs: id="break-increment" and id="session-increment".

User Story #5: I can see an element with a corresponding id="break-length", which by default (on load) displays a value of 5.

User Story #6: I can see an element with a corresponding id="session-length", which by default displays a value of 25.

User Story #7: I can see an element with a corresponding id="timer-label", that contains a string indicating a session is initialized (e.g. "Session").

User Story #8: I can see an element with corresponding id="time-left". NOTE: Paused or running, the value in this field should always be displayed in mm:ss format (i.e. 25:00).

User Story #9: I can see a clickable element with a corresponding id="start_stop".

User Story #10: I can see a clickable element with a corresponding id="reset".

User Story #11: When I click the element with the id of reset, any running timer should be stopped, the value within id="break-length" should return to 5, the value within id="session-length" should return to 25, and the element with id="time-left" should reset to it's default state.

User Story #12: When I click the element with the id of break-decrement, the value within id="break-length" decrements by a value of 1, and I can see the updated value.

User Story #13: When I click the element with the id of break-increment, the value within id="break-length" increments by a value of 1, and I can see the updated value.

User Story #14: When I click the element with the id of session-decrement, the value within id="session-length" decrements by a value of 1, and I can see the updated value.

User Story #15: When I click the element with the id of session-increment, the value within id="session-length" increments by a value of 1, and I can see the updated value.

User Story #16: I should not be able to set a session or break length to <= 0.

User Story #17: I should not be able to set a session or break length to > 60.

User Story #18: When I first click the element with id="start_stop", the timer should begin running from the value currently displayed in id="session-length", even if the value has been incremented or decremented from the original value of 25.

User Story #19: If the timer is running, the element with the id of time-left should display the remaining time in mm:ss format (decrementing by a value of 1 and updating the display every 1000ms).

User Story #20: If the timer is running and I click the element with id="start_stop", the countdown should pause.

User Story #21: If the timer is paused and I click the element with id="start_stop", the countdown should resume running from the point at which it was paused.

User Story #22: When a session countdown reaches zero (NOTE: timer MUST reach 00:00), and a new countdown begins, the element with the id of timer-label should display a string indicating a break has begun.

User Story #23: When a session countdown reaches zero (NOTE: timer MUST reach 00:00), a new break countdown should begin, counting down from the value currently displayed in the id="break-length" element.

User Story #24: When a break countdown reaches zero (NOTE: timer MUST reach 00:00), and a new countdown begins, the element with the id of timer-label should display a string indicating a session has begun.

User Story #25: When a break countdown reaches zero (NOTE: timer MUST reach 00:00), a new session countdown should begin, counting down from the value currently displayed in the id="session-length" element.

User Story #26: When a countdown reaches zero (NOTE: timer MUST reach 00:00), a sound indicating that time is up should play. This should utilize an HTML5 audio tag and have a corresponding id="beep".

User Story #27: The audio element with id="beep" must be 1 second or longer.

User Story #28: The audio element with id of beep must stop playing and be rewound to the beginning when the element with the id of reset is clicked.

You can build your project by forking this CodePen pen. Or you can use this CDN link to run the tests in any environment you like: https://cdn.freecodecamp.org/testable-projects-fcc/v1/bundle.js

Once you're done, submit the URL to your working project with all its tests passing.






## Log 24

### Day 24: [27th June 2020]

**Today's Progress: As: part of my quest to get more expertise with React, I have just started doing the last React project from the Frond end libraries projects in FreeCodeCamp.org certification projects: BUILD A POMODORO CLOCK
I only attempted 4 tasks out of the 29 tasks mentioned above and I passed the first 4 tests! CONGRATULATIONS TO ME :-)

The 4 tasks are :

User Story #1: I can see an element with id="break-label" that contains a string (e.g. "Break Length").

User Story #2: I can see an element with id="session-label" that contains a string (e.g. "Session Length").

User Story #3: I can see two clickable elements with corresponding IDs: id="break-decrement" and id="session-decrement".

User Story #4: I can see two clickable elements with corresponding IDs: id="break-increment" and id="session-increment".


The code for the first 4 tests
for html file:
<div id="root"></div>

for javascript react file
function App(){
  return(
   <div className = "App">
      <p id="break-label">Break </p>
      <p id="session-label">Session Length</p>
      <button onClick id="break-decrement">Break Decrement</button>
      <button onClick id="session-decrement">Session Decrement</button>
      <button onClick id="break-increment">Break Increment</button>
      <button onClick id="session-increment">Session Increment</button>
   </div>    
      
   
  );
}








## Log 25

### Day 25: [28th June 2020- 29th June 2020]

**Today's Progress: As: part of my quest to get more expertise with React, I have just started doing the last front-end project from the Frond end libraries projects in 
fcc and I am badly stuck. Perhaps I should try doing it in jquery instead of React??






## Log 26

### Day 26: [30th June 2020]

**Today's Progress: I did lots and lots of research and digging into react tutorials and practised some more code in react components and props and now, I could figure out where I went wrong. I managed to pass the first 4 tests again and corrected my app code to start with and here is the starter code


function App(){
  return(
    <div className = "App">
       <section id="break-label">Break Length</section>
         <p id="session-label">Session Length</p>
         <button onClick id="break-decrement">Break Decrement</button>
         <button onClick id="session-decrement">Session Decrement</button>
         <button onClick id="break-increment">Break Increment</button>
         <button onClick id="session-increment">Session Increment</button>
        
      
    </div>
  )
}




## Log 27

### Day 27: [2nd June 2020]

I skipped yesterday...oops

I am stuck at one point and still trying to continue with the project...All the best to me ...

Progress: no progress yet




## Log 28

### Day 28: [4th June 2020]

Today's progress: I could not code for two days as my computer internet was down. But today, I achieved a lot by passing 11 tests out of the total 29 tests for the project, Congratulations to me as I am now on the right track,,,,,

The code in progress


function Length(){
  return(
    <div id = "length-controller">
      <h2 id ="break-label">Break Length</h2>
      <h2><span id ="session-label">Session Length</span></h2>
      
    </div>
  )
}
  


class App extends React.Component{
  constructor(props){
    super(props)
    this.state ={
      BreakLength : 5,
      SessionLength: 25,
      Paused:0,
      Running:0,
    }
  }
  render(){
    return(
    <div>
      <section id = "length-controller">
      <h2 id ="break-label">Break Length</h2>
      <button id = "break-decrement"> - </button>
      <button id = "break-increment"> + </button>
        <p id = "break-length"> 5 </p>
      <h2 id ="session-label">Session Length</h2>
      <button id = "session-decrement"> - </button>
      <button id = "session-increment"> + </button>
        <p id ="session-length"> 25 </p>
      </section>
      <section id = "session">
        <h2 id = "timer-label"> Session </h2>
        <p id ="time-left">Time</p>
        
                          
      </section>
      <section id = "controls">
        <button id ="start_stop"></button>
        <button id="pause"></button>
        <button id = "reset"></button>
        <figure>
          <figcaption>Beep sound:</figcaption>
          <audio
          controls
          id = "beep"
          src="/media/examples/t-rex-roar.mp3">
            Beep sound
            <code>audio</code> element.
          </audio>
        </figure>
       
      </section>
     
    </div>
  
  )
  }
  
  
}
ReactDOM.render(<App/>, document.getElementById("root"));






## Log 29

### Day 30: [6th June 2020]

Today's progress: I could not code for two days as my computer internet was down. But today, I achieved a lot by passing 11 tests out of the total 29 tests for the project, Congratulations to me as I am now on the right track,,,,,Not yet able to pass the other tests yet...







## Log 30

### Day 31: [7th June 2020]

Today's progress: I have completed 50% of my pomodoro clock project, should be able to finish it soon ...




## Log 31

### Day 32: [8th June 2020]

Today's progress: I have completed 70% of my pomodoro clock project, should be able to finish it soon ...





## Log 32

### Day 33: [9th June 2020]

Today's progress: I have completed my javascript react file and now doing the styling sheet of my pomodoro clock project, should be able to finish it within a day or two!! ...







## Log 33

### Day 34: [10th June 2020]

Today's progress: I have completed my javascript react file and now doing the styling sheet of my pomodoro clock project, should be able to finish it within a day or two!! ...





##Log 14
### Day 35: [11th June 2020]
Today's progress: I finished my React app project but not yet made it responsive, will add in the media queries tomorrow.
For today, I will call it a day...phew!

