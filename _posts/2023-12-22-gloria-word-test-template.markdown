---
layout: post
title:  "글로리아 단어 시험 템플릿"
date:   2023-12-22 17:01:38 +0900
categories: [Academy]
permalink: /academy/gloria/word/template
---


정답과 정확히 같아야 정답으로 인식합니다. <br>
복수정답은 쉼표로 구분하고, 순서가 구분됩니다. <br>
<input type='checkbox' name='questionType' value='example' checked>예문 삽입
<input type='checkbox' name='questionType' value='toKorean' checked>뜻:단어
<input type='checkbox' name='questionType' value='toEnglish' checked>단어:뜻
<input type='checkbox' name='questionType' value='synonym' checked>유/반의어
<p id="checkboxError">원하는 문제 종류를 선택하세요. 1개 이상 선택해야 합니다.</p>
<input type='checkbox' id="completeRandom" name='completeRandom' onClick="shuffleQuestion()">완전 랜덤 셔플
<input type='checkbox' id="onlyWrongMode" name='onlyWrongMode' onClick="wrongModeCheck()">지금까지 틀린단어만 풀기
<br>

<div> 
  <p id="questionText">문제</p>
  <input id="answerInput" type="text" style="width: 350px; font-size: 16px; height: 20px" placeholder=""> <button onclick="textEntered()">입력</button>
  <p id="grading">(정답 여부)</p> 
  <p id="wrongList">틀린 단어: X</p>
  <button onclick="forceCorrect()">정답 처리</button> <button onclick="skipQuestion()">문제 스킵</button>
  <p id="stats">맞은 문제 수: 0 / 0</p> 
  <p id="addMessage"> </p>
</div>

<br>

<div>
  <p>이곳에서 시험 단어를 변경할 수 있습니다. </p> <p id="listLoaded"></p>
<textarea id="wordList" cols="75" rows="10" placeholder="단어 목록">
# <- 이 기호로 시작하거나 빈 줄은 인식하지 않습니다.
# 띄어쓰기는 채점 중 인식되지 않습니다.
# 형식: 단어/뜻/유의어/반의어/예문(단어:'')
# 유/반의어는 없으면 그 단어의 유/반의어 문제는 출제되지 않습니다.
# 예시: fragile/깨지기 쉬운,덧없는/delicate,transient/firm/Owl is a 'fragile', graceful creature.

fragile/깨지기 쉬운,덧없는/delicate,transient/firm/Owl is a 'fragile', graceful creature.
perk/특전/benefit//'Perks' offered by the firm include a car and free health insurance.
hello/안녕///Say 'hello' to my sister.
예문에 ' 2개가 없거나, / 5개로 이루어지지 않은 문장은 오류처리 됩니다.
</textarea>
  <br>
  <button onclick="shortList()">축소</button> <button onclick="longList()">확대</button> <button onclick="loadList()">로드</button> 
</div>

<br><br>

<button onclick="resetScore()">점수 리셋</button> <button onclick="resetWord()">단어 리셋</button>

{% include gloriaWordQuiz.html %}


