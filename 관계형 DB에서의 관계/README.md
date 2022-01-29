`entity` - 관리하고자 하는 데이터들의 집합입니다. ex) 과목, 학생 등 추상적인 개념

`field` - column에 해당하는 **가장 작은 단위의 데이터를 의미하며, 속성을 표현합니다.**

`record` - **연관된 필드의 집합**을 의미하며, **테이블의 행인 row를 뜻합니다.** 

`table` - **서로 연관된 레코드의 집합**을 뜻합니다.

<br>

**엔터티와 레코드의 차이점 (Entity vs Records)**

- 레코드는 실제 데이터베이스 상에 저장되어 있는 값들의 모임을 말합니다.
- 반면에, 엔터티는 현실 세계에 존재하는 객체를 표현하기 위해 비유(추상)적으로 사용됩니다.

<br>

엔터티 사이의 관계를 릴레이션(relationship)이라 하고, 이것을 도표로 나타낸 것을 ERD(Entity Relationship Diagram)라고 한다.

![](https://images.velog.io/images/wjddk97/post/eff0dddd-846e-4a83-86e0-9f2c53a4c2a3/image.png)

## 1:1 관계

- **하나의 레코드**가 다른 테이블의 **레코드 한 개**와 연결된 관계입니다.


## 1:N 관계

- **하나의 레코드**가 다른 테이블의 **여러 개의 레코드**와 연결된 관계입니다.

## N:M 관계

- **여러 개의 레코드**가 다른 테이블의 **여러 개의 레코드**와 연결된 관계입니다.


<br>

## 자기 참조 관계 **(Self Referencing Relationship)**

- **한 엔터티가 자기 자신과 연결된 관계**입니다.

![](https://images.velog.io/images/wjddk97/post/da3ec4fa-bb03-470e-8ce7-744852138e7e/image.png)

**자기자신을 참조하는 parent_comment 필드**
- 이 값이 null이면 댓글
- 예를 들어, 값이 6이라면 id가 6인 댓글의 대댓글이다.
