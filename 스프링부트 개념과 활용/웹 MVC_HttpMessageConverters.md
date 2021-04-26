스프링 웹 MVC 2부: HttpMessageConverters

[https://docs.spring.io/spring/docs/5.0.7.RELEASE/spring-framework-reference/web.html#mvc-config-message-converters]()

HTTP 요청 본문을 객체로 변경하거나, 객체를 HTTP 응답 본문으로 변경할 때 사용.
{“username”:”keesun”, “password”:”123”} <-> User
● @ReuqestBody
● @ResponseBody


요청,응답 모두 타입에 따라 Converter가 달라짐(JsonConverter, StringConverter...)

@RestController가 아닌 그냥 @Controller를 사용할경우 @ResponseBody를 사용하여함, 그래야만 HttpMesaageConverter가 사용됨

