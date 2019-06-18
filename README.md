---
marp: true
---

<!--
style: |
  section h1 {
    text-align: center;
  }
-->

# Test React JS

---

1. Quelle est la valeur affichée dans le console.log après un clique ?

```js
  state = {
    count: 0
  }

  onClick () {
    this.setState({ count: this.state.count + 1 });
    console.log(this.state.count);
  }
```

<!-- Réponse: 0 -->

---

2. Quelle est la valeur affichée dans le console.log après un clique ?

```js
  state = {
    count: 0
  }

  onClick () {
    this.setState({ count: this.state.count + 1 });
    this.setState({ count: this.state.count + 1 }, () => {
      console.log(this.state.count);
    });
  }
```

<!-- Réponse: 1 -->

---

3. Quelle est la valeur affichée dans le console.log après un clique ?

```js
  state = {
    count: 0
  }

  onClick () {
    this.setState(state => ({ count: state.count + 1 }));
    console.log(this.state.count);
  }
```

<!-- Réponse: 0 -->

---

4. Quelle est la différence entre ces deux codes ?

```js
class App extends React.Component {
  constructor(props) {
    super(props);

    this.state = {
      count: 0
    };
  }

  ...
}
```

```js
class App extends React.Component {
  state = {
    count: 0
  };

  ...
}
```

<!-- Réponse: Aucune différence -->

---

5. Combien de fois va s'afficher "render Button" en console si on clique une fois sur le bouton ?

```js
class Button extends React.Component {
  render() {
    console.log('render Button');

    const { children, onClick } = this.props;

    return <button onClick={onClick}>{children}</button>;
  }
}

class App extends React.Component {
  state = {
    count: 0
  };

  render() {
    return (
      <Button onClick={() => this.setState(({ count }) => count + 1)}>
        Click
      </Button>
    );
  }
}
```

<!-- Réponse: 2 fois -->

---

6. Même question: combien de fois va s'afficher "render Button" en console si on clique une fois sur le bouton ?

```js
class Button extends React.PureComponent {
  render() {
    console.log('render Button');

    const { children, onClick } = this.props;

    return <button onClick={onClick}>{children}</button>;
  }
}

class App extends React.Component {
  state = {
    count: 0
  };

  render() {
    return (
      <Button onClick={() => this.setState(({ count }) => count + 1)}>
        Click
      </Button>
    );
  }
}
```

<!-- Réponse: 2 fois -->

---

7. Même question: combien de fois va s'afficher "render Button" en console si on clique une fois sur le bouton ?

```js
class Button extends React.PureComponent {
  render() {
    console.log('render Button');

    const { children, onClick } = this.props;

    return <button onClick={onClick}>{children}</button>;
  }
}

class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0
    };

    this.onClick = this.onClick.bind(this);
  }

  onClick() {
    this.setState(({ count }) => count + 1);
  }

  render() {
    return <Button onClick={this.onClick}>Click</Button>;
  }
}
```

<!-- Réponse: 1 fois -->

---

8. Quelle est la différence entre ces deux codes ? Expliquez

```js
class App extends React.Component {
  onClick() {
    // ...
  }
}
```

```js
class App extends React.Component {
  onClick = () => {
    // ...
  };
}
```

<!-- Réponse: Fonction fléché permet de ne pas utiliser bind(this) et d'accéder au this de la class  -->

---

9. A quoi sert React.createContext() et dans quels cas l'utiliser ?

<!-- Réponse: le context permet de partager des infos entre un parent et ses enfants et petits enfants sans utiliser les props -->

10. A quoi sert React.createPortal() et dans quels cas l'utiliser ?

<!-- Réponse: permet de rendre un element dans le DOM en dehors du composant courant -->

11. A quoi servent ces balises ?

<!-- Réponse: React.Fragment permet d'afficher une list de <div> à la racine d'un composant -->

```
<>
</>
```

---

12. Que manque t-il ?

```js
import io from 'socket.io-client';
import React from 'react';

export class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      messages: []
    };

    this.socket = io('http://localhost:3000');
  }

  componentDidMount() {
    this.socket.on('message', msg => {
      this.setState(state => ({ messages: [...state.messages, msg] }));
    });
  }

  render() {
    return (
      <div>
        {this.state.messages.map(msg => (
          <div key={msg.id}>{msg.text}</div>
        ))}
      </div>
    );
  }
}
```

<!-- Réponse: la déconnexion du socket -->
