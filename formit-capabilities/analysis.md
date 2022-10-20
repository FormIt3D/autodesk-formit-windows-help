---
설명: >-
  설계 프로세스 초기부터 요소의 성능을 평가하여 BIM 워크플로우를 시작할 수 있습니다.
---

# 일조 + 에너지 해석

\![](<../.gitbook/assets/20220317 Solar Analysis.png>)

## FormIt에서 에너지 해석

설계 프로세스 초기에 건물 모델의 에너지 효율성을 해석합니다.

[Insight 프로젝트 보기](https://gbs.autodesk.com/OneEnergy/Insight)

## Insight를 사용한 에너지 해석

**AEC 컬렉션**을 통해 [FormIt Pro](https://www.autodesk.com/collections/architecture-engineering-construction/overview) 멤버쉽에 가입하면 **Insight**를 사용하여 에너지 해석에 액세스할 수 있습니다.

* Green Building Studio의 해석 엔진으로 초기 단계 설계 모델을 해석합니다.
* 해석 결과의 대시보드 뷰에 연결하여 설계 옵션을 비교합니다.
* 창 대 벽 비율, 건물 방향 등의 에너지 해석 계수 위젯을 조정합니다.
* 면적당 최종 가격으로 계산된 단일 수치로 건물의 에너지 영향을 요약합니다.
* 고객 및 기타 이해 관계자와 함께 향후 검토할 수 있도록 에너지 해석 결과를 저장합니다.

## FormIt + Insight의 새로운 기능 <a href="#insight-what-s-new" id="insight-what-s-new"></a>

### **Insight 안정성 개선** <a href="#improvements-to-insight-reliability" id="improvements-to-insight-reliability"></a>

* [FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021)에서는 이제 Insight 실행을 시작하기 전에 모델에 일반적인 모델 문제가 없는지 확인하고 일반적인 Insight 오류를 수정하여 더욱 안정적인 환경을 제공합니다.
* 또한 FormIt 2021은 일반적으로 FormIt + Insight 연결의 안정성을 개선하여 알려진 여러 오류를 해결하고 실행 성공률을 향상합니다.

## 시작하기 <a href="#insight-getting-started" id="insight-getting-started"></a>

### **작동 방식** <a href="#how-it-works" id="how-it-works"></a>

* Insight 에너지 해석은 FormIt 모델 데이터를 업로드하고, 클라우드에서 수백 개의 해석을 실행하여 다양한 에너지 점수를 확인합니다.
* 에너지 해석은 Revit을 사용하여 모델을 해석합니다. 따라서 FormIt 데이터를 Revit으로 보낼 때처럼 [FormIt 모델이 수밀 및 매니폴드인지 확인](https://formit.autodesk.com/blog/post/repairing-solid-models)해야 합니다.

### **FormIt 모델 준비하기** <a href="#preparing-your-formit-model" id="preparing-your-formit-model"></a>

* Insight는 FormIt 스케치에 표시되는 모든 형상을 사용합니다.
  * 해석하려는 건물 쉘이 유일하게 표시되는 형상인지 확인합니다.
  * 환경, 가구 및 대지 요소와 같은 지지 형상을 별도의 [레이어](../tool-library/layers.md)에 배치하고 레이어를 끕니다.
* Insight는 단순한 솔리드 건물 모델에 가장 효과적입니다.
  * 건물 매스가 [솔리드 및 수밀](https://formit.autodesk.com/blog/post/repairing-solid-models)인지 확인합니다.
  * 건물 설계에 창과 문을 위한 개구부가 이미 있는 경우, 에너지 해석을 위해 특별히 개구부가 없는 새 매스를 작성하고 레이어를 사용하여 자세한 버전을 숨기는 것이 가장 좋습니다.
* 단순 건물 매스에는 [레벨](../tool-library/levels-and-area.md)이 적용되어 있어야 합니다.
* FormIt 모델에는 [위치](../tool-library/setting-location.md) 세트가 있어야 합니다.

![](../.gitbook/assets/insight.png)

### **에너지 해석 시작** <a href="#starting-energy-analysis" id="starting-energy-analysis"></a>

* 도구막대에서 에너지 해석 버튼을 찾습니다.

![](../.gitbook/assets/generate\_insight.png)

* "Insight 생성"을 클릭하여 프로세스를 시작합니다.
* 그러면 보이는 모델 데이터가 업로드되고 클라우드에서 수백 개의 시뮬레이션이 실행됩니다.
* 실행이 완료되면 화면 상단에 메시지가 나타나고, 새 Insight를 볼 준비가 되었음을 나타내도록 메뉴가 업데이트됩니다.
  * "Insight 보기"를 클릭하여 웹 브라우저에서 해석을 봅니다.
  * [Autodesk Insight](https://gbs.autodesk.com/OneEnergy/Insight)에서 모든 인사이트를 찾을 수도 있습니다.

## 문제 해결 <a href="#insight-troubleshooting" id="insight-troubleshooting"></a>

### **일반적인 오류** <a href="#common-errors" id="common-errors"></a>

* "Insight 프로젝트를 작성할 수 없습니다. 나중에 다시 시도하십시오."
  * [Green Building Studio 대시보드](https://gbs.autodesk.com/GBS/Project)에 로그인한 후 FormIt을 다시 시작합니다.
    * 로그인할 수 없거나 "액세스가 거부됨" 페이지가 표시되면 [Green Building Studio 멤버쉽을 구입](https://knowledge.autodesk.com/search-result/caas/CloudHelp/cloudhelp/KOR/BPA-Help/files/GUID-7FCFF904-F943-4020-BF7F-53AA7148673D-htm.html)해야 할 수 있습니다.
  * 모델이 [솔리드 및 수밀](https://formit.autodesk.com/blog/post/repairing-solid-models)인지 확인합니다.
  * [Autodesk 상태 대시보드](https://health.autodesk.com/)에서 FormIt 서비스 관련 문제를 확인합니다．
* Green Building Studio가 이 프로젝트에 대해 에너지 해석을 성공적으로 실행했는지 확인하려면 [Green Building Studio 대시보드](https://gbs.autodesk.com/GBS/Project)를 살펴보십시오.
  * 최신 프로젝트가 리스트 맨 위에 표시되고 248개의 실행이 표시되어야 합니다.
  * 실행이 0개가 표시되면 [FormIt 포럼에서 알려주십시오](https://forums.autodesk.com/t5/formit-forum/bd-p/142). 그러면 문제를 추가로 해결하는 데 필요한 도움을 받을 수 있습니다.

### **상세 로그** <a href="#detailed-logs" id="detailed-logs"></a>

* FormIt 웹은 에너지 해석에 실패할 때 추가 상세 정보를 제공합니다.
  * [FormIt 웹](https://formit.autodesk.com/app)으로 이동합니다.
  * 에너지 해석에 문제가 있는 모델을 엽니다.
  * 에너지 해석을 실행합니다.
  * 개발자 도구를 엽니다(Google Chrome 또는 Firefox에서 F12 키를 누름).
  * 콘솔 탭을 확인합니다.
  * 오류를 복사하거나 스크린샷으로 찍고 [FormIt 포럼에서 보고](https://forums.autodesk.com/t5/formit-forum/bd-p/142)합니다.

## 일조 해석

**AEC 컬렉션**을 통해 [FormIt Pro](https://www.autodesk.com/collections/architecture-engineering-construction/overview) 멤버쉽에 가입하면 건물에 미치는 태양의 영향을 시각화할 수 있습니다.

* 태양이 미치는 영향을 해석할 관련 면을 지정합니다.
* 앱 캔버스 내에서 몇 초 만에 결과를 시각화합니다.
* 입력 점 위에 마우스 커서를 놓으면 태양이 미치는 영향의 계산된 특정 값이 표시됩니다.
* 결과를 월간 유리 연구 또는 연간 일조 패널 적합성 연구로 보도록 선택할 수 있습니다.

FormIt Pro에서 [일조 해석](../tool-library/solar-analysis.md)에 대해 자세히 알아보십시오.
