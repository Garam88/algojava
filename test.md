Test
=============
```
import java.util.Arrays;
import java.util.Scanner;

public class p3_nQueen {
	static int N;
	static int[] sol;
	static int[] visited;
	static int Answer;
	/**
	본 풀이는 sol, visited 두 배열을 사용합니다.
	sol배열의 index는 각 행의 번호를, 안에 들어가는 숫자는 열의 번호를 의미합니다.
	예를들어 [1,3,0,2]이라면 
	. * . .
	. . . *
	* . . .
	. . * .
	을 의미합니다.
	visited는 기존에 백트랙에서 사용하는 개념 그대로 사용하게 되므로, 예시에서처럼 sol=[1,3,0,2]의 경우에는
	[0,0,0,0]->[1,0,0,0]->[1,1,0,0](대각선이라 return)->[1,0,0,0]...(생략)...
	[0,1,0,0]->[0,1,1,0](대각선이라 return)->[0,1,0,1]...로 채워지겠지요.
	코드를 실행해 보시면서 이해해보시기 바랍니다.
	**/
	public static void main(String[] args) {

		Scanner sc = new Scanner(System.in);
		
		N = sc.nextInt();

		sol = new int[N];
		visited = new int[N];
		Answer = 0;
		backtrack(0);

		System.out.println(Answer);
	}

	private static void backtrack(int row) {
		System.out.println("sol: "+Arrays.toString(sol));
		System.out.println("vst: "+Arrays.toString(visited));
		if (row == N) {
			System.out.println("------ANSWER------");
			Answer++;
			return;
		}
		System.out.println("------------------");
		
		for (int i = 0; i < N; i++) {
			//대각선을 확인하는 로직
			boolean flag = true;
			for (int j = 0; j < row; j++) {
				if (Math.abs(sol[j] - i) == Math.abs(j - row)) {	//행끼리, 열끼리 뺀 값의 절대값이 같으면 대각선 위에 존재 함
					flag = false;
					break;
				}
			}
			
			
			if (visited[i] == 0 && flag == true) {
				sol[row] = i;
				visited[i] = 1;
				backtrack(row + 1);
				sol[row] = 0;
				visited[i] = 0;
			}
		}
	}
}
```



