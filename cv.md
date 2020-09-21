# **Galina Znakharchuk**

![Galina Znakharchuk](https://avatars2.githubusercontent.com/u/41628197?s=460&u=8e7ae5227b69cd669b6a5337fa26688e66488afa&v=4)

### **CONTACTS**

Phone: +7 938 473 04 20;

Telegram: @gallagen;

### **SUMMARY**

"Any sufficiently advanced technology is indistinguishable from magic." 
Arthur C. Clarke.


For me, programming is magic - and I'm determined to be a front-end mage this year!
I have a unique and extensive experience, over 10 years, in marketing and design (offline and online).
I am fond of art, purposeful and curious.


### **SKILLS**

* HTML
* CSS, Bootstrap
* JavaScript
* Vue.js, React
* GIT
* Figma
* UI/UX design

##### **SOFT SKILLS**

* Understanding the value for the customer
* Communication skills
* Emotional intellect
* Teamwork
* Time management
* Negotiation skills
* Flexibility and creativity
* Proactivity

### **CODE EXAMPLES**

```
import React from "react"
import ReactDOM from "react-dom"
import "./index.css"

function Square(props) {
  return (
    <button className="square" onClick={props.onClick}>
      {props.value}
      </button>
  );
}

class Board extends React.Component {

  handleClick(i) {
    const squares = this.state.squares.slice();
    if (calculateWinner(squares) || squares[i]) {
      return;
    }
    squares[i] = this.state.xIsNext ? 'X' : 'O';
    this.setState({
      squares: squares,
      xIsNext: !this.state.xIsNext,
    });
  }

  
    renderSquare(i) {
      return (
        <Square 
          value={this.props.squares[i]}
          onClick={() => this.props.onClick(i)}
        />
        );
    }

    render() {
        return (
            <div>
                <div className="board-row">
                    {this.renderSquare(0)}
                    {this.renderSquare(1)}
                    {this.renderSquare(2)}
                </div>
                <div className="board-row">
                    {this.renderSquare(3)}
                    {this.renderSquare(4)}
                    {this.renderSquare(5)}
                </div>
                <div className="board-row">
                    {this.renderSquare(6)}
                    {this.renderSquare(7)}
                    {this.renderSquare(8)}
                </div>
            </div>
        )
    }
}
class Game extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      history: [{ 
        squares:Array(9).fill(null),
      }],
      stepNumber: 0,
      xIsNext: true,
    };
  }

  handleClick(i) {
    const history = this.state.history.slice(0, this.state.stepNumber + 1);
    const current = history[history.length - 1];
    const squares = current.squares.slice();

    if (calculateWinner(squares) || squares[i]) {
      return;
    }
    squares[i] = this.state.xIsNext ? 'X' : 'O';
    this.setState({
      history: history.concat([{
        squares: squares,
      }]),
      stepNumber: history.length,
      xIsNext: !this.state.xIsNext,
    });
  }

  jumpTo(step) {
    this.setState({
      stepNumber: step,
      xIsNext: (step % 2) === 0,
    });
  }

    render() {
      const history = this.state.history;
      const current = history[this.state.stepNumber];
      const winner = calculateWinner(current.squares);

      const moves = history.map((step, move) => {
        const desc = move ?
          'Перейти к ходу #' + move :
          'К началу игры';
        return (
          <li key={move}>
            <button onClick={() => this.jumpTo(move)}>{desc}</button>
          </li>
        );
      });

      let status;
      if (winner) {
        status = 'Выйграл ' + winner;
      } else {
        status = 'Следующий ход ' + (this.state.xIsNext ? 'X' : 'O');
      }

      return (
            <div className="game">
                <div className="game-board">
                  <Board 
                    squares={current.squares}
                    onClick={(i) => this.handleClick(i)}
                  />

                </div>
                <div clssName="game-info">
                    <div>{status}</div>
                    <ol>{moves}</ol>
                </div>
            </div>
        );
    }
}

function calculateWinner(squares) {
  const lines = [
    [0, 1, 2],
    [3, 4, 5],
    [6, 7, 8],
    [0, 3, 6],
    [1, 4, 7],
    [2, 5, 8],
    [0, 4, 8],
    [2, 4, 6],
  ];
  for (let i = 0; i < lines.length; i++) {
    const [a, b, c] = lines[i];
    if (squares[a] && squares[a] === squares[b] && squares[a] === squares[c]) {
      return squares[a];
    }
  }
  return null;
  
}

// ========================================

ReactDOM.render(<Game />, document.getElementById("root"))
```


### **EXPERIENCE**
I have little development experience - mostly educational projects and experiments on my own [GitHub](https://github.com/gallagen)

### **ENGLISH**
A2