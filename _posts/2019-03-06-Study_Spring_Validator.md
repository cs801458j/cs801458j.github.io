# 180306 study

## Spring Validator를 이용한 검증

- 데이터 검증을 위햏 Validator 인터페이스의 validate()메소드를 사용
- ValidatorUtils 클래스는 Validate()메소드를 좀 더 편리하게 사용할 수 있도록 고안된 클래스

## @Valid와 @InitBinder
- 데이터 검증을 위해 직접 호출하지 않고 스프링 프레임워크에서 직접 호출하여 사용 
- @Valid 태그 붙인다. 


## Bean Validation
```java
@Builder
@Getter
public class Person {
    @NotEmpty(message = "이름이 공백이면 안됩니다.")
    private String name;

    @PositiveOrZero(message = "나이는 0 이상으로 입력해야합니다.")
    private int age;
}


ValidatorFactory factory = Validation.buildDefaultValidatorFactory();
Validator validator = factory.getValidator();

Set<ConstraintViolation<Car>> constraintViolations = validator.validate(car);


//  제약조건 위반 내용에 대한 확인

public interface ConstraintViolation<T> {

    // 위반된 내용에 대한 메시지
    String getMessage();

    // 위반된 내용에 대한 메시지탬플릿
    String getMessageTemplate();

    // 유효성검증을 시도한 루트빈
    T getRootBean();

    // 유효성검증을 시도한 루트빈 클래스
    Class<T> getRootBeanClass();

    // 제약조건을 위반한 빈
    Object getLeafBean();

    // 생성자 또는 메소드실행에 대한 유효성 검증이 이뤄졌을 경우, 파라메터값들이 여기에 들어간다. (그 외에는 null)
    Object[] getExecutableParameters();

    // 생성자 또는 메소드실행에 대한 유효성 검증이 이뤄졌을 경우, 응답값이 여기에 들어간다. (그 외에는 null)
    Object getExecutableReturnValue();

    // 루트빈으로부터 유효성검증이 이루어진 프로퍼티경로
    Path getPropertyPath();

    // 유효성검증에 통과하지 못한 값
    Object getInvalidValue();

    // 제약조건 (여기서는 애노테이션)
    ConstraintDescriptor<\?> getConstraintDescriptor();

    ...
}
```


https://medium.com/@gaemi/java-%EC%99%80-spring-%EC%9D%98-validation-b5191a113f5c
