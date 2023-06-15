## Install Dependencies:
1. pip install fastapi 
2. pip install "uvicorn[standard]"

## Run: 
python -m uvicorn main:app --reload

## Dokumentasi
![Cloud Architecture - BudgetIN]()

URL : [https://capstone-project-387701.et.r.appspot.com](https://capstone-project-387701.et.r.appspot.com/register) 
### Register 
- Endpoint : /register
- Method : POST
- Request Body :
<pre>
{
"nama": "John D",
"username": "johnd",
"email": "johnd@gmail.com",
"password": "password123"
}
 </pre>
- Response Body :<br>
		- Status 200 OK
		 <pre>{
		 "message": "User registered successfully"
		 }
     </pre>
		- Status 400 Bad Request<br>
		 <pre>{
		 "message": "Email or username already in use"
		 }
     </pre>
		- Status 500 Internal Server Error
		 <pre>{
		 "message": "Error registering user"
		 }
     </pre>
		

### Login
- Endpoint : /login
- Method : POST
- Request Body :
<pre>
{
"email": "johndoe@example.com",
"password": "password123"
}
 </pre>
- Response Body :<br>
		- Status 200 OK<br>
		<pre>{
		 "success": true,
		 "message": "Login successful"
		 }</pre>
		- Status 401 Unauthorized<br>
		<pre>{
		 "message": "Invalid credentials"
		 }</pre>
		- Status 404 Not Found<br>
		<pre>{
		 "message": "User not found"
		 }</pre>
		- Status 500 Internal Server Error
		<pre>{
		 "message": "Error logging in"
		 }</pre>

### Budget
- Endpoint : /budget
- Method : POST
- Request Body :
<pre>
{
"userId": "user123",
"budgetAmount": 1000
}
 </pre>
- Response Body :<br>
		- Status 200 OK<br>
		<pre>{
		 "message": "Budget saved successfully"
		 }</pre>
		 - Status 500 Internal Server Error
		 <pre>{
		 "message": "Error saving budget"
		 }</pre>
- Endpoint : /budget/userId
- Method : GET
- Response Body :<br>
		- Status 200 OK<br>
		<pre>{
		 "budget": "1000"
		 }</pre>
		 - Status 404 Not Found
		 <pre>{
		 "message": "User not found"
		 }</pre>
		 - Status 500 Internal Server Error
		 <pre>{
		 "message": "Error retrieving budget"
		 }</pre>
- Endpoint : /budget/userId
- Method : PUT
- Request Body :<br><pre>{
		 "budgetAmount": "1500"
		 }</pre>
- Response Body :<br>
		- Status 200 OK<br>
		<pre>{
		 "message": "Budget updated successfully"
		 }</pre>
		 - Status 500 Internal Server Error
		 <pre>{
		 "message": "Error updating budget"
		 }</pre>
- Endpoint : /budget/userId
- Method : DELETE
- Response Body :<br>
		- Status 200 OK<br>
		<pre>{
		 "message": "Budget deleted successfully"
		 }</pre>
		 - Status 500 Internal Server Error
		 <pre>{
		 "message": "Error deleting budget"
		 }</pre>

