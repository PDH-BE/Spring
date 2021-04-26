스프링 웹 MVC 1부: 소개

● 스프링 웹 MVC

○ https://docs.spring.io/spring/docs/5.0.7.RELEASE/spring-framework-reference
/web.html#spring-web

● 스프링 부트 MVC

○ 자동 설정으로 제공하는 여러 기본 기능 (앞으로 살펴볼 예정)

/test/UserControllerTest

```
@RunWith(SpringRunner.class)
@WebMvcTest(UserController.class)
public class  userControllerTest {
    @Autowired
    MockMvc mockMvc;

    @Test
    public void hello() throws Exception {
        mockMvc.perform(get("/hello"))
                .andExpect(status().isOk())
                .andExpect(content().string("hello") );

    }
}
```

main/UserController

```
@RestController
public class UserController {

    @GetMapping("/hello")
    public String hello(){
        return "hello";
    }
}
```
로 간단한 WebMVC Test를 구현해볼 수 있는데, 
WebMVCAutoConfiguration의 자동설정 덕분에 아무런 설정없이 곧바로 실행 가능하다.



● 스프링 MVC 확장

○ @Configuration + implements WebMvcConfigurer

기본 설정 + 추가 설정

● 스프링 MVC 재정의

○ @Configuration + @EnableWebMvc

기본설정이 모두 제거 되어 모든 설정을 직접 해줘야하므로 거의 쓰이진 않는다.
