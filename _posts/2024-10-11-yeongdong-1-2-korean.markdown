---
layout: post
title:  "영동 1-2 국어 중세국어 단어"
date:   2024-10-11 11:30:21 +0900
categories: [school]
permalink: /school/1/2/club/korean
---
<head>
<meta name="viewport" content="width=device-width*0.9, initial-scale=1.0">
<style>
  p { margin: 8px 0px 8px 0px; }
</style>
</head>

정답과 정확히 같아야 정답으로 인식합니다. <br>
복수정답은 인식하지 못합니다. <br>
<input type='checkbox' name='questionType' value='example' disabled>예문 삽입
<input type='checkbox' name='questionType' value='toKorean' disabled>단어:뜻
<input type='checkbox' name='questionType' value='toEnglish' checked>뜻:단어
<input type='checkbox' name='questionType' value='synonym' disabled>유/반의어
<p id="checkboxError">원하는 문제 종류를 1개 이상 선택하세요.</p>
<input type='checkbox' id="completeRandom" name='completeRandom' onClick="shuffleQuestion()">완전 랜덤 셔플
<input type='checkbox' id="onlyWrongMode" name='onlyWrongMode' onClick="wrongModeCheck()">지금까지 틀린단어만
<br>

<div> 
  <p id="questionText">문제</p>
  <input id="answerInput" type="text" style="width: 320px; font-size: 16px; height: 20px" placeholder=""> <button onclick="textEntered()">입력</button>
  <p id="grading" style="word-wrap:break-word; width: 325px">(정답 여부)</p> 
  <p id="wrongList" style="word-wrap:break-word; width: 325px">틀린 단어: X</p>
  <button onclick="forceCorrect()">정답 처리</button> <button onclick="skipQuestion()">문제 스킵</button>
  <p id="stats">맞은 문제 수: 0 / 0</p> 
  <p id="addMessage"> </p>
</div>

<br>

<div>
  <p>이곳에서 시험 단어를 변경할 수 있습니다. </p> <p id="listLoaded"></p>
<textarea id="wordList" cols="47" rows="10" placeholder="단어 목록">
# <- 이 기호로 시작하거나 빈 줄은 인식하지 않습니다.
# 띄어쓰기는 채점 중 인식되지 않습니다.
# 형식: 단어/뜻/유의어/반의어/예문(단어:'')
# 유/반의어는 없으면 그 단어의 유/반의어 문제는 출제되지 않습니다.
# 예시: fragile/깨지기 쉬운,덧없는/delicate,transient/firm/Owl is a 'fragile', graceful creature.

나리/물///
시내/물///
소반/밥상///
졍지/부엌///
즈즐/모습을///
별헤/벼랑에///
곶/꽃///
백구/흰 갈매기///
이화/배꽃 (흰색, 봄)///
도화/복숭아꽃 (붉은색)///
행화/살구꽃 (분홍빛)///
해오라비/해오라기, 하얀 백로///
뫼/산, 수라 (궁중용어)///
하얌(향암)/시골에 살아 세상 이치를 모르는 어리석은 사람///
소, 지당/연못///
시비/사립문///
실솔/귀뚜라미///
즌대/진 곳 (위험한 곳)///
여름/열매///
벽계수/푸른 시냇물///
녀름/여름///
관산/국경, 관문, 요새///
갓/끝///
촉/촛불///
녹양 / 양류/버드나무///
연하 / 금수/안개와 노을 / 수놓은 비단///
혜음(혬, 혬가림)/근심, 걱정, 시름///
남여/가마///
황운/누렇게 익은 곡식///
건곤/하늘과 땅///
모쳠/초가(의 처마)///
날애/날개///
이래/아양///
시앗/첩///
침선/바느질///
수품/솜씨, 실력, 능력///
잣/성///
파람/휘파람///
우음/웃음///
선하다/서운하다///
녀다(니다, 녜다)/가다, 지내다, 살아가다///
얼다/(육체적) 사랑하다///
괴다/(정신적) 사랑하다///
벼기다/우기다, 모함하다///
방송하다/내보내다, 석방하다///
늣기다(느끼다)/흐느끼다///
이슷하다/비슷하다///
혀다/(악기, 불)을 켜다///
어엿브다/불쌍하다///
싀어디여/사라져서, 죽어 없어져///
삼기다/생기다, 태어나다, 만들어지다///
끠우다/꺼리다///
여희다/이별하다, 헤어지다///
둏다(됴타)/좋다///
좋다(조타)/깨끗하다///
헌사하다/야단스럽다///
어리다/어리석다///
슬허하다/슬퍼하다///
외다/그르다, 잘못되다///
하다/많다, 크다///
쟐다/짧다///
수이/쉽게///
긋다/끊어지다///
닛다/이어지다///
오뎐된/방정맞은///
고두/머리를 조아리다///
오마 하다/온다고 한다///
가시다/변하다, 바뀌다///
자로/자주///
모쳐라/마침///
고텨/다시///
져근덧, 건듯/잠깐 사이에///
슬카장/실컷///
하마/이미, 벌써///
빗기(비겨)/비스듬히///
유세차/이해의 차례는///
~ㄹ셰라/~할까 두렵다///
~손대/~에게///
~다히(~다이)/~의,~쪽(~답게)///
~대/~곳(장소)///
~제/~때///
~카니와/물론이거니와///
~하/~야 (호격조사)///
~고져/~하고자 (소망, 의도)///
~다호라/~같구나///
</textarea>
  <br>
  <button onclick="shortList()">축소</button> <button onclick="longList()">확대</button> <button onclick="loadList()">로드</button> 
</div>

<br><br>

<button onclick="resetScore()">점수 리셋</button> <button onclick="resetWord()">단어 리셋</button>

{% include mariaWordQuiz.html %}
