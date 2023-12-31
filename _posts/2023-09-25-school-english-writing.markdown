---
layout: post
title:  "영어 2차 쓰기 평가 연습"
date:   2023-09-25 02:47:08 +0900
categories: [School]
permalink: /school/23/english1
---

자동으로 쓰기 평가의 문장을 무작위하게 고르고, 올바르게 직역했는지 확인합니다.  
대소문자, 띄어쓰기, 문장 부호 등도 주어진 학습지와 정확히 같아야 정답으로 인식합니다.   
컴퓨터라면 아래의 "긴 입력" 버튼으로 입력칸을 늘릴 수 있습니다.   
포스트의 하단에서 답안을 확인할 수 있습니다.    

<div>
  <p id="question-text">이 앱은 사람들이 다른 사람들로부터 빌릴 수 있는 물건들을 쉽게 찾도록 돕는다.</p>
  <input id="answer-input" type="text" style="width: 400px; font-size: 16px; height: 20px" placeholder="직역한 문장"> <button onclick="textEntered()"> 입력 </button> 
  <p id="stats">이곳에 정답을 맞힌 횟수, 비율 등이 표시됩니다.</p>
  <p id="correct-row">주어진 문장을 영작하세요.</p>
  <br>
  <button onclick="shuffleMode()">기본 셔플</button> <button onclick="fullRandomMode()">랜덤 셔플</button>
  <button onclick="shortInput()">짧은 입력</button> <button onclick="longInput()">긴 입력</button>
</div>
<script>
  var questions = [
    "이 앱은 사람들이 다른 사람들로부터 빌릴 수 있는 물건들을 쉽게 찾도록 돕는다.",
    "더 많은 사람들이 그 서비스들을 사용할수록, 그것들이 더 개선될 것이다.",
    "그것은 네가 다른 사람들로부터 빌릴 수 있는 물건들을 찾을 수 있는 앱이다.",
    "그 문제가 더 복잡할수록, 그것을 푸는 데 시간이 더 오래 걸린다.",
    "그녀가 더 유명해질수록, 그녀는 더 많은 돈을 벌 것이다.",
    "전에 한 번도 비행기로 날아간 적이(비행기를 탄 적이) 없었으므로 나는 긴장되었다.",
    "영국에서 태어났지만, 그는 지금 파리를 그의 고향으로 여긴다.",
    "일반적으로 말해, 더 큰 동물들이 더 작은 동물들보다 더 오래 산다.",
    "피터가 저녁을 다 먹었기 때문에, 우리는 산책을 했다.",
    "그 유명인들이 도착하여 자리들에 앉자, 파티가 시작되었다.",
    "그녀는 그를 모방하는 대신에 그녀 자신의 스타일을 개발했어야 했다.",
    "정부는 우리 경제가 성장하도록 돕기 위해 노력을(시도를) 해야 한다.",
    "나는 내 개인 정보를 나누어 주지(알려 주지) 않으려고 노력한다.",
    "우리는 병으로 인해 사람들이 쉬는(퇴근하는/휴가를 내는) 시간의 양을 기록한다.",
    "약간의 조화들이 거실을 장식하기 위해 사용되었다.",
    "예전에는 여행자들이 대개 별들에 의해 길을 찾았다.",
    "홍수들과 지진들과 같은 자연 재해들은 매년 수천 명의 사람들에게 영향을 준다.",
    "이 사전은 전자 형식으로 구할 수 있다.",
    "사이렌은 모두가 건물을 떠나라는 신호였다.",
    "모든 차는 에어백을 갖추고 있다.",
    "몇몇 사람들은 로봇들의 도움으로 인생이 더욱 편안해지기를 기대한다.",
    "수색구조 로봇들은 인간들에게 위험한 재난지역들로 들어갈 수 있다.",
    "내 여동생은 그 고급스러운 가방을 살 수 있기 위해서 돈을 모았다.",
    "만약 내 고양이가 그 냉장고를 열 수 있다면 그것은 내 음식 모두를 먹을 텐데.",
    "이 문제를 해결하기 위해서, 우리는 빌려주는 사람들에게 주기적으로 자신들의 물품들의 사진들을 업데이트할 것을 요청하고 있다.",
    "그녀가 피곤하지 않다면 그녀는 밤새 공부를 할 텐데.",
    "우리는 텐트를 빌릴 수 있고 우리 강아지를 돌봐줄 누군가를 찾을 수 있다.",
    "만약 컴퓨터가 없다면 나는 그것을 끝낼 수 없을 텐데.",
    "우리는 우리의 눈들을 태양으로부터 보호할 수 있기 위해서 선글라스를 쓴다.",
    "그것은 반려동물 소유자들이 자신들의 반려동물들을 돌봐줄 신뢰할 만한 사람들을 찾는 것을 도와준다.",
    "과거에는 로봇들은 인간들이 그들에게(로봇들에게) 하라고 프로그램한 쉬운 과제들만 수행했다.",
    "AI를 가진 로봇들은 환경들을 인지하고 결정들을 만든다.",
    "한 로봇 떼는 서로서로 의사소통할 수 있는 로봇들의 한 거대한 집단이다.",
  ];
  var answers = [
    "This App helps people easily find items that they can borrow from others.",
    "The more people use the services, the more they will improve.",
    "It is an app where you can find items that you can borrow from others.",
    "The more complex the problem is, the longer it takes to solve it.",
    "The more popular she becomes, the more money she will make.",
    "Never having flown on a plane before, I became nervous.",
    "Born in England, he now looks upon Paris as his hometown.",
    "Generally speaking, bigger animals live longer than smaller animals.",
    "Peter having finished dinner, we went out for a walk.",
    "The celebrities arriving and taking seats, the party began.",
    "She should have developed her own style instead of copying him.",
    "The government should try to help our economy grow.",
    "I try not to give out my personal information.",
    "We record the amount of time that people have off work because of sickness.",
    "Some artificial flowers were used to decorate the living room.",
    "Travelers usually navigated by the stars in the old days.",
    "Natural disasters, such as floods and earthquakes, affect thousands of people every year.",
    "This dictionary is available in electronic form.",
    "The siren was a signal for everyone to leave the building.",
    "Every car is equipped with an airbag.",
    "Some people expect life to become more convenient with the help of robots.",
    "Search-and-rescue robots can go into disaster areas that are dangerous for humans.",
    "My sister saved money so that she could buy the luxurious bag.",
    "If my cat could open the fridge, it would eat all my food.",
    "To fix this issue, we are asking lenders to update the pictures of their items regularly.",
    "If she were not tired, she could study all night.",
    "We can borrow a tent and find someone to take care of our dog.",
    "If it were not for the computer, I could not finish it.",
    "We wear sunglasses so that we can protect our eyes from the sun.",
    "It helps pet owners find reliable people to look after their pets.",
    "In the past, robots performed only easy tasks that humans programmed them to do.",
    "Robots that have AI can perceive environments and make decisions.",
    "A robot swarm is a large group of robots that can communicate with one another.",
  ];
</script>
{% include quiz.html %}

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

```
1. 이 앱은 사람들이 다른 사람들로부터 빌릴 수 있는 물건들을 쉽게 찾도록 돕는다.
This App helps people easily find items that they can borrow from others.

2. 더 많은 사람들이 그 서비스들을 사용할수록, 그것들이 더 개선될 것이다.
The more people use the services, the more they will improve.

3. 그것은 네가 다른 사람들로부터 빌릴 수 있는 물건들을 찾을 수 있는 앱이다.
It is an app where you can find items that you can borrow from others.

4. 그 문제가 더 복잡할수록, 그것을 푸는 데 시간이 더 오래 걸린다.
The more complex the problem is, the longer it takes to solve it.

5. 그녀가 더 유명해질수록, 그녀는 더 많은 돈을 벌 것이다.
The more popular she becomes, the more money she will make.

6. 전에 한 번도 비행기로 날아간 적이(비행기를 탄 적이) 없었으므로 나는 긴장되었다.
Never having flown on a plane before, I became nervous.

7. 영국에서 태어났지만, 그는 지금 파리를 그의 고향으로 여긴다.
Born in England, he now looks upon Paris as his hometown.

8. 일반적으로 말해, 더 큰 동물들이 더 작은 동물들보다 더 오래 산다.
Generally speaking, bigger animals live longer than smaller animals.

9. 피터가 저녁을 다 먹었기 때문에, 우리는 산책을 했다.
Peter having finished dinner, we went out for a walk.

10. 그 유명인들이 도착하여 자리들에 앉자, 파티가 시작되었다.
The celebrities arriving and taking seats, the party began.

11. 그녀는 그를 모방하는 대신에 그녀 자신의 스타일을 개발했어야 했다.
She should have developed her own style instead of copying him.

12. 정부는 우리 경제가 성장하도록 돕기 위해 노력을(시도를) 해야 한다.
The government should try to help our economy grow.

13. 나는 내 개인 정보를 나누어 주지(알려 주지) 않으려고 노력한다.
I try not to give out my personal information.

14. 우리는 병으로 인해 사람들이 쉬는(퇴근하는/휴가를 내는) 시간의 양을 기록한다.
We record the amount of time that people have off work because of sickness.

15. 약간의 조화들이 거실을 장식하기 위해 사용되었다.
Some artificial flowers were used to decorate the living room.

16. 예전에는 여행자들이 대개 별들에 의해 길을 찾았다.
Travelers usually navigated by the stars in the old days.

17. 홍수들과 지진들과 같은 자연 재해들은 매년 수천 명의 사람들에게 영향을 준다.
Natural disasters, such as floods and earthquakes, affect thousands of people every year.

18. 이 사전은 전자 형식으로 구할 수 있다.
This dictionary is available in electronic form.

19. 사이렌은 모두가 건물을 떠나라는 신호였다.
The siren was a signal for everyone to leave the building.

20. 모든 차는 에어백을 갖추고 있다.
Every car is equipped with an airbag.

21. 몇몇 사람들은 로봇들의 도움으로 인생이 더욱 편안해지기를 기대한다.
Some people expect life to become more convenient with the help of robots.

22. 수색구조 로봇들은 인간들에게 위험한 재난지역들로 들어갈 수 있다.
Search-and-rescue robots can go into disaster areas that are dangerous for humans.

23. 내 여동생은 그 고급스러운 가방을 살 수 있기 위해서 돈을 모았다.
My sister saved money so that she could buy the luxurious bag.

24. 만약 내 고양이가 그 냉장고를 열 수 있다면 그것은 내 음식 모두를 먹을 텐데.
If my cat could open the fridge, it would eat all my food.

25. 이 문제를 해결하기 위해서, 우리는 빌려주는 사람들에게 주기적으로 자신들의 물품들의 사진들을 업데이트할 것을 요청하고 있다.
To fix this issue, we are asking lenders to update the pictures of their items regularly.

26. 그녀가 피곤하지 않다면 그녀는 밤새 공부를 할 텐데.
If she were not tired, she could study all night.

27. 우리는 텐트를 빌릴 수 있고 우리 강아지를 돌봐줄 누군가를 찾을 수 있다.
We can borrow a tent and find someone to take care of our dog.

28. 만약 컴퓨터가 없다면 나는 그것을 끝낼 수 없을 텐데.
If it were not for the computer, I could not finish it.

29. 우리는 우리의 눈들을 태양으로부터 보호할 수 있기 위해서 선글라스를 쓴다.
We wear sunglasses so that we can protect our eyes from the sun.

30. 그것은 반려동물 소유자들이 자신들의 반려동물들을 돌봐줄 신뢰할 만한 사람들을 찾는 것을 도와준다.
It helps pet owners find reliable people to look after their pets.

31. 과거에는 로봇들은 인간들이 그들에게(로봇들에게) 하라고 프로그램한 쉬운 과제들만 수행했다.
In the past, robots performed only easy tasks that humans programmed them to do.

32. AI를 가진 로봇들은 환경들을 인지하고 결정들을 만든다.
Robots that have AI can perceive environments and make decisions.

33. 한 로봇 떼는 서로서로 의사소통할 수 있는 로봇들의 한 거대한 집단이다.
A robot swarm is a large group of robots that can communicate with one another.
```