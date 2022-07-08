# mongoDB Study

<h2>1. Creat</h2>
<b>카테고리(?) 선택</b> - use [카테고리(?)명] <br>
삽입 - db.[DB명].insert() or insertOne <br>
ex)<br>
db.dogs.insertOne({name : "Charlie", age: 3, breed: "corgi", catFriendly : true})<br>
db.dogs.insert([{name : "Wyatt", age: 14, breed: "golden", catFriendly : false}, {name : "Tonya", age: 17, breed: "chihuahua",        catFriendly : true}])

<h2>2. Read</h2>
<b>찾기</b> - db.[DB명].find() or findOne() <br>
ex) <br>
db.dogs.find()<br>
db.dogs.find({ name : "Charlie"})<br>
db.dogs.findOne({ name : "Charlie"})<br>
    
<h2>3. Update</h2>
<b>업데이트</b> - db.[DB명].updateOne({ [업데이트 대상] } , {$set : {업데이트 내용}})<br>
ex) db.dogs.updateOne({ name : "Charlie" } , {$set : { age : 4 }})<br>

<b>다중 업데이트</b> - db.[DB명].updateMany({ [업데이트 대상] } , {$set : {업데이트 내용}})<br>
ex) db.dogs.updateMany({ catFriendly : true } , {$set : {isAvailable : false}})<br>

<b>수정 일자</b> - $currentDate : {lastChanged: true} (현재 날짜를 수정일로 넣는다.)<br>
ex) db.dogs.updateMany({ catFriendly : true } , {$set : {isAvailable : false} $currentDate : {lastChanged: true}})<br>

<h2>3. Deleted</h2>
<b>삭제</b> - db.[DB명].deleteOne({ [대상] })<br>
ex) db.dogs.deleteOne({ name : "Charlie" })<br>

<b>다중 삭제</b> - db.[DB명].deleteMany({ [대상] }) ( ({}) = 아무것도 넣지 않으면 전체 삭제)<br>
ex) db.dogs.deleteMany({ isAvailable : false })<br>
