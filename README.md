# Tic-Toc-Toe Proposal

The solution have 3 main steps:

 1. Read initial game status
 2. Create game status and define best next move
 3. Show the best move 


## Assumptions

 - Input: Screenshot (png, jpg, jpeg)
 - Output: `Int` best position

GameBoard:

							0  1  2
							3  4  5
							6  7  8


## Approach

 **1. Read initial game status**
	 *Show ad:*
	 `showAd()`
	 *Read Image:*
	 `let status: GameStatus = readImage(image) -> GameStatus`
	 
```
GameStatus: [player] = [ X, O, e
						 O, e, e,
						 X, e, O ] 
```					    
 **2. Create game status and define the best next move**

*Initialize Board game*
	`Let board = Board( status, player )`

```
Board
	- gameStatus: GameStatus
	- player: Player
	- availablePositions: [Int]
	- makeMove (Int) -> Board
```
	 
	

*Get the best next move using 	 [miniMax algorithm:](https://www.geeksforgeeks.org/minimax-algorithm-in-game-theory-set-1-introduction/)*
	
`let bestMove: Int = getBestMove(board) `

```
	func getBestMove(Board) -> Int {
		var bestMove: Int = 0
		for  position in board.availablePositions {
			let result: Int = miniMax(board.makeMove(position), board.player)
			if result > bestMove {
				bestMove = result
			}
		} 
		return  bestMove
	}
```

 **3. Hide ad and show suggestion**
	 
`hideAd()`
`showMove(bestMove)`

