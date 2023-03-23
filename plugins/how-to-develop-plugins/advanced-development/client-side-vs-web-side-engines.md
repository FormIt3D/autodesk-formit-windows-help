# 클라이언트측 엔진과 웹측 엔진

FormIt 플러그인은 다음과 같은 두 개의 고유한 JavaScript 엔진을 활용합니다.

* HTML을 표시하는 패널(웹측)
* 클라이언트측(FormIt)은 FormIt과 해당 형상 커널을 호출합니다.

이러한 두 JavaScript 엔진은 별개의 프로세스에서 작동합니다.

## **클라이언트측(FormIt)과 웹측(HTML)**

FormIt은 여러 JavaScript 엔진을 동시에 실행합니다.

* FormIt 응용프로그램에는 자체 JavaScript 엔진이 있습니다.
* 각 플러그인 도구막대에는 자체 JavaScript 엔진이 있습니다.
* 각 플러그인 패널에는 자체 JavaScript 엔진(Chrome)이 있습니다.

플러그인은 JavaScript가 로드되는 위치를 지정할 수 있습니다.

![](../../../.gitbook/assets/d14.png)

### 클라이언트측(FormIt)

[manifest.json](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/manifest.json#L8)을 사용하여 지정됨

```
    "Scripts": [
        "PLUGINLOCATION/blockFormItSide.js",
        "https://formit3d.github.io/FormItExamplePlugins/SharedPluginFiles/PluginUtils18_0.js"
    ]
```

### 웹측(HTML)

[index.html](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/index.html#L7)을 사용하여 지정됨

* 웹 페이지에서 웹측 스크립트가 로드됩니다.
* 웹측 스크립트는 다중 비동기 호출을 사용하여 클라이언트측(FormIt) JavaScript를 호출할 수 있습니다.

## 웹 기반 플러그인에서 클라이언트측(FormIt) 명령을 호출하는 세 가지 메서드:

### 메서드 1: FormItInterface.CallMethod

`CallMethod`는 함수 이름과 FormIt측에서 실행될 인수를 사용합니다. 전달된 함수는 함수 호출 결과와 함께 호출됩니다.

```
    var args = {
        "w": 10,
        "l": 10,
        "h": 10
    }
    FormItInterface.CallMethod("CreateBlock", args, function(result)
    {
        // Result of the function call
    });
```

**장점:**

➕ `await`가 필요하지 않습니다.

**단점:**

➖ 결과를 얻으려면 콜백이 필요하며 콜백은 "who knows when"으로 호출됩니다.

➖ 스크립트가 두 개의 다른 위치에 정의됩니다.

➖ 플러그인 로직을 두 개의 다른 파일로 분할해야 합니다.

### **메서드 2: FormIt.CallJS**

***FormIt 2022.1 이상 버전에서만 사용 가능**

CallJS는 FormIt측 및 arguments.json 객체에서 호출될 JavaScript 함수를 사용합니다.

```
var args =
{
    "w": 10,
    "l": 10,
    "h": 10
};
var result = await FormIt.CallJS("CreateBlock", args);
```

**장점:**

➕ 필요할 때 결과를 사용할 수 있습니다.

**단점:**

➖**** await를 사용하여 모든 비동기 호출을 장식해야 하며, 이렇게 하지 않으면 문제가 발생합니다.

➖**** `await`로 인해 잠재적으로 느려질 수 있습니다.

### **메서드 3(async/await)**

```
const pt1 = await WSM.Geom.Point3d(0,0,0);
```

웹측에서는 비동기 호출을 통해 FormIt측을 호출합니다. 이 호출은 한 프로세스에서 시작하여 다른 프로세스로 전송되고 결과가 시작 프로세스로 다시 전달됩니다. 따라서 await가 필요합니다.

기본적으로 기본 제공 FormIt API만 호출할 수 있습니다.

**장점:**

➕ 필요할 때 결과를 사용할 수 있습니다.

➕ manifest.json에 스크립트를 정의하지 않은 상태로 웹측에서 모든 코드를 하나의 JS 파일에 결합할 수 있도록 허용합니다.

**단점:**

➖**** `await`를 사용하여 모든 비동기 호출을 장식해야 하며, 이렇게 하지 않으면 문제가 발생합니다.

➖**** `await.`로 인해 잠재적으로 느려질 수 있습니다.

### 메서드 4(RegisterAsyncAPI)

***FormIt 2023.0 이상 버전에서만 사용 가능**

FormIt측에서 사용자 정의 함수를 호출하려면 함수를 등록해야 합니다. 예:

**클라이언트측(FormIt)**

```
FormIt.RegisterAsyncAPI("HelloBlockAsync", "CreateBlock", "l, w, h");
// CreateBlock runs from FormIt.
HelloBlockAsync.CreateBlock = function(args)
{
    return { "Result" : "It Worked!!"};
}
```

**웹측(HTML)**

```
var result = await HelloBlockAsync.CreateBlock(l, w, h);
```

예는 [HelloBlockAsync](https://github.com/FormIt3D/FormItExamplePlugins/tree/master/HelloBlockAsync/v23\_0)를 참고하십시오.

**장점:**

➕ 필요할 때 결과를 사용할 수 있습니다.

➕ manifest.json에 스크립트를 정의하지 않은 상태로 웹측에서 모든 코드를 하나의 JS 파일에 결합할 수 있도록 허용합니다.

**단점:**

➖**** await를 사용하여 모든 비동기 호출을 장식해야 하며, 이렇게 하지 않으면 문제가 발생합니다.

➖**** `await.`로 인해 잠재적으로 느려질 수 있습니다.

##
