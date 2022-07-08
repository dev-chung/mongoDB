# mongoDB Study

1. Creat
카테고리(?) 선택 - use [카테고리(?)명]
삽입 - db.[DB명].insert() or insertOne / 
ex) db.dogs.insertOne({name : "Charlie", age: 3, breed: "corgi", catFriendly : true})
    db.dogs.insert([{name : "Wyatt", age: 14, breed: "golden", catFriendly : false}, {name : "Tonya", age: 17, breed: "chihuahua",         catFriendly : true}])

2. Read
찾기 - db.[DB명].find() or findOne()
ex) db.dogs.find()
    db.dogs.find({ name : "Charlie"})
    db.dogs.findOne({ name : "Charlie"})
    
3. Update
업데이트 - db.[DB명].updateOne({ [업데이트 대상] } , {$set : {업데이트 내용}})
ex) db.dogs.updateOne({ name : "Charlie" } , {$set : { age : 4 }})

다중 업데이트 - db.[DB명].updateMany({ [업데이트 대상] } , {$set : {업데이트 내용}})
ex) db.dogs.updateMany({ catFriendly : true } , {$set : {isAvailable : false}})

수정 일자 - $currentDate : {lastChanged: true} (현재 날짜를 수정일로 넣는다.)
ex) db.dogs.updateMany({ catFriendly : true } , {$set : {isAvailable : false} $currentDate : {lastChanged: true}})

3. Deleted
삭제 - db.[DB명].deleteOne({ [대상] })
ex) db.dogs.deleteOne({ name : "Charlie" })

다중 삭제 - db.[DB명].deleteMany({ [대상] }) ( ({}) = 아무것도 넣지 않으면 전체 삭제)
ex) db.dogs.deleteMany({ isAvailable : false })
