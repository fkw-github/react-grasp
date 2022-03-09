# 通过实现井字棋来认识 React

## 搭建本地开发环境
  1. 安装比较新版本的 Node.js
  2. 使用 `npx create-react-app my-app` 创建新项目
  3. 将 **src/** 文件夹内的所有文件删除（src 该文件夹要保留），你可以使用命令删除，也可以使用图形界面方式删除，看君所好。

## src 文件夹下创建一些文件和添加需要的代码
1. 创建 **index.css**，将下列代码拷贝进去
   ```css
    body {
      font: 14px "Century Gothic", Futura, sans-serif;
      margin: 20px;
    }
    ol, ul {
      padding-left: 30px;
    }

    .board-row:after {
      clear: both;
      content: "";
      display: table;
    }

    .status {
      margin-bottom: 10px;
    }

    .square {
      background: #fff;
      border: 1px solid #999;
      float: left;
      font-size: 24px;
      font-weight: bold;
      line-height: 34px;
      height: 34px;
      margin-right: -1px;
      margin-top: -1px;
      padding: 0;
      text-align: center;
      width: 34px;
    }

    .square:focus {
      outline: none;
    }

    .kbd-navigation .square:focus {
      background: #ddd;
    }

    .game {
      display: flex;
      flex-direction: row;
    }

    .game-info {
      margin-left: 20px;
    }

   ```
2. 创建 **index.js**，并将下列代码拷贝进去
   ```javaScript
    class Square extends React.Component {
      render() {
        return (
          <button className="square">
            {/* TODO */}
          </button>
        );
      }
    }

    class Board extends React.Component {
      renderSquare(i) {
        return <Square />;
      }

      render() {
        const status = 'Next player: X';

        return (
          <div>
            <div className="status">{status}</div>
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
        );
      }
    }

    class Game extends React.Component {
      render() {
        return (
          <div className="game">
            <div className="game-board">
              <Board />
            </div>
            <div className="game-info">
              <div>{/* status */}</div>
              <ol>{/* TODO */}</ol>
            </div>
          </div>
        );
      }
    }

    // ========================================

    ReactDOM.render(
      <Game />,
      document.getElementById('root')
    );

   ```
3. 将下列三行代码拷贝到 **index.js** 文件顶部
   ```javaScript
    import React from 'react';
    import ReactDOM from 'react-dom';
    import './index.css';

   ```

## 在项目文件夹下执行 `npm start`，浏览器访问 [http://localhost:3000](http://localhost:3000) 即可看到井字棋盘
