# Tic-Tac-Toe vs Computer (Computer blocks one turn wins)
# Spring 2022 HS Sr.

import os
import random

def printB(board):
	for r in range(len(board)):
		for c in range(len(board[r])):
			print(board[r][c], end='  ')
		print("\n")


def update(board, r, c, val):
	board[r][c] = val
	return(board)


def isWinBoard(board, val):
	for r in range(1, len(board)):
		if(board[r][1] == val and board[r][2] == val and board[r][3] == val):
			return True
	for c in range(1, len(board[1])):
		if(board[1][c] == val and board[2][c] == val and board[3][c] == val ):
			return True
	if(board[2][2] == val):
		if(board[1][1] == val and board[3][3] == val ):
			return True
		if(board[1][3] == val and board[3][1] == val ):
			return True
	return False


def computerPlay(board):
	flag = True
	for r in range(1, len(board)):
		for c in range(1, len(board[1])):
			if(board[r][c] == "_"):
				hold = board
				if(isWinBoard(update(hold, r, c, "O") , "O") ):
					board = update(board,r,c,"O")
					return board
				else:
					update(hold, r, c, "_")
	ranR = 0
	ranC = 0
	while(ranR == 0):
		ranR = random.randint(1,3)
		ranC = random.randint(1,3)

		if(board[ranR][ranC] == "_"):
			board = update(board,ranR, ranC, "O")
			return(board)
		ranR = 0


def computer(board):
	for r in range(1, len(board)):
		for c in range(1, len(board[1])):
			if(board[r][c] == "_"):
				if(isWinBoard(update(board, r, c, "X") , "X") ):
					board = update(board,r,c,"O")
					return board
				else:
					update(board, r, c, "_")

	board = computerPlay(board)
	return(board)


def ttt():
	board = [ 
		[" ", "1", "2", "3"],
		["1", "_", "_", "_"],
		["2", "_", "_", "_"],
		["3", "_", "_", "_"],
	]
	rounds = 1	
	printB(board)
	while(not(isWinBoard(board, "X")) and not(isWinBoard(board, "O")) and rounds <10):
		r = int(input("Enter r: "))
		c = int(input("Enter c: "))

		while(not(r > 0 and r < 4) or not(c > 0 and c < 4) or not(board[r][c] == "_")): 
			os.system("clear")
			printB(board)
			r = int(input("Not valid\nEnter r: "))
			c = int(input("Enter c: ")) 

		board = update(board, r, c, "X")
		rounds+=1
		if(not(isWinBoard(board, "X")) and rounds < 10):
			board = computer(board)
			rounds+=1
		os.system("clear")  
		printB(board)

	if(isWinBoard(board, "X")):
		print("X is the winner!")
	elif(isWinBoard(board, "O")):
		print("O is the winner!")
	else:
			print("Tie! Try again.")


def main():
	ttt()


main()
