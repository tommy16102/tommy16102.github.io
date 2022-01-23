---
layout: post
title: "C++ algorithm 헤더파일"
author: Hyemin Seo
comments: true
tags:
- algorithm
categories:
- C++
date: 2022-01-23 13:03 +0900
---


# Sort
```
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;

bool bigger(int a, int b) {
	return a > b;
}

int main() {
	vector<int> v = { 1,3,5,4,2 }; //vector
	
	sort(v.begin(), v.end()); //오름차순 정렬
	//1 2 3 4 5

	sort(v.begin(), v.end(), greater<>()); //내림차순 정렬
	//5 4 3 2 1

	sort(v.begin(), v.end(), bigger);//내림차순 정렬
	//5 4 3 2 1

	string s = "53412"; //문자열

	sort(s.begin(), s.end()); //오름차순 정렬
	//12345

	sort(s.begin(), s.end(), greater<>()); //내림차순 정렬
	//54321

	sort(s.begin(), s.end(), bigger);//내림차순 정렬
	//54321
}
```

  
  

# Permutation
```
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;

int main() {
	vector<int> v = { 3,2,1 };

	do {
		for (int i = 0; i < 3; i++) {
			cout << v[i] << ' ';
		}
		cout << endl;
	} while (prev_permutation(v.begin(), v.end()));
	/*
	3 2 1
	3 1 2
	2 3 1
	2 1 3
	1 3 2
	1 2 3
	*/

	sort(v.begin(), v.end());

	do {
		for (int i = 0; i < 3; i++) {
			cout << v[i] << ' ';
		}
		cout << endl;
	} while (next_permutation(v.begin(), v.end()));
	/*
	1 2 3
	1 3 2
	2 1 3
	2 3 1
	3 1 2
	3 2 1
	*/
}
```

  
  
  
# Max/Min
```
#include <iostream>
#include <algorithm>
using namespace std;

int main() {
	cout << max(1, 2) << endl; //2
	cout << max('a', 'b') << endl; //b   
	cout << max('a', 'B') << endl; //a
	cout << max(34.00, 34.01) << endl; //34.01
	cout << max("aab", "aac") << endl; //aab
	cout << max(1, max(2, 3)) << endl; //3

	cout << min(1, 2) << endl; //1
	cout << min('a', 'b') << endl; //a
	cout << min('a', 'B') << endl; //B
	cout << min(34.00, 34.01) << endl; //34
	cout << min("aab", "aac") << endl; //aac
	cout << min(1, min(2, 3)) << endl; //1
}
```


  
  
# Max_Element/Min_Element
```
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;

int main() {
	vector<int> v = { 1,2,3,4,5 };
	cout << *max_element(v.begin(), v.end()) << endl; //5
	cout << *min_element(v.begin(), v.end()) << endl; //1

	int arr[] = { 2,3,4,5,6 };
	cout << *max_element(arr, arr + 5) << endl; //6
	cout << *min_element(arr, arr + 5) << endl; //2
}
```



# Upper_Bound/Lower_Bound  
- 이진탐색으로 구현.  
- upper_bound : 찾으려는 key보다 같거나 큰 숫자가 몇 번째에 처음으로 등장.  
- lower_bound : 찾으려는 key보다 같거나 작은 숫자가 몇 번째에 처음으로 등장.  

```

int main() {
	vector<int> v = { 3, 5, 4, 1 }, org = { 3,5,4,1 };
	sort(v.begin(), v.end());
  
  //1 3 2 0
	for (int i = 0;i < 4;i++) {
		cout << lower_bound(v.begin(), v.end(), org[i]) - v.begin() << ' '; 
	}
	
  //2 4 3 1
	for (int i = 0;i < 4;i++) {
		cout << upper_bound(v.begin(), v.end(), org[i]) - v.begin() << ' '; 
	}
  
}

```
