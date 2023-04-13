# 3D Context Creator

![](<../../.gitbook/assets/3D Context Creator_new.gif>)

## 3D Context Creator는 무엇인가요?

3D Context Creator는 FormIt 내에서 3D 컨텍스트 건물을 생성하는 사용하기 쉬운 플러그인입니다. 

이 플러그인은 프로젝트 대지를 주변 컨텍스트로 시각화하고 설계 프로세스의 초기 단계에서 정보를 바탕으로 의사 결정을 내리는 데 도움이 됩니다.

이 플러그인을 통해 [Open Street Map](https://www.openstreetmap.org/about)에서 데이터를 검색하여 FormIt 형상으로 변환할 수 있습니다. 이 플러그인의 소스 코드는 [Github](https://github.com/matterlab-co/FormIt-Context-Plugin)에서 확인할 수 있습니다.

## 사용 방법

설치하려면 다른 플러그인과 마찬가지로 Plugin Manager에서 플러그인의 토글을 활성화하면 됩니다.

![](../../.gitbook/assets/contextcreator3.png)

토글을 켜면 플러그인이 앱 오른쪽에 나타나고 사용할 준비가 됩니다.

![](<../../.gitbook/assets/3D Context Creator new_no location (1).png>)

대지에 아직 위치가 없는 경우 **위치 설정...** 링크를 클릭하여 위치를 설정하고 3D 컨텍스트를 생성하는 데 사용할 경계를 정의할 수 있습니다.

위치를 설정하면 3D Context Creator가 현재 위치로 업데이트되고 버튼이 활성화됩니다.

![](<../../.gitbook/assets/3D Context Creator new_with location.png>)

3D Context Creator는 위성 이미지의 범위를 사용하여 3D 컨텍스트를 생성합니다. **3D 컨텍스트 생성**을 클릭하기만 하면 됩니다.

위성 이미지의 범위 및 건물의 복잡성에 따라 컨텍스트가 생성되는 데 몇 초 정도 걸릴 수 있습니다.

3D 컨텍스트 건물은 자동으로 그룹 인스턴스에 배치되고 "컨텍스트 건물"이라는 레이어에 배치됩니다. 이 레이어를 사용하여 컨텍스트의 가시성을 전환할 수 있습니다.

![](<../../.gitbook/assets/3D Context Creator_layers.png>)

![](<../../.gitbook/assets/3D Context Creator_NYC.png>)

나중에 위치를 변경하거나 위성 이미지의 범위를 조정하려는 경우 **3D 컨텍스트 생성**을 다시 클릭하여 건물을 재생성할 수 있습니다. 

_컨텍스트를 재생성하면 건물이 포함된 그룹 인스턴스가 새 인스턴스로 바뀌므로 건물에 대한 모든 변경 사항이 손실됩니다._ 이를 방지하기 위해 컨텍스트 컨테이너를 그룹 해제한 다음 다시 그룹화할 수 있습니다.

## **몇 가지 예**

다음과 같은 컨텍스트에서 대표적인 도시가 무엇인지 추측해 보십시오.

![](<../../.gitbook/assets/image (2) (1).png>)

![](<../../.gitbook/assets/image (34).png>)

![](<../../.gitbook/assets/image (13) (1) (1).png>)

![](<../../.gitbook/assets/image (59).png>)
