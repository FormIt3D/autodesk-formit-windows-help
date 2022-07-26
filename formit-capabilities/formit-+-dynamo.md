---
description: Computational Design in FormIt
---

# FormIt + Dynamo

![](<../.gitbook/assets/20181213 formit + dynamo hero image.png>)

Windows용 FormIt에는 유용한 계산 설계 워크플로우를 지원하는 Dynamo가 내장되어 있습니다.

## FormIt + Dynamo의 새로운 기능

### **데이터 그래프, Excel로 레벨 전송 및 면분할 제어**

[FormIt 2023](https://formit.autodesk.com/blog/post/introducing-formit-2023/)에서는[ SendToFormIt 노드 없이](formit-+-dynamo.md#graph-types) Dynamo 그래프를 실행하는 기능을 지원하고, [FormIt 레벨을 Excel로 전송](formit-+-dynamo.md#send-formit-levels-to-excel)하고 [새 FormItGroupOptions 노드를 통해 곡선 및 표면 면분할](../tool-library/curve-+-surface-faceting.md)을 제어하는 기능이 추가되었습니다.

### **치수 입력 및 JS API의 얼리 액세스**

[FormIt 2022.1](https://formit.autodesk.com/blog/post/introducing-formit-2022-1)에는 [친숙한 FormIt 치수를 입력](https://formit.autodesk.com/page/formit-dynamo#dynamo-input-nodes)으로 사용하는 기능이 추가되고, [객체 레벨 옵션](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-options-nodes)이 도입되고, [JavaScript API 액세스](https://formit.autodesk.com/page/formit-dynamo#dynamo-js-api-nodes)를 먼저 이용할 수 있는 미리보기가 제공됩니다. [여기](https://formit.autodesk.com/page/download)에서 다운로드십시오.

### **다중 SendToFormIt 노드**

[FormIt 2021.3](https://formit.autodesk.com/blog/post/introducing-formit-2021-3)에는 [여러 SendToFormIt 노드 및 내포된 Dynamo 그래프](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups)를 사용하는 기능이 추가되었습니다.

### **SelectFromFormIt 노드**

[FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021)에는 [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 노드가 추가되어 항상 연결된 세션, 다중 인스턴스 편집 등을 지원합니다.

## 시작하기

인터페이스에 대해 알아보고 Dynamo 디렉토리를 FormIt에 연결합니다.

### **초기 설정**

FormIt + Dynamo를 처음 사용해 보십니까? Dynamo에서 3D 캔버스를 보려면 먼저 [시스템을 구성](https://formit.autodesk.com/page/formit-dynamo#dynamo-important-notes)해야 합니다.

### **Dynamo 패널**

Dynamo 패널을 사용하여 Dynamo를 시작하고, Dynamo 그룹을 배치하고, Dynamo 그래프를 편집할 수 있습니다.

![Dynamo panel](<../.gitbook/assets/dynamo\_dynamopanel (1).png>)

### **로컬 Dynamo 디렉토리 추가 및 관리**

* Dynamo 패널은 [컨텐츠 라이브러리](https://windows.help.formit.autodesk.com/building-the-farnsworth-house/import-export-and-content-library)와 동일하게 작동합니다. 따라서 이를 통해 Dynamo 파일이 포함된 로컬 디렉토리를 링크하고 관리할 수 있습니다.
* Dynamo 패널에서 "디렉토리 링크" 버튼을 클릭한 다음, 기본 설정 대화상자에서 (+)를 다시 클릭하여 FormIt에 링크할 디렉토리를 선택할 수 있습니다. <img src="../.gitbook/assets/dynamo_selectdirectory.png" alt="" data-size="line">
* 드롭다운을 사용하여 링크된 디렉토리 간을 전환할 수 있습니다.

![](../.gitbook/assets/dynamo\_dropdown.png)

* Dynamo 패널을 통해서만 .dyn 파일 및 하위 폴더를 볼 수 있습니다.
* 필터 막대를 사용하여 Dynamo 파일 및 하위 폴더를 필터링하면 필요한 항목을 쉽게 찾을 수 있습니다.

![](../.gitbook/assets/dynamo\_filter.png)

## Dynamo의 다양한 기능

Dynamo에서 그래프를 작성 및 편집하거나, 그래프를 표시하지 않고 FormIt에서 매개변수를 조정할 수 있습니다. 또는 두 가지 작업을 동시에 수행할 수도 있습니다!

### **그래프 유형**

FormIt은 다음 세 가지 유형의 Dynamo 그래프를 지원합니다.

* 데이터 그래프: 데이터 그래프에는 _SendToFormIt_ 노드가 없습니다. 데이터 그래프를 사용하면 FormIt을 통해 데이터를 표면화하거나 전달할 수 있습니다. 예를 들어, 데이터 그래프를 사용하여 Excel로 데이터를 보내거나 비기하학적 데이터를 계산하여 Watch 노드에 표시할 수 있습니다.
* 형상 그래프: 형상 그래프는 즉시 형상을 생성합니다. 해당 매개변수를 확인하려면 형상 그래프를 캔버스에 배치해야 합니다. 썸네일을 클릭하면 형상이 커서에 나타나 3D 장면에 배치할 수 있습니다. 이 그래프를 사용하려면 하나 이상의 _SendToFormIt_ 노드가 있어야 하고 그래프의 끝에서 형상을 수신해야 합니다.
* 선택 그래프: 선택 그래프는 실행하기 전에 FormIt을 선택해야 합니다. 선택해야 하는 항목을 나타내는 프롬프트가 FormIt의 왼쪽 상단 코너에 표시됩니다. 항목을 선택하면 그래프가 실행되고 선택에 따라 형상이 생성됩니다. 이 그래프를 사용하려면 하나 이상의 _SendToFormIt_ 노드가 있어야 하고 그래프의 끝에서 형상을 수신해야 합니다.

![](../.gitbook/assets/dynamo-graph-types.png)

### **형상 그래프: Dynamo 그룹을 FormIt에 배치**

![](../.gitbook/assets/dynamo\_stairsgif.gif)

* Dynamo 패널에서 실행할 Dynamo 그래프의 썸네일을 클릭합니다.
   * 내장된 샘플을 사용하거나 보유 중인 Dynamo 파일의 [라이브러리를 연결](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started)할 수 있습니다.
* 형상을 FormIt에 배치하면 Dynamo 그래프의 사본이 FormIt 파일에 포함됩니다.
   * 형상을 생성하려면 그래프의 출력 형상 노드에 [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 노드를 부착해야 합니다.
* SendToFormIt 노드의 형상은 배치할 수 있도록 커서에 표시됩니다.
   * 그래프에 '입력임'이라고 표시된 [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 노드가 있으면, FormIt은 먼저 선택을 요청하며(각 선택 노드는 세로 순서로 되어 있음) 선택에 따라 올바른 위치에 형상을 생성합니다.
* 원본 Dynamo 파일의 사본이 이제 FormIt 그룹에 포함되고, 소스 그래프에서 독립됩니다.
* 배치 시 특성 패널이 자동으로 전환되어 사용 가능한 매개변수가 표시됩니다.

### **형상 그래프: 매개변수 수정**

![](../.gitbook/assets/dynamo\_stairsgif2\_modifyparameters.gif)

* Dynamo 그룹을 배치한 후 선택하고 특성 패널로 전환하거나 그룹을 간단히 두 번 클릭하여 특성으로 자동 전환합니다.
   * Dynamo에서 "입력임"으로 표시된 모든 입력 노드가 여기에 나열됩니다.
   * [**SelectFromFormIt**](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 입력 노드는 맨 위에 버튼으로 표시됩니다. 이 입력 노드를 사용하여 그래프를 실행하는 데 사용되는 선택을 업데이트할 수 있습니다.
   * FormIt은 Number Slider, Integer Slider, Boolean Toggle 같은 입력 노드와 Number/String 필드를 지원합니다.
* FormIt에서 입력을 변경한 다음, 실행을 클릭합니다. 실행 버튼이 파란색으로 바뀌어 매개변수가 수정되었으며 그래프를 실행해야 함을 나타냅니다.
   * Dynamo는 백그라운드에서 실행되어 변경 사항을 처리하고 FormIt에서 업데이트된 형상을 반환합니다.
   * FormIt 2022 이상에서는 특성 패널에서 첫 실행이 이루어지면 전용 Dynamo 인스턴스가 작동되므로, 이후의 편집 속도가 훨씬 빨라집니다.
   * Dynamo를 실행하는 동안 FormIt을 계속 사용할 수 있습니다.&#x20;
* 각 SendToFormIt Group 내의 모든 형상은 Dynamo 그래프가 실행될 때 삭제되고 대치됩니다.

### 데이터 그래프: FormIt 레벨을 Excel로 보내기

FormIt 2023 이상에서는 Dynamo를 사용하여 FormIt 레벨을 Excel로 보낼 수 있습니다.&#x20;

* [여기에서 샘플 Dynamo 그래프](https://formit-help.s3.amazonaws.com/Send+Levels+to+Excel.dyn)를 다운로드합니다.
* Dynamo 팔레트의 위치를 Dynamo 그래프가 저장된 로컬 디렉토리로 지정합니다.
* 썸네일을 마우스 오른쪽 버튼으로 클릭하고 _포함된 그래프 편집을 클릭합니다._
* 임의 위치에 빈 Excel 스프레드시트를 작성합니다.
* 스프레드시트 위치 필드를 편집하여 Excel 스프레드시트의 경로를 사용합니다.
* 시트 이름 등 원하는 다른 필드를 편집합니다.
* Dynamo를 닫고 그래프를 저장합니다.

이제 팔레트에서 예제 파일을 클릭하기만 하면 형상을 생성할 필요 없이 FormIt에서 실행됩니다.&#x20;

Dynamo 입력이 Dynamo 팔레트에 나타나고, Excel이 열리며 그래프의 결과가 표시됩니다.&#x20;

모델을 변경할 때 그래프 썸네일 또는 _실행_ 버튼을 다시 클릭하여 최신 버전의 FormIt 스케치의 레벨 데이터로 스프레드시트를 업데이트할 수 있습니다.

![](../.gitbook/assets/dynamo-send-levels-to-excel.gif)

### 새 Dynamo 창 시작

![](../.gitbook/assets/dynamo\_launchwindow.gif)

* FormIt 2021 이상에서는 Dynamo 패널에서 Dynamo 시작 버튼을 클릭하면 FormIt과 연결된 세션이 자동으로 시작됩니다.
   * 이렇게 하면 Dynamo에서 그래프 템플릿이 열리고, FormIt에서 템플릿 형상이 자동으로 생성됩니다.
   * 결과 형상은 현재 그룹 편집 컨텍스트의 원점에서 새 그룹으로 나타납니다. Dynamo를 시작하기 전에 원하는 그룹 컨텍스트에 있는 것이 가장 좋습니다.&#x20;
   * 템플릿에는 FormIt 노드와 일부 예제 형상이 모두 포함되어 있습니다. 슬라이더를 조정하면 두 응용프로그램에서 모두 정육면체의 크기가 조정됩니다.
   * 여기에서 다른 Dynamo 그래프를 열거나, 템플릿의 이러한 기본 구성요소를 사용하여 새로운 항목을 작성하고 Dynamo에서 새 위치에 다른 이름으로 저장할 수 있습니다.

### **포함된 그래프 + 소스 그래프 편집**

기존 Dynamo 그래프는 두 가지 다른 방법으로 편집할 수 있습니다. FormIt에 이미 배치되어 있는 포함된 그래프를 편집하거나 컴퓨터에 저장된 소스 그래프를 편집하는 것입니다.

### **포함된 그래프**

Dynamo 객체를 FormIt에 배치하면 해당 기본 그래프가 복사되어 현재 FormIt 파일에 포함됩니다. Dynamo에서 이 편집 작업은 **포함된 그래프 편집** 버튼을 통해 수행됩니다.

![](../.gitbook/assets/dynamo\_embeddedgraph.png)

![](../.gitbook/assets/dynamo\_editgraphgif.gif)

* Dynamo 그룹을 선택하고 특성 패널로 전환하거나 그룹을 간단히 두 번 클릭하여 특성으로 자동 전환합니다.
* **포함된 그래프 편집** 버튼을 클릭합니다.
* Dynamo의 맨 위에 있는 파일 이름은 이제 "(FormIt)"을 포함합니다. 즉, 소스 그래프를 수정하지 않고 이 FormIt 파일에 포함된 그래프를 편집하게 됩니다.
* 하나 이상의 [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 노드가 FormIt으로 보낼 형상에 연결되어 있는지 확인합니다.
* 그래프를 조정하면 FormIt에 형상 업데이트가 실시간으로 표시됩니다.
* Dynamo에서 변경 사항을 저장하지 않으면 FormIt은 마지막으로 저장한 Dynamo 그래프 버전으로 롤백합니다.
* 각 SendToFormIt Group 내의 모든 형상은 Dynamo 그래프가 실행될 때 삭제되고 대치됩니다.

### **소스 그래프**

소스 그래프는 [로컬 디렉토리를 연결](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started)한 후 Dynamo 패널에 표시됩니다. 이러한 그래프는 컴퓨터에 저장되며, 소스 그래프 편집 버튼을 클릭하여 Dynamo에서 편집할 수 있습니다.

![](../.gitbook/assets/dynamo\_editsourcegraph.png)

![](../.gitbook/assets/dynamo\_sourcegraphgif.gif)

* Dynamo 파일이 포함된 [디렉토리를 Dynamo 패널에 연결](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started)한 다음, 패널에서 해당 위치로 이동합니다.&#x20;
* 편집하려는 Dynamo 그래프의 썸네일을 마우스 오른쪽 버튼으로 클릭하고(또는 화살표를 클릭) **소스 그래프 편집** 버튼을 선택합니다.
* 요청된 그래프가 열려 있는 상태에서 Dynamo가 시작되고, FormIt에 그래프의 최종 출력의 형상이 표시됩니다.
   * 하나 이상의 [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 노드를 입력으로 사용하는 그래프의 경우, SelectFromFormIt 노드가 선택 항목으로 채워질 때까지 결과 형상이 표시되지 않을 수 있습니다.
* 결과 형상은 현재 그룹 편집 컨텍스트의 원점에서 새 그룹으로 나타납니다.
   * 소스 그래프 편집을 클릭하기 전에 원하는 그룹 컨텍스트에 있는 것이 가장 좋습니다.
* 편집을 마치면 Dynamo를 저장하고 닫습니다. FormIt에서 소스 그래프가 복사되고 FormIt 파일에 포함됩니다.
   * **소스 그래프**를 더 많이 편집해야 하는 경우 포함된 사본을 삭제하고 다음 단계를 다시 수행합니다.

### **곡선 + 표면 면분할 제어**

*   FormIt 2023부터 FormItGroupOptions 노드의 SetCurveFacetingCount 및 SetSurfaceFacetingCount를 사용하여 SendToFormIt 노드에 부착된 곡선 및 표면의 면분할을 제어할 수 있습니다.

    <img src="../.gitbook/assets/dynamo-formitgroupoptions-faceting-nodes.png" alt="" data-size="original">
* 이러한 노드는 전역 곡선 및 표면 면분할 설정을 재지정하며, 이 설정은 편집 -> 기본 설정 -> 단위 + 정확도에서 정의할 수 있습니다.
* 이 기능은 Dynamo 그래프에서 특정 면분할 값을 사용하여 곡선 객체를 생성해야 하는 경우 매우 유용합니다. 즉, 현재 세션에서 실행되는 각 Dynamo 그래프에 대한 전역 설정을 변경할 필요성이 줄어듭니다.

![](../.gitbook/assets/dynamo-formitgroupoptions-faceting.gif)

* 편집 -> 기본 설정 -> 단위 + 정밀도에서 면분할 설정을 전역으로 설정할 수도 있습니다.
* 기본 설정에서 면분할 품질을 조정한 후 그래프를 다시 실행하여 새 전역 면분할 설정을 사용할 수 있습니다.

![](../.gitbook/assets/dynamo\_controlcurve.gif)

[FormIt의 곡선 및 표면 면분할 설정에 대해 자세히 알아보십시오.](https://windows.help.formit.autodesk.com/tool-library/curve-+-surface-faceting)

## Dynamo에서 FormIt 그룹 사용

FormIt 그룹의 강력한 기능을 이용해 Dynamo 형상 구성을 개선하고 유용한 워크플로우를 구현할 수 있습니다.

### **그룹 및 SelectFromFormIt 노드**

* [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 노드의 형상을 선택하는 경우 FormIt 그룹에 형상을 저장하고 그룹을 대신 선택하는 것이 유용합니다.
   * 이렇게 하면 선택한 FormIt 그룹의 컨텐츠를 유연하게 변경할 수 있습니다. 따라서 그룹을 참조하는 그래프를 다시 실행하기만 하면 업데이트된 결과를 확인할 수 있습니다.
* 그룹 해제된 형상을 선택하고 해당 형상을 변경하면 다음에 그래프를 실행할 때 형상을 다시 선택하라는 메시지가 FormIt에 표시될 수 있습니다.

### **그룹에 형상 생성**

* Dynamo 그래프가 FormIt에서 실행되면 기하학적 결과가 FormIt 그룹에 포함됩니다.
* 그래프의 각 [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 노드는 노드 입력 포트의 형상을 포함하는 하위 그룹을 작성합니다.
* FormIt에서 Dynamo 객체를 생성하면, 전체 그래프와 해당 매개변수가 FormIt 파일에 사본으로 포함됩니다.
* 그래프가 실행되면 각 하위 그룹 내의 형상이 삭제된 후 재생성됩니다.
   * 형상을 수정하거나 하위 그룹 내의 표면을 페인팅하면 다음에 Dynamo 그래프를 실행할 때 변경 사항이 손실되므로 주의해야 합니다.
   * 그러나 FormIt 재료를 사용하여 하위 그룹(내부에 포함된 형상 아님)을 페인팅하는 경우 해당 재료는 다음 실행 시까지 유지됩니다. 아래를 참조하십시오.

### **그룹 및 재료 사용**

* 여러 **SendToFormIt** 노드를 사용하는 경우 노드를 재료별로 구성할 수 있으므로 다른 재료로 다른 FormIt 하위 그룹을 페인팅할 수 있습니다.
* 이 예에서는 FormIt의 간단한 평면에서 전체 건물이 생성됩니다. 고유한 재료가 필요한 건물 구성요소마다 자체 **SendToFormIt** 노드가 있습니다.

![](<../.gitbook/assets/dynamo\_sendtoformit (1).png>)

* 각 하위 그룹에 재료를 적용하면 다음 Dynamo 실행 시까지 재료가 유지됩니다.

![](../.gitbook/assets/dynamo\_materialsgif.gif)

### **Dynamo 그룹 내포**

* **SelectFromFormIt** 노드를 사용해 하나의 Dynamo 그래프에서 하위 그룹 결과를 선택하여 다른 그래프의 결과를 실행할 수 있습니다.&#x20;
* 위의 예에서 건물 생성기 그래프의 유리 출력은 내장 점두 커튼월 샘플의 선택 형상으로 사용됩니다.

![](../.gitbook/assets/dynamo\_storefront\_curtainwallgif.gif)

* 건물 모양이 변경되면 멀리언 시스템 그룹을 선택하고 특성 패널에서 실행을 클릭하기만 하면 됩니다.
   * 유리 그룹의 컨텐츠가 변경되더라도 그룹 자체는 변경되지 않았으므로, 그래프를 다시 실행할 때 유리를 다시 선택할 필요가 없습니다.
* 위의 모델은 FormIt 2022 이상에서 **Dynamo Samples**의 **Building Mass** 하위 폴더에 있는 "Roof Planes Building"으로 사용할 수 있습니다.
* FormIt의 다양한 기능과 함께 Dynamo를 사용하면 강력한 개념 모델러의 풍부한 컨텍스트에서 완전한 재료 및 내포된 논리를 갖는 완전한 파라메트릭 설계를 작성하고 조정할 수 있습니다.

![](../.gitbook/assets/dynamo\_parametricdesigngif.gif)

### **계속 적용되는 표준 FormIt 그룹 동작**

* 위에 설명한 내용을 제외하고 FormIt의 Dynamo 그룹은 다른 그룹과 동일한 규칙으로 작동합니다.
   * Dynamo 패널에서 새 Dynamo 객체를 배치하면 고유 그룹이 작성되고 스케치에 이미 배치된 동일한 객체의 인스턴스에는 영향을 주지 않습니다.
   * Dynamo 그룹을 복사하여 붙여넣으면 동일한 상태로 유지됩니다. 한 사본의 Dynamo 그래프를 변경하면 고유하게 만든 경우를 제외하고 동일한 인스턴스의 형상도 업데이트됩니다.
   * 바로 가기 MU 또는 상황에 맞는 메뉴를 통해 Dynamo 그룹을 고유하게 만들 수 있습니다.

![](<../.gitbook/assets/dynamo\_makeunique (1).png>)

## 필수 FormIt 노드

FormIt과 Dynamo 간에 데이터를 전송할 수 있는 가장 강력한 기능을 가진 노드입니다.

### **SendToFormIt 노드**

* FormIt에서 Dynamo 객체를 생성하려면 하나 이상의 SendToFormIt 노드의 _형상_ 입력에 원하는 기하학적 노드 출력을 부착합니다.

![](<../.gitbook/assets/dynamo\_sendtoformitnode (1).png>)

* FormItGroupOptions는 FormIt 2022의 새로운 포트(선택 사항)이며, 아래의 **FormItGroupOptions Nodes** 섹션에 자세히 설명되어 있습니다.
* FormIt 2021.3 이상에서는 여러 SendToFormIt 노드를 사용하여 Dynamo 결과를 FormIt 그룹 및 하위 그룹으로 깔끔하게 구성할 수 있습니다.
* [Dynamo가 FormIt 그룹과 함께 연동하는 방식을 살펴보십시오](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups).

![](<../.gitbook/assets/dynamo\_sendtoformitnodes (1).png>)

* SendToFormIt 노드는 기본적으로 선택되어 있는 '출력임' 플래그를 사용합니다. 노드를 마우스 오른쪽 버튼으로 클릭하여 다음을 확인할 수 있습니다.

![](<../.gitbook/assets/dynamo\_isoutput (1).png>)

* 이 옵션이 선택되면, 이 SendToFormIt 노드에 부착된 형상이 FormIt에서 하위 그룹 내에 나타납니다.
* 이 옵션이 선택되지 않으면, 형상이 FormIt으로 전송되지 않고 해당 하위 그룹(있는 경우)이 삭제됩니다.

### **SelectFromFormIt 노드**

* FormIt 2021 이상 버전은 Dynamo 그래프에서 입력으로 사용할 형상을 FormIt에서 선택하는 기능을 제공합니다.

![](<../.gitbook/assets/dynamo\_selectfromformitnode (1).png>)

* SelectFromFormIt 노드의 이름은 FormIt의 프롬프트에 사용되므로, 선택해야 하는 FormIt 형상 유형을 알 수 있도록 이름을 지정해야 합니다.

![](<../.gitbook/assets/dynamo\_selectobjectstoarraynode (1).png>)

* Dynamo 그래프 편집기 또는 특성 패널에서 FormIt에서 선택 버튼을 클릭하면, FormIt에서 형상 선택을 안내하는 선택 마법사 모드가 시작됩니다.

![](../.gitbook/assets/dynamo\_selectobjectstoarrayUI.png)

* SelectFromFormIt 노드는 기본적으로 선택되는 '입력임' 플래그를 사용합니다. FormIt에서 선택할 수 있도록 이 옵션이 선택되어 있어야 합니다. 확인할 노드를 마우스 오른쪽 버튼으로 클릭합니다.

![](<../.gitbook/assets/dynamo\_isinput (1).png>)

* '입력임'이 선택된 경우:
   * 그래프의 Dynamo 패널 썸네일에 선택이 필요하다는 표시가 나타납니다.

![](../.gitbook/assets/dynamo\_patharray.png)

* 그래프를 실행할 때 FormIt 선택 마법사가 그래프 맨 위부터 시작해서 각 SelectFromFormIt 노드에 대한 선택 설정을 안내합니다.
* 처음 생성한 후에는 FormIt 특성 패널에 각 SelectFromFormIt 노드에 대한 버튼이 표시됩니다.

![](../.gitbook/assets/dynamo\_selectarraypath.png)

* 이러한 버튼을 클릭하면 선택 마법사가 시작됩니다. 따라서 최종 형상을 생성하는 데 사용되는 선택을 변경할 수 있습니다. 다시 선택하면 그래프가 자동으로 다시 실행됩니다.

### **팁, 트릭 및 참고**

* 어떤 유형의 형상이 예상되는지 알 수 있도록 SelectFromFormIt 노드의 이름을 지정합니다. 예를 들어 "대지 경계(모서리) 선택"과 같이 지정합니다.
   * 모든 유형의 FormIt 형상을 선택할 수 있지만 FormIt 그룹에 선택 항목을 포함하고 [원시 형상 대신 해당 항목을 선택](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups)하는 것이 가장 좋습니다.
* 선택 기반 Dynamo 그래프의 결과를 이동해야 하는 경우, 먼저 선택 형상을 이동하고 그래프를 다시 실행하는 것이 좋습니다. 그러면 업데이트된 선택 형상이 선택되어 적절하게 재배치됩니다.&#x20;
   * Dynamo 결과 **및** 선택사항을 그룹화한 다음, 포함하는 그룹을 이동할 수도 있습니다.
* FormIt 형상을 Dynamo로 보내면 형상을 다시 FormIt으로 되돌릴 때 모든 속성, 재료 또는 내포된 그룹이 손실됩니다.
* Dynamo에서 선택 기반 그래프를 편집하고 FormIt에서 선택한 형상이 변경되는 경우, SelectFromFormIt 노드에서 "FormIt에서 선택" 버튼을 클릭하여 형상을 다시 선택해야 합니다.&#x20;
* FormIt에서 선택하면 활성 [선택 필터](https://windows.help.formit.autodesk.com/tool-library/select-edge-face-or-object#selection-filtering)가 적용됩니다. 예를 들어 FormIt 정점을 선택하려면 선택 필터에서 해당 정점을 사용하도록 설정해야 합니다.

![](../.gitbook/assets/dynamo\_filterselection.png)

## 기타 입력 노드

FormIt에는 Dynamo 그래프를 쉽게 사용자화할 수 있는 다양한 입력 옵션이 있습니다.

### **FormItLengthString 노드**

FormIt 2022.1.0 이상에서는 **FormItLengthString** 노드를 사용하여 활성 스케치의 FormIt 단위 설정에 관계없이 지원되는 FormIt 단위 유형(피트-인치, 인치, m, cm, mm)으로 치수를 지정할 수 있습니다.

![](../.gitbook/assets/dynamo\_formitlengthstring.png)

지원되는 다른 입력 노드와 마찬가지로 _FormItLengthString_ 은 '입력임'으로 표시된 경우 FormIt 특성 팔레트에 표시되며, 이름을 바꾸면 FormIt에 새 이름이 표시됩니다.

![](../.gitbook/assets/dynamo\_propertiespalette.png)

_FormItLengthString_ 노드의 각 인스턴스는 어떤 단위 유형으로도 사용할 수 있으므로, 위에 표시된 대로 단일 Dynamo 그래프에서 여러 단위를 사용할 수 있습니다.

### **원시 숫자에서 FormItLengthString으로 전환**

FormIt 2022.1.1 이상에서 FormItLengthString 노드를 사용하도록 그래프를 전환하거나(그래프에 첫 번째 노드를 배치하여) 원시 숫자만 사용하도록 그래프를 전환하면(마지막 FormItLengthString을 제거하여) Dynamo에서 그래프를 편집하는 동안 특정 동작이 변경됩니다.

* 그래프를 편집하는 동안 [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 노드를 사용하는 경우, 위와 같이 원시 숫자와 _FormItLengthString_ 노드 간을 전환하려면 각 _SelectFromString_ 에 대한 형상을 다시 선택해야 합니다. 그래야 결과가 FormIt에서 올바르게 계속 축척됩니다.
* 그래프에 첫 번째 FormItLengthString 노드를 배치하면 그래프에서 치수(원시 숫자 입력 포함)로 의도된 모든 숫자는 미터(Dynamo의 기본 단위)를 나타냅니다.
   * [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 노드에서 변경 사항을 고려하고 FormIt에서 생성된 형상이 올바른 크기로 유지되는지 확인합니다.
   * 반대로 그래프에서 모든 FormItLengthString 노드를 제거하면 FormIt의 단위 설정이 무엇이든 관계없이 해당 단위를 나타내도록 원시 숫자가 전환됩니다(이전 동작).
* _FormItLengthString_ 노드의 숫자 출력은 미터 단위이지만 FormIt에서 형상 결과의 크기를 변경하지는 않습니다.

![](<../.gitbook/assets/dynamo\_outputinmeters (1).png>)

### **기타 지원되는 입력 노드**

Dynamo에서 "입력임"으로 표시된 경우 표준 Dynamo 입력 노드가 FormIt 특성 패널에 표시됩니다.

* 번호 슬라이더
* 정수 슬라이더
* 번호
* 문자열
* 부울 전환

입력 노드의 이름을 바꿀 수 있으며(명확성을 위해 권장됨), 이 경우 해당 새 이름이 FormIt에 표시됩니다.

![](<../.gitbook/assets/dynamo\_cuboidsize (1).png>)

![](../.gitbook/assets/dynamo\_inputs.png)

## 기타 출력 노드

Dynamo에서 FormIt으로 비기하학적 결과를 표시하는 다양한 방법이 있습니다.

### **Watch 노드**

FormIt 2022 이상에서는 "출력임"으로 표시된 Watch 노드가 특성 패널의 "Watch 노드 출력" 섹션에 표시됩니다.

![](<../.gitbook/assets/dynamo\_watchnodes (1).png>)

### **FormIt 알림 표시**

FormIt 2022.1 이상에서는 **UI.ShowNotification** 노드를 사용하여 Dynamo 그래프에서 FormIt 측 알림을 표시할 수 있습니다.&#x20;

![](../.gitbook/assets/dynamo\_notifications.png)

### **FormIt 콘솔에 기록**

FormIt 2022.1 이상에서는 **FormIt.ConsoleLog** 노드를 사용하여 FormIt 응용프로그램 콘솔(스크립트 출력 창)에 직접 추가 데이터를 기록할 수 있습니다.

![](../.gitbook/assets/dynamo\_logtoconsole.png)

## FormIt 옵션 노드

개별 형상 수준이나 포함하는 그룹 수준에서 데이터를 FormIt으로 보내는 방법을 제어할 수 있습니다.

### **FormItGeometryOptions**

FormIt 2022.1 이상 버전은 **FormItGeometryOptions** 노드를 사용하여 개별 Dynamo 형상을 FormIt으로 보내는 방법을 사용자화할 수 있는 기능을 제공합니다.

* 생성된 Dynamo 그룹 내의 개별 형상에 대한 레이어를 지정합니다.
* 생성된 Dynamo 그룹 내의 개별 형상에 대한 문자열 속성을 지정합니다.

_FormItGeometryOptions_ 노드는 _SendToFormIt_ 노드에서 업스트림으로 사용할 수 있습니다.

![](<../.gitbook/assets/dynamo\_formitgeometryoptions (1).png>)

### **FormItGroupOptions**

FormIt 2022 이상 버전에서는 _FormItGroupOptions_ 노드를 사용하여 FormIt에서 **SendToFormIt** 노드의 Dynamo 그룹이 생성되는 방식을 사용자화할 수 있는 기능을 제공합니다.

* SendToFormIt 노드가 형상을 FormIt에 메쉬로 보낼지 또는 객체로 보낼지 지정합니다.
* SendToFormIt 노드에 의해 작성된 그룹의 레이어를 지정합니다.
* SendToFormIt 노드에서 작성된 그룹에 대한 문자열 속성을 지정합니다.

FormItGroupOptions 노드를 데이지 체인 방식으로 함께 연결하여 임의의 순서로 조합해 사용할 수 있습니다.

![](../.gitbook/assets/dynamo\_daisychain.png)

## JavaScript API 노드

FormIt 2022.1 이상 버전에서는 다음과 같은 두 개의 새 노드를 통해 Dynamo에서 JavaScript API 및 사용자 함수에 액세스할 수 있습니다.

### **CallJSAPI**

**CallJSAPI** 노드를 사용하면 Dynamo에서 직접 FormIt JavaScript API를 호출할 수 있습니다.

![](<../.gitbook/assets/dynamo\_calljsapi (1).png>)

함수 이름 및 매개변수에 대해서는 JavaScript 설명서를 살펴보십시오. 이 설명서의 경우 [FormIt API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html)와 [WSM API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html)(모델링 커널)로 나누어져 있습니다.

**CallPluginJS**

반대로 **CallPluginJS** 노드를 사용하면 로드된 플러그인 또는 스크립트 편집기 창에서 실행된 스크립트 조각에서 사용자 함수를 호출할 수 있습니다.

![](<../.gitbook/assets/dynamo\_callpluginjs (1).png>)

## 중요 참고

### **시스템 요구사항**

* FormIt에서 Dynamo를 사용하려면 [Windows용 FormIt](https://formit.autodesk.com/page/download) v17.0 이상이 필요합니다.
   * FormIt + Dynamo 통합에는 새로운 기능과 수정 사항이 정기적으로 수신되므로, 가능하면 항상 최신 업데이트를 다운로드하는 것이 가장 좋습니다.
* Windows 10도 필요합니다. 기술적인 이유로 이전 버전의 Windows는 더 이상 지원되지 않습니다.

**문제 해결**

* 시스템에서 [NVIDIA 또는 AMD 그래픽 카드](https://www.howtogeek.com/414201/how-to-check-what-graphics-card-gpu-is-in-your-pc/)나 여러 카드를 사용하는 경우, 고출력 GPU를 사용하려면 FormIt 및 Dynamo를 설정해야 합니다.
   * _C:/Program Files/Autodesk/FormIt/FormIt.exe_
   * _C:/Program Files/Autodesk/FormIt/DynamoSandbox/FormItDynamoSandbox.exe_
   * NVIDIA 카드를 사용하는 경우 [NVIDIA 제어판이 설치되어 있는지 확인합니다](https://whatsabyte.com/blog/find-nvidia-control-panel/).
   * [NVIDIA](https://nvidia.custhelp.com/app/answers/detail/a\_id/2615/\~/how-do-i-customize-optimus-profiles-and-settings%3F) 또는 [AMD](https://www.amd.com/en/support/kb/faq/dh-017) 제어판을 사용하여 다음 응용프로그램이 개별 그래픽 카드를 사용하도록 설정합니다.
* 영어를 사용하지 않는 지역에 있는 경우, 특정 Dynamo 노드의 문제를 방지하려면 Windows 10 국가 설정을 영어로 설정해야 할 수 있습니다.
   * "언어"를 검색해 "언어 설정"을 선택합니다.
   * 언어 대화상자의 오른쪽 위에서 "관리 언어 설정"을 클릭합니다.
   * "시스템 로캘 변경..." 버튼을 클릭합니다.
   * "영어(미국)"를 선택합니다.
* 작은 형상이나 숫자로 작업할 때 그래프가 FormIt에서 결과를 생성하지 못하는 경우 Dynamo 축척 설정을 "작게"로 변경해 보십시오.
   * Dynamo 메뉴 > 기본 설정 > 일반 > 형상 축척 > 작게

![](../.gitbook/assets/dynamo\_geometryscaling.png)

### **지원 받기**

FormIt + Dynamo에 대한 도움이 필요하십니까? [포럼에 알려주시기 바랍니다](https://forums.autodesk.com/t5/formit-forum/bd-p/142).
