* ## 스프링 타입 컨버터

![image](https://user-images.githubusercontent.com/60100532/178111099-b4cddc99-2e8e-4837-be8e-2d72db67da40.png)

* ### 인터페이스 분리 원칙 - ISP(Interface Segregation Principal)
  * 인터페이스 분리 원칙은 클라이언트가 자신이 이용하지 않는 메서드에 의존하지 않아야 한다.
  
  * `DefaultConversionService` 는 다음 두 인터페이스를 구현했다.
    * `ConversionService` : 컨버터 사용에 초점
    * `ConverterRegistry` : 컨버터 등록에 초점
    
  * 이렇게 인터페이스를 분리하면 컨버터를 사용하는 클라이언트와 컨버터를 등록하고 관리하는 클라이언트의
    관심사를 명확하게 분리할 수 있다. 
  * 특히 컨버터를 사용하는 클라이언트는 `ConversionService` 만
    의존하면 되므로, 컨버터를 어떻게 등록하고 관리하는지는 전혀 몰라도 된다. 결과적으로 컨버터를
    사용하는 클라이언트는 꼭 필요한 메서드만 알게된다. 
  * 이렇게 인터페이스를 분리하는 것을 ISP 라 한다.