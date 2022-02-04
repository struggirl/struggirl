//检查井字棋是否有胜利
#include <stdio.h>
int main() {
	const int size = 3;
	int board[size][size];
	int i, j;//数组行列下标
	int numOfX;
	int numOfO;
	int result = -1;   //   -1：没人赢  1：X赢  0：O赢

//读入矩阵
	for (i = 0; i < size; i++) {
		for (j = 0; j < size; j++) {
			scanf("%d", &board[i][j]);//依次读入很离谱，但暂时不知道怎么改
		}
	}
//检查行
//因为内循环做完一轮才做外循环，所以行循环在里，列循环在外
	for (i = 0; i < size && result == -1; i++) {//result不等于-1的时候就是有人胜利了，故构成出循环的条件
		numOfO = numOfX = 0;//对O和X的数量初始化
		for (j = 0; j < size; j++) {
			if (board[i][j] == 1) {
				numOfX++;//如果格子里是1，则X的数量加一
			}
			else {
				numOfO++;//如果格子里的不是1（是0），则O的数量加一
			}
		}
		if (numOfO == size) {
			result = 0;
		}//如果O的数量和长度相等，则O胜利
		else if (numOfX == size) {
			result = 1;
		}//如果X的数量和长度相等，则X胜利
	}
//检查列
	for (j = 0; j < size && result == -1; j++) {//result不等于-1的时候就是有人胜利了，故构成出循环的条件
		numOfO = numOfX = 0;//对O和X的数量初始化
		for (i = 0; i < size; i++) {
			if (board[i][j] == 1) {
				numOfX++;//如果格子里是1，则X的数量加一
			}
			else {
				numOfO++;//如果格子里的不是1（是0），则O的数量加一
			}
		}
		if (numOfO == size) {
			result = 0;
		}//如果O的数量和长度相等，则O胜利
		else if (numOfX == size) {
			result = 1;
		}//如果X的数量和长度相等，则X胜利
	}
//检查对角线
		numOfO = numOfX = 0;//再次对O,X的个数初始化
		for (i = 0; i < size; i++) {
			if (board[i][i] == 1) {
				numOfX++;
			}
			else {
				numOfO++;
			}
		}
		if (numOfO == size) {
			result = 0;
		}else if (numOfX == size) {
			result = 1;
		}
			numOfO = numOfX = 0;
			for (i = 1; i < size; i++) {
				if (board[i][size - i - 1] == 1) {
					numOfX++;
				}else {
					numOfO++;
				}
			}
			if (numOfO == size) {
				result = 0;
			}
			else if (numOfX == size) {
				result = 1;
			}
			if (result = -1) {
				printf("平局");
			}
			else if (result = 0) {
				printf("O胜");
			}
			else {
				printf("X胜");
			}
	return 0;
}
