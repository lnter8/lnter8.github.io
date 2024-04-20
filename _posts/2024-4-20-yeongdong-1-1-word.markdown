---
layout: post
title:  "영동 1-1 영어 단어"
date:   2024-4-20 11:30:21 +0900
categories: [school]
permalink: /school/1/1/english/word
---
<head>
<meta name="viewport" content="width=device-width*0.9, initial-scale=1.0">
<style>
  p { margin: 8px 0px 8px 0px; }
</style>
</head>

정답과 정확히 같아야 정답으로 인식합니다. <br>
복수정답은 인식하지 못합니다다. <br>
<input type='checkbox' name='questionType' value='example' disabled>예문 삽입
<input type='checkbox' name='questionType' value='toKorean' checked>단어:뜻
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

#Day 1
relieve/완화시키다, 안심시키다///
constant/변함없는, 계속되는, 상수///
identify/확인하다, 식별하다, 동일시하다///
subtle/미묘한, 미세한///
fright/공포, 놀람///
archaic/구식의, 낡은, 고대의///
precise/정확한, 정밀한///
allocate/할당하다, 배치하다///
manipulate/조종하다, 조작하다///
valid/타당한, 유효한, 효과적인///
virtual/사실상의, 가상의///
derive/유래하다, 추론하다
eliminate/제거하다, 없애다///
dominate/지배적인, 우세한, 두드러진///
moderate/중간의, 온건한, 완화하다, 조정하다///

#Day 2
prompt/자극하다, 재촉하다, 신속한, 즉각적인, 시간을 지키는///
desperate/절망적인, 필사적인, 절박한///
transmit/보내다, 전달하다, 옮기다, 전염시키다///
distinctive/독특한, 특색있는///
genuine/진짜의, 거짓이 아닌///
verbal/말의, 언어의, 구두의///
stroke/치기, 타격, 뇌졸중, 쓰다듬다, 어루만지다///
discipline/규율, 기강, 훈련, 징벌, 학과, 학문 분야, 훈련하다, 징계하다///
resolve/해결하다, 풀다, 결심하다, 결심, 결의, 의지///
tremendous/거대한, 굉장한, 굉장히 좋은///
retention/보유(력), 유지, 기억(력)///
static/정적인, 정지된///
assumption/가정, 추정, 장악, 떠맡기///
prospect/예상, 기대, 전망, 유망한 후보자///
reference/언급, 참고, 참조, 추천인, 추천서, 관련, 관계///

#Day 3
drain/액체를 배출하다, 고갈시키다, 소모시키다, 유출, 고가, 소모///
respective/저마다의, 각자의///
soar/높이 치솟다, 급상하다, 비상, 높이 날기///
equilibrium/평형, 균형, 마음의 평정///
prominent/툭 튀어나온, 현저한, 유명한, 탁월한///
intensify/강해지다, 강화하다///
compensate/보완하다, 메우다, 보상하다///
dismiss/쫒아내다, 해산하다, 해고하다, 기각하다///
elaborate/복잡한, 정교한, 정교하게 만들다///
profound/깊은, 심오한///
literal/글자 그대로의, 있는 그대로의///
alert/방심하지 않는, 경고하다, 주의하다, 경계 태세, 경보///
currency/통화, 화폐, 유통, 유행///
draft/초안, 원고, 통풍, 외풍, 징병, 선발///
extension/확대, 확장, 증축///

#Day 4
extract/뽑다, 추출하다, 발췌하다, 추출물, 발췌///
fierce/사나운, 거친, 맹렬한///
steep/가파른, 경사가 급한, 터무니 없는, 적시다, 담그다///
identical/동일한, 똑같은, 일란성의///
supplement/보충, 보완, 부록, 보충하다///
suspend/매달다, 걸다, 중지하다, 보류하다, 정학시키다///
depreciate/가치가 떨어지다, 평가 절하하다, 경시하다///
sublime/숭고한, 고상한, 웅장한///
deteriorate/악화시키다, 질을 떨어드리다, 쇠퇴하다///
grasp/꽉 잡다, 이해하다, 파악하다, 꽉 잡기, 파악///
inherit/물려받다, 상속받다///
recipient/수취인, 그릇///
shrink/줄어들다, 오그라들다, 움츠리다///
expertise/전문적 지식, 기술///
inferior/열등한, 더 못한, 하위의///

#Day 5
literary/문학의, 문학적인///
distort/비틀다, 왜곡하다///
optimal/최상의, 최선의, 최적의///
rear/기르다, 부양하다, 교육하다, 뒤, 후방///
skeptical/회의적인, 의심 많은///
empirical/경험적인, 경험상의///
ethnic/인종의, 민족의///
incorporate/포함하다, 통합하다, 구체화하다, 법안으로 만들다///
rationality/합리성, 이치에 맞음///
distract/주의를 다른 데로 돌리다, 산만하게 하다, 기분전환하다///
infer/추론하다, 추측하다, 결론을 내리다///
virtue/선, 덕, 선행, 가치, 장점///
subordinate/하위의, 종속된, 부하, 종속자, 종속시키다///
dilute/묽게 하다, 희석하다, 희박하게 하다///
evoke/불러일으키다, 일깨우다, 환기시키다///
</textarea>
  <br>
  <button onclick="shortList()">축소</button> <button onclick="longList()">확대</button> <button onclick="loadList()">로드</button> 
</div>

<br><br>

<button onclick="resetScore()">점수 리셋</button> <button onclick="resetWord()">단어 리셋</button>

{% include mariaWordQuiz.html %}
