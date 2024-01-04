# 프롬프트
## ClassName 추가
아래 svg를 다음과 같이 만들어줘

```
1. 모든 id를 삭제해줘
2. style 대신 className 속성을 넣어줘
3. className은 줄을 기준으로 넣어줘
  * 줄을 숫자 3으로 나눴을 때 나머지가 1이면 graph-type-selector--graphic-line graphic-line-a
  * 줄을 숫자 3으로 나눴을 때 나머지가 2이면 graph-type-selector--graphic-line graphic-line-b
  * 줄을 숫자 3으로 나눴을 때 나머지가 0이면 graph-type-selector--graphic-line graphic-line-c
4. 모든 줄에 요소를 복사해서 className만 다르게 넣어줘
  * 줄을 숫자 3으로 나눴을 때 나머지가 1이면 graph-type-selector--graphic-fill graphic-fill-a
  * 줄을 숫자 3으로 나눴을 때 나머지가 2이면 graph-type-selector--graphic-fill graphic-fill-b
  * 줄을 숫자 3으로 나눴을 때 나머지가 0이면 graph-type-selector--graphic-fill graphic-fill-c

<rect style="fill:#000000;stroke-width:0.884114" id="rect18-7-2" width="14.271025" height="14.34057" x="14.3217" y="73.18074"/>
<rect style="fill:#000000;stroke-width:0.734077" id="rect18-2-3" width="14.271025" height="9.8862782" x="14.3217" y="63.292175"/>
<rect style="fill:#000000;stroke-width:0.548165" id="rect18-75" width="14.271025" height="5.5127759" x="14.3217" y="57.777096"/>
<rect style="fill:#000000;stroke-width:1.10048" id="rect18-7" width="14.271025" height="22.218489" x="28.593094" y="65.302826"/>
<rect style="fill:#000000;stroke-width:0.913726" id="rect18-2" width="14.271025" height="15.317253" x="28.593094" y="49.982025"/>
<rect style="fill:#000000;stroke-width:0.682315" id="rect18" width="14.271025" height="8.5411901" x="28.593094" y="41.437267"/>
<rect style="fill:#000000;stroke-width:1.42063" id="rect18-7-9" width="14.271025" height="37.025925" x="42.864487" y="50.495388"/>
<rect style="fill:#000000;stroke-width:1.17954" id="rect18-2-7" width="14.271025" height="25.525379" x="42.864487" y="24.964092"/>
<rect style="fill:#000000;stroke-width:0.681016" id="rect18-1" width="14.271025" height="8.5087109" x="42.864487" y="16.449451"/>
<rect style="fill:#000000;stroke-width:1.30696" id="rect18-7-1" width="14.271025" height="31.33844" x="57.13588" y="56.182873"/>
<rect style="fill:#000000;stroke-width:1.08517" id="rect18-2-5" width="14.271025" height="21.604473" x="57.13588" y="34.573395"/>
<rect style="fill:#000000;stroke-width:0.690936" id="rect18-3" width="14.271025" height="8.7583923" x="57.13588" y="25.809984"/>
<rect style="fill:#000000;stroke-width:1.44994" id="rect18-7-1-5" width="14.271025" height="38.570389" x="71.407272" y="48.950924"/>
<rect style="fill:#000000;stroke-width:1.20388" id="rect18-2-5-4" width="14.271025" height="26.590122" x="71.407272" y="22.354647"/>
<rect style="fill:#000000;stroke-width:0.713739" id="rect18-3-5" width="14.271025" height="9.346035" x="71.407272" y="13.002437"/>
```
