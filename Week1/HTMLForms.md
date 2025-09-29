
## 📝HTML Forms & Inputs
### 📌 **Basic Structure**
```
<form action="submit.html" method="post">
    <!-- Input fields go here -->
</form>
```
-   `action` → the page or URL where the form data is sent
    
-   `method` → how the data is sent (`GET` or `POST`)

### **Common Input Types**
1️⃣ **Text, Password and Email  Input**
```
<!-- Text Input -->
<label for="name">Name:</label>
<input type="text" id="name" name="name" placeholder="Enter your name"> 

<!__ Password Input __>
<label for="password">Password:</label>
<input type="password" id="password" name="password" placeholder="Enter password">

<!__ Email Input __>
<label for="email">Email:</label>
<input type="email" id="email" name="email" placeholder="Enter your email">
```
2️⃣**Radio Buttons**
```
<p>Gender:</p>
<input type="radio" id="male" name="gender" value="male">
<label for="male">Male</label>
<input type="radio" id="female" name="gender" value="female">
<label for="female">Female</label>
```

-   Only **one option can be selected** per `name`

**3️⃣Checkboxes**
```
<p>Hobbies:</p>
<input type="checkbox" id="reading" name="hobby" value="reading">
<label for="reading">Reading</label>
<input type="checkbox" id="sports" name="hobby" value="sports">
<label for="sports">Sports</label>
```
-   Multiple options **can be selected**

4️⃣**Submit Button**
```
<input type="submit" value="Submit">
```
-   Sends the form data to the page specified in `action`


## Textarea & Select Dropdown

### Textarea (for multi-line text)

```
<label  for="message">Message:</label>
<br>
 <textarea  id="message"  name="message"  rows="4"  cols="30"  placeholder="Write your message"></textarea>
``` 

### Select Dropdown

```
<label  for="country">Country:</label>
 <select  id="country"  name="country">
  <option  value="usa">USA</option>
   <option  value="uk">UK</option> 
   <option  value="india">India</option>
    </select>
    ```