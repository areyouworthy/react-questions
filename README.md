# React

###### 1. What the difference between Real DOM and Virtual DOM ?

<details><summary><b>Answer</b></summary>
<p>

#### Answer:

| Real DOM                             | Virtual DOM                        |
| ------------------------------------ | -----------------------------------|
| It updates slow                      | It updates faster                  |
| Can directly update HTML             | Can’t directly update HTML         |
| Creates a new DOM if element updates | Updates the JSX if element updates |
| DOM manipulation is very expensive   | DOM manipulation is very easy      |
| Too much of memory wastage           | No memory wastage                  |

</p>
</details>

---

###### 2. What is React ?

<details><summary><b>Answer</b></summary>
<p>

#### Answer:

- React is a **front-end JavaScript library** developed by Facebook in 2011.
- It follows the **component based approach** which helps in building reusable UI components.
- It is used for developing complex and interactive web and mobile UI.
- Even though it was open-sourced only in 2015, it has one of the largest communities supporting it.

</p>
</details>

---

###### 3. What are the features of React? 

<details><summary><b>Answer</b></summary>
<p>

#### Answer:

- It uses the **virtual DOM** instead of the real DOM.
- It uses **server-side rendering**.
- It follows **uni-directional data flow** or data binding.

</p>
</details>

---

###### 4. What is JSX?

<details><summary><b>Answer</b></summary>
<p>

#### Answer:

JSX is a shorthand for **JavaScript XML**. This is a type of file used by React which utilizes the expressiveness of JavaScript along with HTML like template syntax. This makes the HTML file really easy to understand. This file makes applications robust and boosts its performance. Below is an example of JSX:

```javascript
render() {
  return(
    <div>     
      <h1> Hello World from Edureka!!</h1>
    </div>
  );
}
```

</p>
</details>

---

###### 5. What do you understand by Virtual DOM? Explain its working.

<details><summary><b>Answer</b></summary>
<p>

#### Answer:

A virtual DOM is a lightweight JavaScript object which originally is just the copy of the real DOM. It is a node tree that lists the elements, their attributes and content as Objects and their properties. React’s render function creates a node tree out of the React components. It then updates this tree in response to the mutations in the data model which is caused by various actions done by the user or by the system.
This Virtual DOM works in three simple steps.

1 - Whenever any underlying data changes, the entire UI is re-rendered in Virtual DOM representation.
2 - Then the difference between the previous DOM representation and the new one is calculated.
3 - Once the calculations are done, the real DOM will be updated with only the things that have actually changed. 

</p>
</details>

---

###### 6. What is Props and State

What is the difference between props and state in a component.

<details><summary><b>Answer</b></summary>
<p>

#### Answer:

Props is the shorthand for Properties in React. They are read-only components which must be kept pure i.e. immutable. They are always passed down from the parent to the child components throughout the application. A child component can never send a prop back to the parent component. This help in maintaining the unidirectional data flow and are generally used to render the dynamically generated data.

</p>
</details>

---

###### 7. State

What are the different way to write a setState ?

<details><summary><b>Answer</b></summary>
<p>

#### Answer:

```javascript
  state = {
    count: 0
  }

  onClick () {
    this.setState({ count: this.state.count + 1 });
  }
```

```javascript
  state = {
    count: 0
  }

  onClick () {
    const {count} = this.state;
    this.setState({ count: count + 1 });
  }
```

```javascript
  state = {
    count: 0
  }

  onClick () {
    this.setState(prevState => ({ count: prevState.count + 1 }));
  }
```

</p>
</details>

---

###### 8. Quelle est la valeur affichée dans le console.log après un clique ?

```javascript
  state = {
    count: 0
  }

  onClick () {
    this.setState(prevState => ({ count: prevState.count + 1 }));
    console.log(this.state.count);
  }
```

<details><summary><b>Answer</b></summary>
<p>

#### Answer:

0

</p>
</details>

---

###### 9. Quelle est la valeur affichée dans le console.log après un clique ?

```javascript
  state = {
    count: 0
  }

  onClick () {
    this.setState(prevState => ({ count: this.state.count + 1 }));
    this.setState(prevState => ({ count: this.state.count + 1 }), () => {
      console.log(this.state.count);
    });
  }
```

<details><summary><b>Answer</b></summary>
<p>

#### Answer:

1

</p>
</details>

---

###### 10. Quelle est la différence entre ces deux codes ?

```javascript
class App extends React.Component {
  constructor(props) {
    super(props);

    this.state = {
      count: 0
    };
  }

  onClick = () => {
    this.setState(prevState => ({ count: this.state.count + 1 }));
  }
  ...
}
```

```javascript
const App = () => {
  const [count, setCount] = useState(0);

  onClick = () => {
    setCount(count + 1);
  }
  ...
}
```

<details><summary><b>Answer</b></summary>
<p>

#### Answer:

Aucune différence mise à part qu'en 1. App est une classe alors qu'en 2. App est une fonction.

</p>
</details>

---

###### 11. Quelle est la différence entre ces deux codes ? Expliquez

```javascript
class App extends React.Component {
  onClick() {
    // ...
  }
}
```

```javascript
class App extends React.Component {
  onClick = () => {
    // ...
  };
}
```

<details><summary><b>Answer</b></summary>
<p>

#### Answer:

La fonction fléchée (arrow function) permet de ne pas utiliser bind(this) et d'accéder au this de la classe.

</p>
</details>

---

###### 12. A quoi sert React.createContext() et dans quels cas l'utiliser ?

<details><summary><b>Answer</b></summary>
<p>

#### Answer:

Le context permet de partager des infos entre un parent et ses enfants et petits enfants sans utiliser les props.

</p>
</details>

---

###### 13. A quoi sert React.createPortal() et dans quels cas l'utiliser ?

<details><summary><b>Answer</b></summary>
<p>

#### Answer:

Cela permet de rendre un element dans le DOM en dehors du composant courant.

</p>
</details>

---

