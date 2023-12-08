---
title: "Vector"
excerpt: "vector에 관하여..."

categories:
  - C++
tags:
  - [vector,C++,stl]

permalink: /cpp/vector/

toc: true
toc_sticky: true

date: 2023-12-08
last_modified_at: 2023-12-08
---
# std::vector
  - #include <vector> 로 사용가능
  - 실행시간에 길이 조정이 가능한 컨테이너 
  - 원소를 메모리에 연속해서 저장
  - 포인터 산술연산 지원
  
## vector 생성 및 초기화
```cpp
    - 1차원 벡터
    vector<int> vec1;
    vector<int> v;
	vector<int> v(5);    // 0 0 0 0 0
	vector<int> v(5, 1); // 1 1 1 1 1
    
    - 1차원 벡터 배열
    vector<int> vec1[10];

    - 2차원 벡터
    vector<vector<int>> v(10,vector<int>(10,0)); 
    // v(행개수,열개수,초기화값) v[i][j]로 요소에 접근 가능

    vector<int> vec2(vec1.begin(), vec1.end()); //복제
    vector<int> vec3(vec2);    //복제
    vector<int> vec3 = vec2;   //복제

    vector<int> vec4(std::move(vec3));  //이동
    vector<int> vec4 = std::move(vec3);   //이동

    vector<int> vec5 {1,2,3,4,5};
    vector<int> vec5 = {1,2,3,4,5};

```
## vector 함수
```cpp
    - 원소 삽입
    v.push_back(1); // 마지막에 삽입
    v.insert(1,2,3); // 1번째 위치에 3값을 2개 삽입
    v.insert(1,2);  // 1번째 위치에 2값을 삽입

    - 원소 접근
    v.at(i) //i번째 요소 접근(범위 검사함)
    v.[i]
    v[i]
    v.front()
    v.back()

    - 원소 제거
    v.pop_back();  //마지막 원소 제거
    v.clear();    //원소삭제(모두 제거)
    v.erase(iter);   // iter가 가르키는 놈을 삭제
    v.erase(iter1, iter2);      // iter1 ~ iter2 범위 삭제

    v.~vector();  //소멸자

    - 반복자
    v.begin();  // 첫번째 iter
    v.end();    // 마지막 iter
    v.rbegin(); // reverse begin iter
    v.rend();   // reverse end iter

    - 그 외
    v.empty();      // vector 가 비어있는지 확인
    v.size();       // vector 벡터의 사이즈 리턴    
    v.reserve(10);      // 10칸을 예약(할당)(메모리 확보)
    v.resize(10);       // 크기를 10으로 변경, 커질경우 초기화 0
    v.resize(10, 1);    // 크기를 10으로 변경, 커질경우 초기화 1
    
    - 복사
    // 전체 복사 1
	vector_to.resize(vector_from.size());
	copy(vector_from.begin(), vector_from.end(), vector_to.begin());
	
    // 부분 복사 1
	vector_to.resize(vector_from.size());
	copy(vector_from.begin() + 1, vector_from.begin() + 3, vector_to.begin());
	
    // 전체 복사 2
	vector_to.clear()
	vector_to.assign(vector_from.begin(), vector_from.end());
	
    // 부분 복사 2
	vector_to.clear()
    vector_to.assign(vector_from.begin() + 1, vector_from.begin() + 3);
    
    - 정렬
    // 오름차순 정렬
    sort(v.begin(), v.end()); // == sort(v.begin(), v.end(), less<int>() );

    // 내림차순 정렬
    sort(v.begin(), v.end(), greater<int>());

    // 구조체 a값 기준 오름차순 정렬 - 람다 함수
    sort(vv.begin(), vv.end(), [](const auto& lhs, const auto& rhs) {return lhs.a < rhs.a; });

    // 구조체 a값 기준 내림차순 정렬 - 람다 함수
    sort(vv.begin(), vv.end(), [](const auto& lhs, const auto& rhs) {return lhs.a > rhs.a; });

    // 구조체 a값 기준 오름차순 정렬 - cmp 함수
    typedef struct str {int a, b;}str;
    bool cmp(const str& lhs, const str& rhs){
        return lhs.a < rhs.a;
    }
    sort(v.begin(), v.end(), cmp);

    // 구조체 a값 기준 내림차순 정렬 - cmp 함수
    bool cmp(const str& lhs, const str& rhs){
        return lhs.a > rhs.a;
    }
    sort(v.begin(), v.end(), cmp);

    - 역순
	reverse(v.begin(), v.end());

``` 
