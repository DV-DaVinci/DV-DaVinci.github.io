---
title: applicationContext.xml
date: 2022-04-02 06:06:00 +09:00 
categories: [WEB-Backend, Spring] 
tags: [Spring, applicationContext.xml]     # TAG names should always be lowercase
---

IoC를 지원하는 스프링 컨테이너는 객체를 관리하는 별도의 설정파일이 필요합니다.

‘IoC 란?’ 포스팅에서 '서블릿 컨테이너'를 예시로 들었었습니다.

결국에는 둘 다 컨테이너기 때문에 서블릿 컨테이너에게 web.xml 파일이 있었던 것처럼 스프링 컨테이너 설정파일도 ~.xml일 것이다 라는 것을 예상해 볼 수 있습니다.

## applicationContext.xml 생성

---

![스크린샷(209).png](/assets/2022-04-02-applicationContext/1.png)

`Java Resource > src/main/resource`에서 ‘Spring Bean Configuration File’로 만들어줍니다. 

![스크린샷(210).png](/assets/2022-04-02-applicationContext/2.png)

파일 이름은 ‘applicationContext.xml’입니다.

구조를 보면 `<beans>`라는 엘리먼트로 묶여있고 그 안에 각종 Namespaces(네임스페이스) 관련 설정이 되어 있습니다. 

앞으로 이 설정파일에 `<bean>` 엘리먼트로 클래스를 등록할 수 있습니다. 

클래스 하나 당 하나의 `<bean>` 엘리먼트가 필요합니다.

## applicationContext.xml 클래스 등록

---

기존에 간단하게 만들었던 클래스를 한번 등록해보겠습니다. 

- IPhone

```java
package coupling;

public class IPhone implements Phone {
	public void powerOn() {
		System.out.println("아이폰 전원 ON");
	}
	public void powerOff() {
		System.out.println("아이폰 전원 OFF");
	}
	public void volumeUp() {
		System.out.println("아이폰 소리 ++");
	}
	public void volumeDown() {
		System.out.println("아이폰 소리 --");
	}
}
```

- applicationContext.xml

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

	<bean class="coupling.IPhone" id="phone"/>

</beans>
```

`<bean>` 엘리먼트 안에 `class`라는 속성으로 어떤 클래스를 등록할 것인지 작성할 수 있습니다. 

또 `id` 라는 속성을 통해서 이 클래스를 뭐라고 부를건지 이름을 정해줄 수 있습니다. 

## applicationContext.xml에 객체관리를 맡겨보자

---

이제 이 설정파일에 객체관리를 맡겨보겠습니다. 

- Phone User

```java
package coupling;

import org.springframework.context.support.AbstractApplicationContext;
import org.springframework.context.support.GenericXmlApplicationContext;

public class PhoneUser {
	public static void main(String[] args) {
		AbstractApplicationContext factory = new GenericXmlApplicationContext("applicationContext.xml");
		
		Phone phone = (Phone)factory.getBean("phone");
		
		phone.powerOn();
		phone.volumeUp();
	
		factory.close();
	}
}
```

`AbstractApplicationContext` 는 앞에 붙어있는 ‘Abstract’를 보면 유추할 수 있겠지만 인터페이스입니다. 이 인터페이스를 구현한 하위의 다양한 클래스들 중 `GenericXml`을 만들었습니다. 여기서 `factory` 객체는 스프링 컨테이너를 눈으로 볼 수 있게 객체화 시킨 것입니다. 

실제로 많이 사용하는 것은 아니지만 동작방식을 살펴보기 위해 채택했습니다. 

나중에 웹개발로 본격적인 내용을 포스팅하게되면 web.xml을 사용하게 될 겁니다.

## applicationContext.xml에 등록했던 객체를 어떻게 불러낼까?

---

xml에 bean으로 등록했기 때문에 getBean() 메소드를 이용해 불러낼 수 있습니다. 조금 전 xml에서 클래스의 id를 phone으로 등록했기 때문에 `getBean("phone")`으로 명령합니다. 

여기서 getBean() 은 리턴타입이 Object이기 때문에 Phone 객체에 넣으려면 캐스팅을 해주어야 합니다. 

## ‘phone’ 객체가 어느 순간에 만들어질까?

---

applicationContext.xml에 등록했던 ‘phone’ 객체가 언제 만들어지는지 확인해보기 위해  IPhone클래스에서 기본생성자를 작성해보겠습니다. 

- IPhone

```java
package coupling;

public class IPhone implements Phone {
	
	public IPhone() {
		System.out.println("아이폰 생성됨");
	} //기본생성자
	
	public void powerOn() {
		System.out.println("아이폰 전원 ON");
	}
	public void powerOff() {
		System.out.println("아이폰 전원 OFF");
	}
	public void volumeUp() {
		System.out.println("아이폰 소리 ++");
	}
	public void volumeDown() {
		System.out.println("아이폰 소리 --");
	}
}
```

- 실행결과

```java
아이폰 생성됨
아이폰 전원 ON
아이폰 소리 ++
```

 결과를 확인해보면 `lookup`을 하는 순간 기본생성자를 호출해서 객체를 생성하고, 만들어진 객체로 powerOn()/ volumeUp() 을 하고 있다는 것을 확인할 수 있습니다. 

중요한건 점점 객체를 생성, 관리하는 것을 전부 설정파일에 넘김으로써 

개발자가 더이상 코드개입을 하지 않을 수 있도록 하는겁니다. 

## IPhone에서 GalaxyPhone으로 바꾸고 싶다면?

---

이제 설정파일이 외부에 있기 때문에 갑자기 IPhone에서 GalaxyPhone으로 바꾸고 싶다면 applicationContext.xml에서 간단한 수정을 통해 해결할 수 있습니다.

우선 GalaxyPhone 클래스를 만들었습니다.

- GalaxyPhone

```java
package coupling;

public class GalaxyPhone implements Phone{

	@Override
	public void powerOn() {
		System.out.println("갤럭시 전원 ON");
	}
	@Override
	public void powerOff() {
		System.out.println("갤럭시 전원 OFF");
	}
	@Override
	public void volumeUp() {
		System.out.println("갤럭시 소리 ++");
	}
	@Override
	public void volumeDown() {
		System.out.println("갤럭시 소리 --");
	}

}
```

- applicationContext.xml 수정

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

	<bean class="coupling.GalaxyPhone" id="phone"/>

</beans>
```

class 속성에서 IPhone을 GalaxyPhone으로 수정했습니다.

- 실행결과

```java
갤럭시 전원 ON
갤럭시 소리 ++
```

코드를 하나도 고치지 않고 설정만 변경했을 뿐인데 <u>유지보수가 한층 더 용이해졌습니다.</u>