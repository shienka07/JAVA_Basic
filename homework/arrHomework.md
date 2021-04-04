##  하-1 : int형 6칸 짜리 배열을 생성하세요.

int[] nums = new int[6];



##  하-2 : 다음 출력 결과를 예상하세요.

​	int[] a = new int[2]; 
​	System.out.println(a[0]); // 답 :  0
​	System.out.println(a[1]); // 답 :  0

​    double[] b = new double[2];
​    System.out.println(b[0]); // 답 : 0.0
​    System.out.println(b[1]); // 답 : 0.0 

​    String[] c = new String[2];
​    System.out.println(c[0]); // 답 : null 
​    System.out.println(c[1]); // 답 : null

   char[] d = new char[2];
   System.out.println(d[0]); // 답 : (\0) -> 눈에 안보임 
   System.out.println(d[1]); // 답 : (\0) -> 눈에 안보임

   boolean[] e = new boolean[2];
   System.out.println(e[0]); // 답 : false
   System.out.println(e[1]); // 답 : false

 



## 하-3 :  입력받은 수로 int 배열 생성하기

- 사용자에게 배열의 칸 개수를 입력 받고, 해당 정수의 크기만큼 정수형 배열을 생성하세요.

- 	입력 : 3  ===> 결과 : [ 0, 0, 0 ] 
- 	입력 : 5  ===> 결과 : [ 0, 0, 0, 0, 0 ] 

```java
public static void main(String[] args) {
		
	Scanner sc = new Scanner(System.in);
		
	int a = 0;
		
	System.out.println("배열의 개수를 입력해주세요 : ");
	a = sc.nextInt();
		
	int[] nums;
	nums = new int [a];
		
	System.out.println(Arrays.toString(nums));
}
```







##  하-4 : (3)번에서 생성된 배열에 다음 기능을 추가하세요.

- 	ㄱ. 0 ~ n-1 까지의 숫자를 배열에 순서대로 저장하세요.
		- 입력 : 3  ===> 결과 : [0, 1, 2]
		- 입력 : 5  ===> 결과 : [0, 1, 2, 3, 4]
-	ㄴ. 배열의 가장 마지막 원소부터 0번 원소까지 역순으로 출력하세요.
-	ㄷ. for문을 사용하여 배열에 저장된 실제 원소들을 역순으로 재배치 하세요. (난이도 중)
	   -  sysout(배열[0]); // 3
	   -  sysout(배열[1]); // 2
	   -  sysout(배열[2]); // 1
	   -  sysout(배열[3]); // 0
	   - (for문을 쓰되 for문의 실행 횟수가 n/2이 되도록하세요. 
    - (5칸 배열이면 2회만에, 10칸 배열이면 5회만에 for문이 종료되도록))

```java
public class Homework01 {

	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		
		// 배열 갯수 입력 받기
		int a = 0;
		
		System.out.println("배열의 개수를 입력해주세요 : ");
		a = sc.nextInt();
		
		int[] nums;
		nums = new int [a];
		
		// 숫자 순으로 원소에 넣기
		for (int i = 0; i < nums.length ; ++i) {
			nums[i] = i;
		}
		System.out.println(Arrays.toString(nums));
		
		// 역순 출력
		for (int i = nums.length-1; 0 <= i; --i) {
			System.out.print(nums[i] + "\t");
		}
		System.out.println();
		
		
		// 역순 재배치
		for (int i = 0; i < (nums.length/2) ; i++) {
			int b = (nums.length)-i -1;
			int c = nums[i];
			nums[i] = nums[b];
			nums[b] = c;
		}
		
		for (int i = 0; i < nums.length; ++i) {
			System.out.print(nums[i]);
		}
  
    }
}
```







## 하-5 :  입력받은 수로 String 배열 생성후 값 입력받기

- 사용자에게 배열의 칸 개수를 입력 받고, 해당 정수의 크기만큼 String형 배열을 생성하고

	- 입력 : 3  ===> 결과 : [ null, null, null ] 
	- 입력 : 5  ===> 결과 : [ null, null, null, null, null ]


- 사용자에게 입력받은 단어들을 순차적으로 배열에 저장하세요.  

```java
public class Homework02 {
	public static void main(String[] args) {
		Scanner sc = new Scanner (System.in);
		
		int a= 0;
		
		System.out.println("배열의 개수를 입력해주세요 : ");
		a = sc.nextInt();
		
		String[] names;
		names = new String [a];
		
		System.out.println(Arrays.toString(names));
		System.out.println();
		
		for(int i =0; i < names.length; ++i) {
			System.out.print("이름을 입력해주세요 : ");
			names[i] = sc.next();
		}
		
		System.out.println(Arrays.toString(names));
		
    }
}
```





-----------------

난이도 : 중
 중-1 : https://www.acmicpc.net/problem/8958

안해도됨



##  중-2 :  D-Day 계산기

dates 배열은 다음과 같이 1~12월의 최대 일자가 들어있습니다. 

​	 ==> int[] dates = {31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31}; 

- 1) dates 배열을 활용하여 1/1일부터 사용자에게 입력 받은 월/일 까지 며칠이 소요되는지 출력하세요.
   - 단, 사용자에게 해는 따로 입력받지 않기때문에 윤년은 없다고 가정합니다.

- 예) 월 : 12   일 : 31  ==> 364일 소요!
    - 월 : 4    일 : 12   ==> 101일
- 원리) 4/12 의 결과를 계산하려면
    - 1 / 1 ~ 1 / 31  => 31 (dates[0]) 
    - 2 / 1 ~ 2 / 28  => 28 (dates[1])
    - 3 / 1 ~ 3 / 31  => 31 (dates[2])
	 - 4 / 1 ~ 4 / 12  => 12 (사용자가 입력한 일)
    - => 31 + 28 + 31 + 12 - 1 = 101일 



```java
public class Homework02 {
	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		
		int[] dates = new int[] {31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31};
		int month = 0;
		int day = 0;
		int sum = 0;
		
		System.out.println("1/1 부터 며칠이 소요되는지 알려드립니다!");
		System.out.println("원하시는 날짜를 입력해주세요 : ");
		System.out.print("월 : ");
		month = sc.nextInt();
		System.out.print("일 : ");
		day = sc.nextInt();
		
		for (int i = 0; i <= month; ++i) {
			sum += dates[i];
		}
		
		sum += day;
		
		System.out.println("1월 1일부터 원하시는 날짜까지 " + sum + "일이 소요됩니다.");
		
```

2) 시작월/일과 목표 월/일 을 각각 입력 받고 d-day 계산기를 만드세요.
  - 단, year는 입력받지 않기때문에 d-day의 최댓값은 364일로 가정합니다.
  - 예) 시작 : 9/26  목표 : 11/23  ==> 결과 : d-day 58 !!!
      - 시작 : 1/1 목표 : 12/31  ==> 결과 : d-day 364 !!!
      - 시작 : 12/31 목표 : 1/1  ==> 결과 : d-day 1 !!!
      - 시작 : 4/12 목표 : 4/11  ==> 결과 : d-day 364 !!!
   - 원리)
	 - start : 1/1 ~ 시작 월/일까지 며칠이 소요되는지 계산합니다. 
	 - end : 1/1 ~ 목표 월/일까지 며칠이 소요되는지 계산합니다. 
	 - end-start 를 합니다. 
	 - 이때 음수가 나온다면 목표일이 시작일보다 앞서있다는 의미입니다. (즉 목표일이 이듬해)
	 - 이 경우 +365를 하면 됩니다.	

```java
public class Homework02_1 {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);

		int[] dates = new int[] { 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };
		int sMonth = 0;
		int sDay = 0;
		int eMonth = 0;
		int eDay = 0;
		int sSum = 0;
		int day = 0;

		System.out.println("D-day 계산기!");
		System.out.println("기준 날짜를 알려주세요");

		System.out.print("월 : ");
		sMonth = sc.nextInt();
		System.out.print("일 : ");
		sDay = sc.nextInt();

		for (int i = 0; i < sMonth - 1; ++i) {
			sSum += dates[i];
		}
		sSum += sDay - 1;

		System.out.println("원하는 날짜를 알려주세요");

		System.out.print("월 : ");
		eMonth = sc.nextInt();
		System.out.print("일 : ");
		eDay = sc.nextInt();

		for (int i = 0; i < eMonth - 1; ++i) {
			eSum += dates[i];
		}
		eSum += eDay - 1;
		
        
		if (sSum <= eSum) {
			day = eSum - sSum;
		} else {
			day = eSum - sSum + 365;
		}

		System.out.println("D-day : " + day + "!!!");
	}
}
```













##  중-3:  성 + 이름 조합하기

- "김", "이", "박", "최", "한" 등의 대한민국 성씨를 저장할 배열을 만들고, 성씨들을 저장하세요.
- "피카츄", "라이츄", "파이리", "꼬부기", "버터풀", "야도란", "피죤투" 를 저장할 배열을 만들고 이름들을 저장하세요.
     - 1) 총 10개의 성+이름 조합을 출력하세요. ( Math.random()을 사용하며, 중복 조합을 허용합니다)
     - 2) 조합가능한 모든 이름을 출력하세요.



```java
public class Homework03 {
	
	public static void main(String[] args) {
	
		String[] fNames = new String[] {"김", "이", "박", "최", "한", "성", "송"};
		String[] lNames = new String[] {"피카츄", "라이츄", "파이리", "꼬부기", "버터풀", "야도란", "피죤투"};
		
		int f = (int) ((Math.random()*7)+1);
		int l = (int) ((Math.random()*7)+1);
		int count = 0;
		
		// 3-1
		System.out.println(fNames[f] + lNames[l]);
		
		
		// 3-2
		for (int i = 0; i < fNames.length; ++i) {
			for (int j = 0; j < lNames.length; ++j) {
				System.out.println(fNames[i] + lNames[j]);
			}
		}
		
	}
}
```





##  중-4: https://www.acmicpc.net/problem/4344

```java
public class Homework04 {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		
		int[] student;
		double avg = 0.0; // 평균 성적
		double sum = 0; // 성적 누적
		double count = 0; // 평균 이상 학생수
	

		int testcase = sc.nextInt();
		
		
		for (int i =0; i < testcase ; i++) {

			student = new int[sc.nextInt()]; // 학생수
			// 각 케이스 마다 학생수로 배열 만들기
	
			// 성적입력
			for (int j =0; j < student.length; j++) {
				student[j] = sc.nextInt(); // 성적 입력
				sum += student[j]; // 성적 누적
			}
			
			avg = (double) sum / student.length;
			
			// 학생들 개별 평균점수 이상인지 확인
			for (int j = 0; j < student.length; j++) {
				if (student[j] > avg ) {
					count++;
				}
			}
            
			// (평균이상 학생수 / 총 학생수)
			System.out.print(new DecimalFormat(".###").format((100 * count)/student.length));
			System.out.print("%");
			
			
			System.out.println();
		
		}
		
	}

}
```





## 중-5: 호텔관리 프로그램 만들기 
- 	step1) 사용자에게 호텔의 방 개수를 입력 받습니다.
- 	step2) 방개수와 동일한 크기의 배열을 생성합니다. (5개면 5칸짜리 배열 생성)
-  step3) 사용자 메뉴를 메시지로 보여주고 메뉴를 선택 받습니다.    

 < 메뉴 >

1. 체크인

2. 체크아웃

3. 현황 보기

4. 종료하기

// 메뉴를 뜨게하는법
종료를 누르기 전까지 계속 다른것을 누를수 있기



   1. 체크인
      방 호수(1번부터 시작)를 입력 받습니다.
      방이 이미 입실 중이면 "입실 중인 방은 체크인 하실 수 없습니다."를 출력하세요.
      빈 방인 경우 "입실 완료!"를 출력하고 메뉴로 돌아갑니다.

   2. 체크아웃
      방 호수(1번부터 시작)를 입력 받습니다.
      방이 빈 방이면 "빈 방은 체크아웃 하실 수 없습니다."를 출력하세요.
      체크인 상태인 경우 "퇴실 완료!"를 출력하고 메뉴로 돌아갑니다.

   3. '방호수 - 상태'를 출력합니다.
      출력 예)
      1호 : 빈 방
      2호 : 입실 중
      3호 : 입실 중
      4호 : 빈 방
      5호 : 빈 방

   4. 종료
      반복을 종료하고 '영업 종료' 를 출력합니다.

      (힌트 : 사용자가 4호에 입실한다면 [3]번칸에 1을 저장하고 퇴실한다면 0을 저장합니다. 즉 투숙객이 있음은 1로 없으면 0으로 표시합니다.)

      step4) 사용자가 메뉴에서 0을 입력할 때까지 (3) 과정을 진행합니다.



```java
public class Homework05 {
	public static void main(String[] args) {

		Scanner sc = new Scanner(System.in);

		String menu = "1. 체크인 \n" + "2. 체크아웃 \n" + "3. 현황 보기 \n" + "0. 종료";

		String select;
		int[] rooms;
		int a = 0;

		String roomStatus[] = null;

		// step 1
		String aRoom = JOptionPane.showInputDialog(null, "방 개수를 입력해주세요");

		// stpe 2
		a = Integer.parseInt(aRoom);
		rooms = new int[a];
		roomStatus = new String[a];

        
		// step 3
		loop: while (true) {

			select = JOptionPane.showInputDialog(null, menu);

			switch (select) {

			case "1": {
				String message = JOptionPane.showInputDialog(null, "체크인 하실 방 호수 입력하세요.");
				int num = Integer.parseInt(message) - 1;
				if (num > rooms.length - 1 || num < 0) {
					JOptionPane.showMessageDialog(null, "선택가능한 호실을 벗어났습니다.");
					break;
				}
				if (rooms[num] == 0) {
					JOptionPane.showMessageDialog(null, "입실이 완료되었습니다!");
					++rooms[num];
				} else {
					JOptionPane.showMessageDialog(null, "입실 중인 방은 체크인 하실 수 없습니다.");
				}
				break;
			}

			case "2": {
				String message = JOptionPane.showInputDialog(null, "체크아웃 하실 방 호수 입력하세요.");
				int num = Integer.parseInt(message) - 1;

				if (rooms[num] == 0) {
					JOptionPane.showMessageDialog(null, "빈 방은 체크아웃 하실 수 없습니다.");
				} else {
					JOptionPane.showMessageDialog(null, "퇴실이 완료되었습니다!");
					--rooms[num];
				}
				break;
			}

			case "3": {
				for (int i = 0; i < rooms.length; ++i) {
					if (rooms[i] == 1) {
						roomStatus[i] = i + 1 + "호실 : 입실중";
					} else {
						roomStatus[i] = i + 1 + "호실 : 빈 방";
					}
				}
				JOptionPane.showMessageDialog(null, roomStatus);
				break;
			}
			
            // step 4
			case "0": {
				JOptionPane.showMessageDialog(null, "프로그램을 종료합니다.");
				break loop; 
			}

			default: {
				JOptionPane.showMessageDialog(null, "잘못된 선택입니다.");
			}
			}
		}
	}

}
```



##  중-6: 로또생성기 만들기 

- 	step1) 사용자에게 1 ~ 45 중 6개의 숫자를 입력 받습니다.
- 	step2) 컴퓨터는 로또 번호 6개를 생성합니다. 배열의 크기는 6이고 int형입니다.
- 	step3) 1 ~ 45 중 6개의 숫자를 배열에 담습니다. 중복된 원소가 있으면 안됩니다.
- 	step4) (구현 가능하다면) 오름차순 정렬을 합니다.
- 	step5) 배열 결과를 출력합니다.
- 	step6) 사용자가 몇 개의 번호를 맞췄는지 출력하세요.



```java
public class Homework06 {
	public static void main(String[] args) {

		Scanner sc = new Scanner(System.in);

		int[] lotto = new int[6];
		int[] user = new int[6];
		int count = 0;
        
		// user의 번호 고르기
		for (int i = 0; i < user.length; ++i) {
			System.out.print(i + 1 + "번째 숫자를 골라주세요 : ");
			user[i] = sc.nextInt();
            
            // 범위제한
			if (user[i] < 0 || 45 < user[i]) {
				System.out.println("범위 안의 수를 골라주세요");
				i--;
			}
            
            // 중복 제한
			for (int j = 0; j < i; ++j) {
				if (user[i] == user[j]) {
					System.out.println("같은 수를 입력하셨습니다.");
					i--;
					break;
				}

			}
		}
        
        // 선택한 번호 오름차순 정렬
		for (int i = 0; i < user.length - 1; ++i) {
			for (int j = i + 1; j < user.length; ++j) {
				if (user[i] > user[j]) {
					int a = user[i];
					user[i] = user[j];
					user[j] = a;
				}
			}
		}
        

        // 로또 번호 추출
		for (int i = 0; i < lotto.length; ++i) {
			lotto[i] = (int) (Math.random() * 45) + 1;
			
            // 중복 제한
			for (int j = 0; j < i; j++) {
				if (lotto[i] == lotto[j]) {
					i--;
					break;
				}
			}
		}
        
        // 오름차순 정렬
		for (int i = 0; i < lotto.length - 1; ++i) {
			for (int j = i + 1; j < lotto.length; ++j) {
				if (lotto[i] > lotto[j]) {
					int a = lotto[i];
					lotto[i] = lotto[j];
					lotto[j] = a;
				}
			}
		}
        
        
        // 맞춘 갯수 카운트
		for (int i = 0; i < user.length; ++i) {
			for (int j = 0; j < lotto.length; ++j) {
				if (user[i] == lotto[j]) {
					count++;
				}
			}
		}

		System.out.println();
		System.out.print("선택한 숫자 : ");
		for (int i = 0; i < user.length; ++i) {
			System.out.print(user[i] + " ");
		}

		System.out.println();
		System.out.print("Lotto 당첨 번호 : ");
		for (int i = 0; i < lotto.length; ++i) {
			System.out.print(lotto[i] + " ");
		}

		System.out.println();
		System.out.println("맞춘 갯수는 : " + count + "개 입니다!");

	}
}
```

