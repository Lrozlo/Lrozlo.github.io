---
title: "표준 템플릿 라이브러리(STL)"
excerpt: "container / algorithm / iterator"

categories:
  - C++
tags:
  - [tag1, tag2]

permalink: /cpp/example1/

toc: true
toc_sticky: true

date: 2023-12-08
last_modified_at: 2023-12-08
---

# 표준 템플릿 라이브러리(STL)
## 구성요소
  - container
  - iterator
  - algorithm

## container
  * ### sequential container
    + **std::vector** (95%는 벡터로 충분)
	      크기를 동적으로 조절 가능,
	      메모리 자동 관리해주고 성능도 좋음
    + **std::array**
      
      sequential container중 유일하게 크기를 실행시간에 조절 불가 -> 메모리 사용량을 최소화하도록 성능을 최적화한 것!
    + **std::vector는 새로운 원소를 맨 뒤에 추가하지만 std::deque는 원소를 맨 앞에도 추가 가능**
    + **std::list** : 이중연결리스트 / **std::forward_list** : 단일연결리스트 
        
      → 둘 다 컨테이너의 임의의 지점에서 매우 빠르게 접근하도록 최적화 되어 있음

  * ### associative container

    + **key - value 쌍으로 구성된 컨테이너, 주어진 key에 대한 value를 제공**

    + **총 8가지 associative container 제공됨**

    + **ordered associative container / unordered associative container (가장 큰 차이는 성능)**

      - ordered associative container의 접근 시간 : 원소의 개수에 대해 log함수로 증가
      - unordered associative container의 접근 시간 : 일정(크기와 관계 없음)
    + #### ordered associative container
      - std::set
      - std::map
      - std::multiset
      - std::multimap

      	*set은 key에 연관된 값이 없고 map은 키에 연관된 값 있음*
				
        *map은 key 고유, multimap은 key 중복가능*
				
        *map의 속성은 vector와 비슷
				-> 연관 컨테이너 사용하는 경우 95프로는 key기준 정렬하는 map으로 충분*

    + #### unordered associative container
      - std::unordered_set

      - std::unordered_map
      
      - std::unordered_multiset
      
      - std::unordered_multimap

    + **container adapter**
	      
      순차 컨테이너에 대한 간편한 인터페이스 제공
		
      std::stack / std::deque / std::priority_queue

## iterator   

- 컨테이너와 알고리즘을 연결해줌
- 반복자는 컨테이너에 의해 생성되며, 범용 포인터로 구성됨
- 반복자는 컨테이너에 대한 반복문을 임의의 위치를 기준으로 정방향/역방향으로 진행하는데 사용됨
- 반복자의 종류는 컨테이너마다 다름
- 반복자 어댑터(iterator adapter)를 사용하면 스트림에 직접 접근 가능
- STL에서 제공하는 알고리즘은 원소 또는 원소 범위에 대해 작동하는데, 이때 범위는 시작지점을 가리키는 begin iterator와 end iterator(범위 끝의 원소가 아니라 그 다음 지점을 가리키는 것에 주의!)로 지정.

