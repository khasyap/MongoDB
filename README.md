# MongoDB
MongoDB



use kk

db.createCollection("student")

db.student.insertMany([{"studentName":"srikrishna","studentAddress":"udupi","studentMarks":96},
                      {"studentName":"srijagannath","studentAddress":"puri","studentMarks":99}])

db.student.find();

db.student.find({studentMarks:{$gte:95}})


db.student.deleteOne({studentName:"srikrishna"})


db.student.drop()


db.student.updateOne({studentName:"srikrishna"},{$set:{studentAddress:"dwaraka"}})


db.createCollection("placements")

db.placements.insertOne({"company":"TCS","salary":"700000","location":"Hyd",studentId:ObjectId('688c50bec1308ac4dab38e11')})

db.student.aggregate({

	$lookup:{
		from:"placements",
		localField:_id,		
		foreignField:studentId
		as:"student placements"
		}

})


