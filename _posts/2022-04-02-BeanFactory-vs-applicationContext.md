---
title: BeanFactory vs ApplicationContext 차이점
date: 2022-04-02 09:46:00 +09:00 
categories: [WEB-Backend, Spring] 
tags: [Spring]     # TAG names should always be lowercase
---

---

간단한 실습을 통해 그 차이점을 확인할 수 있습니다.

applicationContext.xml에서 IPhone과 GalaxyPhon을 만들고 

id는 겹치지 않도록 설정한 뒤 PhoneUser로 가서 ‘gphone’을 lookup 해봅시다.

- applicationContext.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

	<bean class="coupling.IPhone" id="phone"/>
	<bean class="coupling.GalaxyPhone" id="gphone"/>

</beans>
```

- PhoneUser

```java
package coupling;

import org.springframework.context.support.AbstractApplicationContext;
import org.springframework.context.support.GenericXmlApplicationContext;

public class PhoneUser {
	public static void main(String[] args) {
		AbstractApplicationContext factory = new GenericXmlApplicationContext("applicationContext.xml");
		
		Phone phone = (Phone)factory.getBean("gphone");//gphone lookup
		
		phone.powerOn();
		phone.volumeUp();
	
		factory.close();
	}
}
```

- 실행결과

```java
아이폰 생성됨
갤럭시 전원 ON
갤럭시 소리 ++
```

실행결과를 보면 GalaxyPhone을 요청했는데도 ‘아이폰 생성됨’이 출력된 것을 확인할 수 있습니다. 

BeanFactory와 ApplicationContext의 차이점을 확실히 보여주는 결과입니다.

## BeanFactory

---

BeanFacotory는 컨테이너가 실행될 때 바로 객체가 생성되는 것이 아닙니다. 

클라이언트가 객체를 요청했을 때 그때 객체를 생성합니다.

컨테이너 동작과 객체를 만드는 행위를 완전 다른 행위라고 보는 겁니다.

장점은 메모리 낭비를 하지 않을 수 있지만

단점은 사용자가 해당 스탭 때 필요한 객체들을 전부 알고 있어야 한다는 것입니다.

BeanFactory처럼 클라이언트가 객체를 요청했을 때 생성하는 것을 `‘지연로딩’`이라고 합니다. 

그리고 별도의 추가기능을 지원하지 않고 개발자가 만든대로 딱 객체를 지급하는 용도 정도로만 쓰입니다.

BeanFactory는 메모리를 아낄 수 있는 장점이 있지만, 그 장점을 applicationContext에서 각종 설정으로 충분히 해결할 수 있습니다. 

때문에 일반적으로 많이 쓰이진 않지만 필요한 부분에서 필요한 만큼 쓰이기도 합니다. 

## ApplicationContext

---

ApplicationContext를 구현한 클래스들 중 GenericXmlApplicationContext를 선택해서 썼는데, 뭔가를 상속받았기 때문에 기능들이 다 갖춰져 있을 거라는 것을 예상할 수 있습니다. 

그래서 개발자가 필요한 언어처리, 트랜잭션 등 다양한 기능을 지원해줍니다.

ApplicationContext는 실습에서 볼 수 있었던 것처럼 `<bean>`으로 등록한 모든 객체를 미리 생성해놓고 골라서 씁니다. 
이런 것을 `‘즉시로딩’`이라고 합니다.

장점은 객체를 미리 다 생성해두기 때문에 사용자가 어떤게 필요한지 고르지 않아도 됩니다.

단점은 한번 쓰거나, 안 쓰는 것들도 다 로드하기 때문에 메모리가 낭비되는 경향이 있습니다. 하지만 이런 단점들도 설정으로 충분히 해결할 수 있기 때문에 BeanFactory보다 많이 사용되고 있습니다. 

[스프링 공식 문서]([https://docs.spring.io/spring-framework/docs/2.5.x/reference/beans.html#context-introduction-ctx-vs-beanfactory](https://docs.spring.io/spring-framework/docs/2.5.x/reference/beans.html#context-introduction-ctx-vs-beanfactory))를 찾아보니 두 컨테이너 중 특별한 이유가 없다면 ApplicationContext를 사용해야 한다고 나와있습니다.

이유는 BeanFactory를 상속받았기 때문에 BeanFactory의 모든 기능을 포함하는 것은 물론이고 추가 기능들을 제공하기 때문입니다.