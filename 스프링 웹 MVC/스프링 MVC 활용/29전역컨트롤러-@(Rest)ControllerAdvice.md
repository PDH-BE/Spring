전역 컨트롤러: @(Rest)ControllerAdvice

예외 처리, 바인딩 설정, 모델 객체를 모든 컨트롤러 전반에 걸쳐 적용하고 싶은 경우에 사용한다. 

- @ExceptionHandler

- @InitBinder

- @ModelAttributes

적용할 범위를 지정할 수도 있다.

- 특정 애노테이션을 가지고 있는 컨트롤러에만 적용하기 

- 특정 패키지 이하의 컨트롤러에만 적용하기

- 특정 클래스 타입에만 적용하기

참고

- https://docs.spring.io/spring/docs/current/spring-framework-reference/web.html#mvc-ann -controller-advice

---

사용 예시

```java
// Target all Controllers annotated with @RestController
@ControllerAdvice(annotations = RestController.class)
public class ExampleAdvice1 {}

// Target all Controllers within specific packages
@ControllerAdvice("org.example.controllers")
public class ExampleAdvice2 {}

// Target all Controllers assignable to specific classes
@ControllerAdvice(assignableTypes = {ControllerInterface.class, AbstractController.class})
public class ExampleAdvice3 {}

```