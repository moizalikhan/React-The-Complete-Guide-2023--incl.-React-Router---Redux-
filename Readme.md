### Webpack
* event-driven plugin-based compiler
* compilation-start → resolver → Module factory → Transpiler → parse(recur) →DependecyGraph →sort → bundle(merges) → Tree shaking and mimification → compilation-end
* loader work at the file level before the bundle is generated, plugin work at the chunk level after the bundle is generated
* webpacks combines your js files and build static assets for browser to run it optimaly.
* loaders and plugins
* environment setter
* "in Any web- application there a starting point and its a module which depends on other modules as depedency and they have other dependencies a module bundler takes this modules and generate a js file.
            * Dependecy Resolution untill it reach a dead end
            *  bundle them
            *  Loader/Transformer css through link tag
            *  map of modules as key and values
            *  webpack_require --> runtime
            *  concatenate modules
            *  the main feature of web pack is code splitting -- dynamic import
            *  Tree shaking, minification
            *  Fewer files need to be retrieved in order to load all modules.
            *  Compressing the bundled file is slightly more efficient than compressing separate files.
            *  During bundling, unused exports can be removed, potentially resulting in significant space savings.
            *  Solving the problem of cyclic dependencies
            *  Anchoring transpilation and pre-processing on Modules

### React Concepts
* Components Concept
* jsx is not understood by the browser it transformed to understand by the browser.
* render method injects the component into the root.
* first app then the component hiearchy
* jsx to Dom nodes
* Custom components are executed as functions and then it values analyzed and untill it ends up with only built in elements then rendered.
* built in components are rendered as dom nodes
* { } for dynamic data
* prop ---> forward data into components
* custom html attributes set on components and merge into single objects
* Every custom componenet receive props {props.children}
* may be we can use destructing 
* onclick built in prop
* components executed once then we have to tell to do it again know as state
* no regular variable handles state
* hooks usestate() only called in react component functions and on top level and it gives back a Array of two elements
* const [selectedTopic, setSelectedTopic(function)]
* when we call setSelectedTopic it schedules the stateupdate and it reexecutes it
* when updating state ()=>  means when your state depends on the old state then pass a function to the useeffect function
* Lifting the state up: ancestor component manages state value thats needed by both child 1 and child 2 via props
* props drilling
    * component composition: wrapper around a list of products
    * React context api --> createContext() gives us an object that has a react conponent <context.provider> 
    * UseContext hook
    * the default value set when creating the context  is only used if a component that was not wrapped by the provider component tries to access context value
    * <context.consumer>
    * {()}=>{} a extra wrapper
    * UseReducer --> one or more complex values to a simpler value for state management useReducer hook gives an array of 2 elements
    * const [state, DispatcherFunction] = useReducer(reducer function, {[]});
    * Reducerfunction(state, action){}

* React hooks:
  * stateful component
  * pure functions --> same output for input
  * sideeffect
  * stateless
  * stateful logic in an another function and that is hook
  * hook: a plain old js that has react specific things to manage state and side effects by that your component become stateless
  * no utility func because it has hook and it has some state advantages
  * Usestate() --> declare and track the state variables values of your component
  * Const [state, setstate] = useeffect(initial value)
  * lazily intialize
  * setcounter(prev)
  * operations that are not realed to input and output sideeffect
  *  Dom manipulation
  *  component rending logic and side effect logic must seprate out
  *  useefeect hook comes in hands when managing sideeffects
  *  useeffect takes (fucntion,Cleaning logic,Dependency array)
  * Virtual dom:
    * Dom Manipultion--> Dom update, ReREdnder
    * react never updated the original dom tree directly
    * virtual dom in memory copy of your vd
    * update the original dom partially
    * batch update
    * react keep the in memory VR of the actual dom and keep it sync with batch update is called recomsilation
    * diffing algo
    * root change and tear it down
    * attribute change
    * li is worse we use key value 
    * react memo--> memomiztion(cache)
    * if props change then memo will rendered
    * usecallback and usememo hook
    * js first class func
    * usecallback we get the function and in use memo it executes the function
    * function same and if dependedncy array
    * referntial equality object.is()
    * expensive redering
    * reusability and enhancing an attribute --> Higher order componenets
    * in react in hoc is just a pure react component as a arjument and return a new enhanced component
    * 

### Web hooks
A webhook is a mechanism that allows one system or application to send real-time data to another system or application as soon as an event occurs. Instead of one system constantly polling another for updates, the system that generates the events sends a notification to the system that needs to be informed. Webhooks are commonly used in web development and integration scenarios to enable seamless communication between different services.

Here's a high-level overview of how webhooks work internally:

1. **Event Generation:**
   - The process begins with an event occurring in the source system or application. This event could be anything from a new user registration, a change in data, a status update, etc.

2. **Webhook Registration:**
   - The recipient system, which wants to be notified of these events, typically provides an endpoint URL (webhook URL). This URL is where the source system will send the event data.

3. **HTTP POST Request:**
   - When the event occurs, the source system constructs an HTTP POST request containing relevant information about the event. This data is usually in JSON or XML format and includes details such as event type, timestamp, and any relevant payload.

4. **Webhook Trigger:**
   - The source system sends this HTTP POST request to the webhook URL provided by the recipient system. This triggers the webhook on the recipient side.

5. **Webhook Handling:**
   - The recipient system receives the incoming HTTP POST request at its webhook endpoint. It parses the data and extracts the relevant information about the event.

6. **Event Processing:**
   - The recipient system then processes the received data, taking appropriate actions based on the event. This might involve updating a database, triggering additional processes, or notifying users.

7. **Acknowledgment (Optional):**
   - In some cases, the recipient system sends an acknowledgment (HTTP response) back to the source system to confirm the successful receipt of the webhook. This step is optional and depends on the implementation.

8. **Error Handling:**
   - Both the source and recipient systems should implement error handling mechanisms. For example, if the recipient system is temporarily unavailable, the source system might retry sending the webhook at a later time.

Webhooks provide a more efficient and real-time approach to communication between systems compared to traditional polling methods. They are widely used in various scenarios, such as integrating third-party services, enabling automation, and facilitating communication between different components of a distributed system.

* in case of stripe theres also a signing sceret over https
* hash of the message
* 2gb file---> md5 hash
* status code 400> exponantional backpropagation algorithm
* clients are unreliable
* synchronous and asynchronous


### Web Component
* web components use shadow dom and it is custom html element
  
* A web component is a set of web platform APIs that allows you to create reusable, encapsulated, and interoperable custom elements in web documents and web applications. Web components consist of three main technologies:

1. **Custom Elements:**
   - Custom elements allow developers to create their own HTML elements with custom behavior. These elements can encapsulate functionality, and once defined, they can be reused throughout a web application.
   - Custom elements are created using the `class` syntax in JavaScript. They extend the `HTMLElement` class, and developers can define their own lifecycle callbacks and methods.

2. **Shadow DOM (Document Object Model):**
   - Shadow DOM provides encapsulation by creating a scoped, isolated DOM subtree for a custom element. This means that the styles, scripts, and markup inside a shadow DOM are separate from the rest of the document.
   - Shadow DOM allows developers to create components with their own styling and behavior, preventing outside styles or scripts from affecting the component and vice versa.

3. **HTML Templates:**
   - HTML templates allow you to define chunks of markup that can be cloned and inserted into the document as needed. Templates are inert, meaning they are not rendered until explicitly activated.
   - Web components often use HTML templates to define their structure, and the Shadow DOM can be used to encapsulate the template's content.

* you can also extend html existing elements
* Custom elements
* shadow dom
* scoped styles