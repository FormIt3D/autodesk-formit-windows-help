# 사용자 고유의 기능 추가

### HTML, JavaScript 및 CSS 패널 내부

플러그인 플레이그라운드 샘플 플러그인에서 편집을 클릭하면 HTML, JS(JavaScript) 및 CSS 패널이 표시됩니다. HTML 패널(왼쪽)을 사용하면 플러그인의 사용자 인터페이스를 수정할 수 있습니다. JS 패널(가운데)을 사용하면 FormIt JS 플러그인 API를 사용하여 FormIt과 통신할 수 있는 함수를 작성할 수 있습니다. 마지막으로 CSS 패널(오른쪽)은 HTML의 스타일을 결정합니다.

![](<../../../.gitbook/assets/image (27).png>)

### 함수를 추가하여 원통 작성

이 플러그인에 원통을 작성하기 위한 기능을 추가해 보겠습니다.

먼저 HTML 패널에서 입력 필드와 UI 버튼을 구성합니다. 다음 코드를 복사하여 23번 행 뒤와 _\<!-- Do not remove below scripts unless you know what you're doing- - >_ 앞에 붙여넣습니다.

이렇게 하면 플러그인에 몇 가지 기본 UI 요소가 추가됩니다.

```
<p>Cylinder: Create a cylinder at the origin.</p>
<div>
    <input id="Radius" type=number value=2 />
    <label>Radius</label>
</div>

<div>
    <input id="CHeight" type=number value =0.5 />
    <label>Height</label>
</div>


<input id="CreateCylinderBtn" type=button value="Create Cylinder" />

```

![](<../../../.gitbook/assets/image (86).png>)

다음으로, JS 패널에 두 개의 함수를 추가해 보겠습니다. 다음 코드를 복사하여 파일 끝에 붙여넣습니다(16번 행 뒤).

그러면 FormIt 작업공간에 원통이 작성됩니다

```
// Create cylinder
const createCylinder = async (r,h) =>
{
    const posCenter = await WSM.Geom.Point3d(0,0,0);

    const histID = await FormIt.GroupEdit.GetEditingHistoryID();
    console.log(histID,posCenter,r,h);

    const cyl = await WSM.APICreateCylinder(histID,posCenter,r,h);
}


// Execute function when 'create cylinder' button is clicked
document.getElementById("CreateCylinderBtn").addEventListener("click", ()=>
{
    console.log('create cylinder clicked')

    const r = Number(document.getElementById("Radius").value);
    const h = Number(document.getElementById("CHeight").value);

    createCylinder(r,h);

});
```

![](<../../../.gitbook/assets/image (82).png>)

### 실행 및 미리보기

결과를 볼 준비가 되면 재생 버튼 ![](<../../../.gitbook/assets/image (81).png>)을 다시 클릭합니다. 그러면 플러그인에 대한 업데이트가 동일한 패널에 표시됩니다.

![](<../../../.gitbook/assets/image (14).png>)

### FormIt 플러그인 API

FormIt 플러그인 API에 대한 전체 설명서는 [유용한 링](../useful-links.md) 섹션을 참고하십시오.
