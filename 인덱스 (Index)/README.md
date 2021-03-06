# **인덱스란?**

**데이터베이스 테이블에 대한 검색 성능의 속도를 높여주는 자료구조입니다.**

특정 컬럼에 인덱스를 생성하면, 해당컬럼의 데이터들을 정렬하여 별도의 메모리 공간에 데이터의 물

리적 주소와 함께 저장됩니다.

> 일반적으로 PK는 자동으로 인덱스가 적용됩니다.
> 

<br>

## 인덱스를 사용하는 이유?

**전반적인 시스템의 부하를 줄일 수 있고,**

**테이블을 조회하는 속도를 향상시킬 수 있습니다.**

<br>

**[ 조건검색 where 절의 효율성 ]**

테이블을 만들고 데이터가 쌓이면 레코드는 내부적으로 순서없이 뒤죽박죽 저장됩니다.

이렇게 되면 where절에 특정 조건에 맞는 데이터들을 찾아낼때도 처음부터 끝까지 다 읽어서

검색 조건과 맞는지 비교해야 합니다.

**하지만 인덱스 테이블은 데이터들이 정렬되어 저장 되어 있기 때문에 조건에 맞는 데이터들을 빠르게 찾아낼 수 있습니다.**

<br>
<br>

**[ 정렬 Order by 절의 효율성 ]**

인덱스를 사용하면 order by의sort과정을 피할수 있습니다.

order by는 부하가 많이 걸리는 작업입니다.

정렬과 동시에 1차적으로 메모리에서 정렬이 이뤄지고,

메모리보다 큰 작업이 필요하면 디스크 I/O도 추가적으로 발생됩니다.

인덱스는 이미 정렬 되어 있기 때문에 자원의 소모를 하지 않아도 됩니다.

<br>
<br>

**[ MIN, MAX의 효율적인 처리 ]**

인덱스는 이미 정렬되어 있기에 MIN값과 MAX값을

레코드의 시작과 끝 값을 가져오면 되기에 효율적입니다.

<br>

### 인덱스의 단점

- DB의 약 10%의 저장공간이 필요하며, 관리를 위한 추가 작업이 필요합니다.
- 잘못 사용할 경우 오히려 성능이 저하되는 역효과가 발생할 수 있습니다.
- INSERT, DELETE, UPDATE가 빈번하면 인덱스의 크기가 비대해져서 성능이 저하될 수 있기 때문입니다.

<br>

### 인덱스를 사용하면 좋은 경우

- JOIN이나 WHERE 또는 ORDER BY에 자주 사용되는 컬럼
- INSERT, UPDATE, DELETE가 자주 발생하지 않는 컬럼
- 데이터의 중복도가 낮은 컬럼
