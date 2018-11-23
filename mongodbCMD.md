// Command

show dbs

// Add user 
 
db.createUser({
	user: "sagar",
	pwd: "sagard123456789",
	roles: ["readWrite", "dbAdmin"],
	passwordDigestor : "server"
});

// Create Collection

db.createCollection('customers');

// Command show all collections 
show collections

// Insert data into customers

db.customers.insert({first_name: "sagar", last_name: "dash"});

// get the data 

db.customers.find();

// Insert multiple data into customers collection

db.customers.insert([
	{first_name: "Amit", last_name: "Biswas"},
	{first_name: "Ikramul", last_name: "Haque"}
	
	]);

// update db

db.customers.update(
 	{first_name: "Amit"},
 	{first_name: "Jhon", last_name: "doe", gender: "male"}
);

/* 
In here we see we updated `first_name` `last_name` `gender` but if we use only one field for updte, Like if update only gender where jhon exist then we have to use SET operator.
*/
db.customers.update(
	{first_name: "Ikramul"},
	{$set: {gender: "male"}}
);

db.customers.update(
	{first_name: "Ikramul"},
	{$set: {age: 25}}
);

db.customers.update(
	{first_name: "Ikramul"},
	{$inc: {age: 5}}
);

db.customers.update(
	{first_name: "Ikramul"},
	{$unset: {age: 1}}
);



