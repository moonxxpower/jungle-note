# mongoDB

**NoSQL** 타입의 데이터 베이스 프로그램으로, JSON과 비슷한 형태로 자료를 정리한다.

각각의 딕셔너리인 도큐먼트가 모여 컬렉션, 컬렉션이 모여 DB가 되는 형태이다. 예를 들어 각 영화 정보 (제목/순위/별점)가 도큐먼트이고, 이것들을 모인 컬렉션을 DB에 저장할 수 있는 것이다.

MongoDB라는 프로그램을 조작하기 위해서는 **pymongo**가 필요하다.

**(*) NoSQL**

딕셔너리 형태로 데이터를 저장해두는 DB로, 데이터 하나하나 마다 같은 필드 값들을 가질 필요가 없어 자유로운 형태의 데이터 적재에 유리한 대신, 일관성이 부족할 수 있다.

**(*) pymongo**

```python
# DB 연결하기
from pymongo import MongoClient       
client = MongoClient('localhost', 27017) 
db = client.jungle

# 저장하기 (collection: users)
db.users.insert_one({'name': 'bobby', 'age': 21})

# 입력 일자를 포함하여 저장을 위해서는 datetime (시간 라이브러리)가 필요하다.
# utcnow()를 사용하면, 도큐먼트 생성 시간 (현재 시간)으로 저장된다.
from datetime import datetime, timezone
create_date = datetime.now(timezone.utc)

# 조회하기
user = db.users.find_one({'name': 'bobby'})
same_ages = list(db.users.find({'age': 21}, {'_id': False})

# 수정하기
db.users.update_one({'name': 'bobby'}, {'$set': {'age': 19}})

# 삭제하기
db.users.delete_one({'name': 'bobby'})
```