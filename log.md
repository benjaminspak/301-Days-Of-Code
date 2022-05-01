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
### Day 35: [11th July 2020]
Today's progress: I finished my React app project but not yet made it responsive, will add in the media queries tomorrow.
For today, I will call it a day...phew!

##Log 15
### Day 36: [12th July 2020]
sorry for typo mistake earlier, this is july month running and not june...
Today's progress: I was supposed to add the responsiveness to my project but could not do so as I am unable to open my codepen file today, some error in codepen server apparently, hope, it will be up by tomorrow!!!




##Log 16
### Day 37: [13th July 2020]

Today's progress: I finished the project and passed all the tests in the project tasks for making the Pomodoro clock.

Link to my work: https://codepen.io/meeramenon07/pen/zYrzgpp




##Log 17
### Day 38: [14th July 2020]

Today's progress: I am planning to do more JavaScript projects and React projects and also revise on lessons from React and JavaScript while doing the challenges. Signed up for one more free lesson in React from Scrimba to make a React project. The project is Build a Movie Search App in React. Just started researching and doing lessons today to get more inspiration for this project!

##Log 18
### Day 39: [15th July 2020-16th July 2020 ]

Today's progress: Signed up with a movie database to get a new API link for creating the movie search app Doing some research and also taking tutorials to get help for this project




## Log 40
### Day 40 : [16th July -17th July 2020]

Today's progress: I love this Search Movie React app project tutorial. Scrimba tutorial is so practical oriented, just love it. In order to remember and grasp on a long term basis, I always type out my code and also write down my code and this makes it so much easier to understand and also remember. Today, I made the function class for this app. 
Tomorrow, I will continue with it to make the next component for this project.




## Log 41
### Day 41 : [18th July 2020]

Today's progress: I learnt React Hooks- How to manage state with useState() and how to add api for search query and also how to catch errors .

Tomorrow, I will continue .
The code for searchMovies.js

import React, {useState} from "react";

export default function SearchMovies(){
    
    //states- input query, movies
    const [query, setQuery] = useState('');
    //create the state for movies, and update that state appropriate
    const [movies, setMovies] = useState([]);
    
    const searchMovies = async (e) => {
        e.preventDefault();
                
        const url = `https://api.themoviedb.org/3/search/movie?api_key=5dcf7f28a88be0edc01bbbde06f024ab&language=en-US&query=${query}&page=1&include_adult=false`;
        
        try {
            const res = await fetch(url);
            const data  = await res.json();
            setMovies(data.results);
        }catch(err){
            console.error(err);
        }
    }




    
    return (
        <>
            <form className="form" onSubmit={searchMovies}>
                <label className="label" htmlFor="query">Movie Name</label>
                <input className="input" type="text" name="query"
                    placeholder="i.e. Jurassic Park"
                    value={query} onChange={(e) => setQuery(e.target.value)}
                    />
                <button className="button" type="submit">Search</button>
            </form>
            <div className="card-list">
                {movies.filter(movie => movie.poster_path).map(movie => (
                    <div className="card" key={movie.id}>
                        <img className="card--image"
                            src={`https://image.tmdb.org/t/p/w185_and_h278_bestv2/${movie.poster_path}`}
                            alt={movie.title + ' poster'}
                            />
                        <div className="card--content">
                        <h3 
                        
                        
                        
                        className="card--title">{movie.title}</h3>
                        <p><small>RELEASE DATE: {movie.release_date}</small></p>
                        <p><small>RATING: {movie.vote_average}</small></p>
                        <p className="card--desc">{movie.overview}</p>
                        </div>

                    </div>
                ))}
            </div>    
        </>
    )


}






## Log 42
### Day 42 : [19th July 2020]

Today's progress: Leant how to make the movie display information. Will do the styling tomorrow.



## log 43
### Day 43 : [20th July 2020]

Today's progress- Finished the movie search app tutorial. Tomorrow, I am going to try doing the same app in my codepen file 





## Log 44
### Day 44: [21st July 2020]

Today's progress: Today, I want to try out the new feature of github profiles and decided to include my tutorial videos as well in my coding challenges, so, here is one of the tutorials that I published on youtube today: This is to teach about lastIndexOf in javascript strings. Here is the link:
<iframe width="560" height="315" src="https://www.youtube.com/embed/vNbUZQ_19jg" frameborder="0" allow="accelerometer; autoplay=0; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>



## Log 45
### Day 45: [22nd July 2020]

Today's progress: I realised that I am getting stuck at different points of the project since and so, I decided to research and find out what are the core concepts of making a search app and thanks to a simple explanation in a blog by Gideon Bamuleseyo, I was able to grasp where I went wrong in the first place and now, it is so crystal clear to me. So, today, I just spent fiddling around with some search apps and now, I am ready to do the  search app projects in React.




## Log 46
### Day 46: [23rd July -24th July 2020]

Today's progress: I skipped yesterday since it was my moms birthday, and had lots of chores to do and no time to sit. Today, I finished my app for meal search , with the help of some googling and blog lessons and here is the link to it on my codepen file
: [https://codepen.io/meeramenon07/full/GRozbBJ]





## Log 47
### Day 47:[25th july 2020]
Today's progress: I am revising my code today,writing down in pen on paper improves my muscle memory and thats what I did today and then, also typed on my computer into my codepen file and here is the pen link .
`https://codepen.io/meeramenon07/pen/GRozbBJ`



## Log 48
### Day 48: [26th July 2020]
Today, I am just going to read some more advanced concepts on props, and api for creating more react projects. I found some great concepts on w3 schools . It is so strange that after making some projects in React and going through advanced blogs and tutorials, I was still getting stuck at some point or the other while creating projects but these lessons on w3 schools on React props are so well explained, that I decided to read them for today and tomorrow before diving into more React projects next week.


## Log 49
### Day 49 : [27th July 2020]

Today, I am continuing to research and read up the concepts on react forms and props and I am really getting into react


## Log 50
### Day 50 : [29th July 2020]

Today's progress: I am practising to write down each and every code syntaxes in React so that I will not be confused while write code for react projects.



## Log 51
### Day 51: [30th July 2020]
Todays progress: Today, instead of coding for my projects, I decided to update my github readme profile markdown and my profile really looks nice after using up this new readme profile feature. Thanks to github guys for doing this for us.

Here is my profile after update :
[github readme profile](https://github.com/meeramenon07)

`https://github.com/meeramenon07`



## Log 52
### Day 52: [31st July 2020]

Today's progress: I am just going to play around with practise codes for props and components from a nice blog called golang.com I will practise these small snippets for two days after which I am going to start doing some serious projects in React.

One of the code snippets for creating stateful functin in react for addressing user name is as follows

```
class Message extends React.Component{
  state ={
   user: 'Meera Menon'
  }
  render(){
    return(
      <h1>Hello {this.state.user}</h1>
    );
  }
} 

ReactDOM.render(<Message />, document.getElementById("root");

```


```
function Vehicles(){
 const car = "Fiat";
 const specifications = {
  length:4000,
  width:3000,
  height:1500
 
 }
 const getDimensions = specifications =>(
   `${car.length}(mm) ${car.width}(mm) ${car.height}(mm)`
 
 );
 
 
  return(
   <div>
   <h1>{car}</h1>
   <p>{getDimensions(specifications)}</p>
   
   </div>
  
  );
}

ReactDOM.render(<Vehicles />, document.getElementById("root");

```




## Log 53
### Day 53: [01st August 2020]
Today's progress: Today, I am continuing with writing down some syntaxes for jsx in React
The code that I practised writing down as follows for stateless functions in React:

```
function Vehicles(){
  const price = 7000;
    if (price < 7000){
      return <div>Car Price: {price + price*0.05}</div>
    }else{
      return<div>Car Price: {price + price*0.15}</div>
    }
  
  return(
    <div><h1>{price}</h1></div>
  );
}
ReactDOM.render(<Vehicles />, document.getElementById("root"));



```


Jsx using javascaript mapping to use in stateless function in React:

```

function Automobiles(){


 const cars = ["Mercedes", "Fiat", "Toyota", "Ambassador", "Ford"];
 
 const carList = cars.map( (car) =>
      <li key = {car.toString()}>{cars}</li>
 
 );
 
  return (<ul> <h1>{carList}</h1></ul>);
  
  
  

}
ReactDOM.render(<Automobiles />, document.getElementById("root");


```

Thought of the day: Practise is perfection


Links to the code:
[codepen]{https://codepen.io/meeramenon07/pen/RwrXLpP}

[codepen]{https://codepen.io/meeramenon07/pen/ExPqwEM}





## Log 54
### Day 54: [02nd August 2020]

*Today's progress*: Today I am still continuing with React syntax code practising by keying it down in my codepen files. The following is the relation between parent and child props in stateless react function
```
function Parent(){
  return(
   <Child name="mike" english="90" hindi="100"/>
  )
}

function Child(props){
  return(
  <div>  
   <h1>{props.name}</h1>
   <ul>
     <li>{props.english}</li>
     <li>{props.hindi}</li>
   </ul>
  </div>    
  )
} 

ReactDOM.render(<Parent />, document.getElementById("root"));
```





## Log 55
### Day 55: [03rd August 2020]

*Today's progress*: I am watching a video tutorial on the making of a shopping cart in havascript and also React and this will give me the importance of using React over plain vanilla javascript in doing complex projects,

video link:
[YouTube](https://www.youtube.com/watch?v=LDKnz5gwdz4&feature=youtu.be  "JavaScript / React Shopping Cart - Using Vanilla JavaScript and then using React [Project] [2020]
")
I will continue watching this long tutorial tomorrow





## Log 56 
### Day 56 : [04th August 2020]

Today's progress: after watching the tutorials, I am practising some more codes on my codepen 

using for loop, checking out parent and child components and passing props 

code below
```
//parent component

function App(){
   
    return <Student  name="George Van" marks={[45,43,67,70,80,90,70]}/>;
      
    
}

//child components
//USING for loop
function markList(marks){
  let arrayItems = [];
  for(let i = 0; i < marks.length; i++){
     arrayItems.push(<li>{`${marks[i]}`}</li>);
    
  }
  return arrayItems;
}

function Student(props){
  return(<ul>{markList(props.marks)}</ul>)
}

ReactDOM.render(<App />, document.getElementById("root"));


```

[codepen](https://codepen.io/meeramenon07/pen/mdPborO) 


Thoughts of the day getting there somehow hopefully







## Log 57 
### Day 57 : [05th August 2020]

*Today's progress: Continuing with coding practice. Now, I am practising props ....below is a pen where I am rendering an array in child component using the map method 

```
function App(){
  return Student  name="Mike"  marks={[70,40,50,60,30]}/>;
}

function Student(props){
  return 
  <ul>
  {props.marks.map(mark =>(
  <li>{ `${mark}` }</li>
  ))}
  
  </ul>
  );

}

ReactDOM.render(<App />, document.getElementById("root");


Rendering unknown content in react

// parent component

function App(){
return(
<div>
<Student name="Mike">
<p>Mike is a student studying in some school or college.</p>
</Student>
</div>
);
}


//child component

function Student(props){
 return(
 <h1>{props.name}</h1>
 <p>{props.children}</p>
 );
}

ReactDOM.render(<App />, document.getElementById("root"));

```






## Log 58 
### Day 58 : [06th August 2020]

*Today's progress:

practised following :

Using React -using function props

```
var names = ["John", "Alice", "Mark"];
function userName(name) {
  
  names = names.filter(item => item !== name)
  
}
//The function defined as userName, uses the JavaScript method to remove the item from array. The userName function is provided to the Student component as the value for a prop named userCallback. The onClick expression is a fat arrow function that calls the function prop when it is invoked.

//parent component

function App() {
  return (
    <ul>
      {names.map((name, index) => (
        <li key={name}>
          <Student index={index} name={name} userCallback={userName} />
        </li>
      ))}
    </ul>
  );
}

//child component
function Student(props) {
  return (
    <div>
      <span>{props.name}</span>
      <span>
        <button onClick={() => props.userCallback(props.name)}>
          Click Here
        </button>
      </span>
    </div>
  );
}


ReactDOM.render(<App />, document.getElementById("root"));

```


PASSING PROPS WITH SPREAD IN REACT

```
//Parent component
function App() {
  return (
    <div>
      <Student name="Mathew" physics="45" chemistry="49" biology="53" />
      <Student name="John" physics="75" chemistry="71" biology="78" />
      <Student name="Robin" physics="95" chemistry="91" biology="88" />
    </div>
  );
}

//Child component-first level child

function Student(props){
  return(
    <div>
      <h1>{props.name}</h1>
      <p><Marks {...props} /></p>
      
    </div>
  
  );
}

//child component- second level child
//The {...props} expression passes on all of the props received from the parent component.


function Marks(props){
  return(
    <div>
      <ul>
        <li>PHYSICS: {props.physics}</li>
        <li>CHEMISTRY: {props.chemistry}</li>
        <li>BIOLOGY: {props.biology}</li>
        
      </ul>
    </div>
  
  )
}


ReactDOM.render(<App />, document.getElementById("root"));

```


Thoughts of the day: ready to start my projects from tomorrow onwards, wish me luck in this React journey









## Log 59 
### Day 59 : [08th August 2020]
Skipped for two days as I was brushing up on my regex skills 

I revised regex - match method, and extracting an array with repeated words, I also revised the flags i and g where i is for ignoring ases and g is for extracting repeated words
I will give it a couple of days more to finish this revision before moving on to my react projects building.   ooops ....it is not just moving ahead...






## Log 60 
### Day 60 : [09th August 2020]

Today's progress : Continuing with my regex revision, learnt how to match letters, letters and number ranges, and also how to excluse a number and letter ranges.
After finishing all the regex revision lessons, I am going to document all the lessons and codes of regex on one log so that it is easier for me to retrieve later whenever I need them again.


## Log 61
### Day 61 :[12th August 2020]

Today's progress: Continuing with my regex journey. Learnt how to match numbers, non numbers, greedy, lazy ranges, and many more, there are still eight more topics to cover again for revision in regex and I should be able to finish in two days time after which I will log my regex journey in another repo or this repo, I am not yet sure as of now. I also want to revise my es6 but not sure if I should do that first or straight away proceed to react projects

Thoughts of the day = It is a very steep climb to reach my react journey peak, hehehe








#Log62
### Day 62: [13th August 2020]

Todays progress: Continuing with my Regex revision classes- revised on various types of quantifiers and Look arounds.



#Log 63 ###Day 63 : [Date:17th August 2020]
I took a three day break to learn and revise regex to do better in react finally finished my regex lessons today
Today's progress: Going to plan a project in react by tomorrow






#Log 64 ###Day 64 : [Date:18th August 2020]

Today, I started doing revision of my code for ES6, modern javascript since it is most important and vital for doing code in React projects, I should be able to finish my revision in ES6 in a week's time after which it will be much more easier for me to think in react








#Log 65 ###Day 65 : [Date:19th August 2020]

Today's progress: My es6 class begins
Topic 1 
Write arrow functions with parameters:
var myConcat = function(arr1,arr2){
  return arr1.concat(arr2);
}

changing the above function to an arrow function will look like this:

var myConcat = (arr1, arr2) => arr1.concat(arr2);
better practice to write const in place of var :
const myConcat = (arr1,arr2) => arr1.concat(arr2);
console.log(myConcat (([1.2],[3,4,5]));
//[1,2,3,4,5]


TOPIC 2: WRITING HIGHER ORDER ARROW FUNCTIONS

const realNumberArray = [4,5.6, -9.8, 3.14, 42, 6, 8.34, -2];

const squareList = (arr) => {
   const squaredIntegers = arr;
   return squaredIntegers;
};
const squaredIntegers = squareList(realNumberArray);
console.log(squaredIntegers);

after doing arrow function, it will look like this - while getting the result after filter and map of the numbers provided:

const squareList = (arr) => {
  const squaredIntegers = arr.filter(num => Number.isInteger(num) && num > 0).map( x  => x * x);
};

const squaredIntegers = squareList(realNumberArray);
console.log(squaredIntegers);




Topic 3 : use arrow functions to write concise anonymous functions
var magic = function() {
  return new Date();
};


after doing arrow function

const magic = () => newDate();







#Log 66 ###Day 66 : [Date:20th August 2020]s

##Today's topics:

-set default parameters for your functions
-use the rest operator with function parameters


Topic: set default parameters for your functions
const increment= (function() {
   return function increment(number,value=1
){
   return number + value;


};




})();

console.log(increment(5,2)); //7

console.log(increment(5));//6



Topic:use the rest operator with function parameters

const sum = (function(){
   return functin sum(x,y,z){
     const args = [x,y,z];
     return args.reduce( (a,b) => a + b, 0);
   
   
   };

})();
console.log(sum(1,2,3));

after using the rest operator, this looks like the following function


const sum = function(){
   return function sum(...args){
      return args.reduce((a,b) => a+b, 0);
   };

})();
console.log(sum(1,2,3,4));
now it is possible to check for more than three values in the console .log after using the rest operator.









#Log 67 ###Day 67 : [Date:21st August 2020]s
Today's topic- Spread operator es6

const arr1 = ['JAN', 'FEB', 'MAR', 'APR', 'MAY'];
let arr2;
(function() {
  arr2 = arr1; // change this line
  arr1[0] = 'potato'
})();
console.log(arr2);

//will show potato as the first element in the resultant array 

After using the spread operator:

const arr1 = ['JAN', 'FEB', 'MAR', 'APR', 'MAY'];
let arr2;
(function() {
  arr2 = [...arr1]; // change this line
  arr1[0] = 'potato'
})();
console.log(arr2);
//["JAN", "FEB", "MAR", "APR", "MAY"]







#Log 68 ###Day 68 : [Date:29th August 2020]s

I have started doing projects in React hooks
The first one is creating a quiz app in react hooks and I am working on it , hope to complete it within this week
