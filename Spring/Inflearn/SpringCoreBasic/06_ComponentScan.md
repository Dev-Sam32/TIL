# 섹션 6. 컴포넌트 스캔

## @ComponentScan

- 설정 정보 없이 ```@Component``` 어노테이션이 붙은 클래스 스프링 빈으로 등록한다.
  ⚠️ ```@Configuration``` 안에 ```@Component``` 어노테이션이 붙어있기 때문에 따로 등록이 필요없다.

- 탐색 위치, 기본 스캔 대상 지정
  ``` java
  @ComponentScan {
    basePackages = "hello.core", "hello.service"
  }
  ```

  - 탐색할 패키지의 시작 위치를 변경할 수 있다. ( 명시된 패키지를 포함한 하위 패키지 모두 스캔)

  - Default) ```@ComponentScan``` 이 붙은 설정 정보 클래스의 패키지

    -> 관례적으로 설정 정보 클래스의 위치를 프로젝트 최상단에 둔다고 한다.

    -> ```basePackages``` 를 따로 지정하지 않아도 된다. -> 생략 가능

- ```@Component```, ```@Controller```, ```@Service```, ```@Repository```, ```@Configuration``` 모두 스캔된다.

- ```inclueFilters```, ```excludeFilters``` 로 스캔 대상 추가 or 제외를 지정할 수 있다.

- ```@ComponentScan``` 시 동일명의 빈 등록으로 충돌이 난다면, 수동 등록 빈이 우선된다.

## @Autowired

- ```@ComponentScan``` 사용시 의존관계 주입을 위해 생성자에 ```@Autowired``` 를 사용한다.(생성자 주입)
