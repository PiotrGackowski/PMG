
# Task 1: Test cases for Registration Form component

# Table of contents	
1. [Introduction](#introduction)
2. [Test cases](#testcases)
	1. [Core tests](#coretests)
		1. [CORE-001 User is able to register when he put correct data](#core001)	
		2. [CORE-002 User is not able to register when user with the same data is already in system](#core002)	
		3. [CORE-003 User is not able to register when he won’t provide any data](#core003)	
	2. [Email field tests](#emailtests)
		1. [EMAIL-001 User is not able to register when he provide email without "@" character](#email001)	
		2. [EMAIL-002 User is not able to register when he provide email without top domain](#email002)	
		3. [EMAIL-003 User is not able to register when he provide email with two "@" characters](#email003)	
		4. [EMAIL-004 User is not able to register when he provide email with multiple dots](#email004)	
		5. [EMAIL-005 User is not able to register when he provide email with text followed](#email005)	
	3. [Password and Confirm Password fields tests](#passtest)
		1. [PASS-001 User is not able to register when he didn’t provide password](#pass001)	
		2. [PASS-002 User is not able to register when he didn’t fill "Confirm Password"](#pass002)	
		3. [PASS-003 User is not able to register when values from password fields are not equal.](#pass003)	
		4. [PASS-004 User is not able to copy password between "Password" and "Confirm Password" fields using mouse commands.](#pass004)	
		5. [PASS-005 User is not able to copy password between "Password" and "Confirm Password" fields using keyboard shortcuts.](#pass005)	
		6. [PASS-006 Password field have correct type](#pass006)	
	4. [Name field tests](#nametest)
		1. [NAME-001 User is not able to register when he put only space in Last Name field](#name001)	
		2. [NAME-002 User is able to register when he use arabic or japanese characters in Last Name field](#name002)	
	5. [Other tests](#othertest)
		6. [USABILITY-001 Tabindex is set correct](#other001)	


# <a name="introduction"></a> Introduction	

As I didn't have any documentation except how component looks I made some assumptions during test case creations:

+ After user fill fields and press "Register" button there is some page that he will be redirected. This page will contain only information "User was registered".

+ Tester have access to database or some admin tool that allow to verify that user was registered

+ Supported browsers: Google Chrome in *desktop mode* on Windows 10 platform.

+ Only limit for Password field about how strong password user should use is "there should be not empty password or it should not be space". For example: no requirements for how long password should be or letters/special characters/numbers need to be used by user. 

+ All fields should be filled with data to register user. 

If this assumptions are not true, then some of test cases need to be changed and/or new testcases will be needed.


# <a name="testcases"></a> Test cases 
## <a name="coretests"></a> Core tests 



### <a name="core001"></a> CORE-001 User is able to register when he put correct data

**ID**: CORE-001

**Name**: User is able to register when he put correct data

**Priority** (high/medium/low): high

**Description**: We want to be sure that system in typical correct situation is working correct. Put correct data and expect that user will be able to register.

**Preconditions**: User with parameters as in Step 1 is not present in system.

**Steps**:

Step 1. Put such values in fields:

>+ E-mail: example@example.com

>+ Password: password

>+ Confirm Password: password

>+ Last Name: Smith

Step 2. Press "Register" button.

**Expected**:

+ "User is registered" page is visible.

+ Correct user data are visible in admin logs or database.




### <a name="core002"></a> CORE-002 User is not able to register when user with the same data is already in system.

**ID**: CORE-002

**Name**: User is not able to register when user with the same data is already in system.

**Priority** (high/medium/low): high

**Description**: We want to test situation that user with the same data is not able to register.

**Preconditions**: In system there is registered user with such data: 

>+ E-mail: example@example.com

>+ Password: password

>+ Last Name: Smith

**Steps**:

Step 1. Put such values in fields:

>+ E-mail: example@example.com

>+ Password: password

>+ Confirm Password: password

>+ Last Name: Smith

Step 2: Press "Register" button

**Expected**:

+ "User is registered" page is not visible.

+ There is some alert that such user is already in system.



### <a name="core003"></a> CORE-003 User is not able to register when he won’t provide any data

**ID**: CORE-003

**Name**: User is not able to register when he won’t provide any data

**Priority** (high/medium/low): high

**Description**: We want to be sure that system in incorrect situation is reacting correct. Press “Register” button and expect that user will not be able to register.

**Preconditions**:  User didn’t fill any field

**Steps**:

Step 1. Press "Register" button

**Expected**:

+ User stays on a page with Registration Form component and is not redirected to any other page

+ "User is registered" page is not visible.

+ Some kind of alert message is visible. In this alert all required fields are mentioned and information that user should provide data is visible.



## <a name="emailtests"></a> Email field tests




### <a name="email001"></a> EMAIL-001 User is not able to register when he provide email without "@" character

**ID**: EMAIL-001

**Name**: User is not able to register when he provide email without "@" character. 

**Priority** (high/medium/low):medium 

**Description**: 

**Preconditions**:  

+ User didn’t fill any field. 

+ Test user don't exist in system.

**Steps**:

Step 1. Put such values in fields:

>+ E-mail: example.example.com

>+ Password: password

>+ Confirm Password: password

>+ Last Name: Smith

Step 2: Press "Register" button

**Expected**:

+ "User is registered" page is not visible.

+ Alert message about incorrect email is visible.



### <a name="email002"></a> EMAIL-002 User is not able to register when he provide email without top domain


**ID**: EMAIL-002

**Name**: User is not able to register when he provide email without top domain

**Priority** (high/medium/low): medium

**Description**: 

**Preconditions**:  

**Steps**:

Step 1. Put such values in fields:

>+ E-mail: example@example

>+ Password: password

>+ Confirm Password: password

>+ Last Name: Smith

Step 2: Press "Register" button

**Expected**:

+ "User is registered" page is not visible.

+  Alert message about incorrect email is visible.



### <a name="email003"></a> EMAIL-003 User is not able to register when he provide email with two "@" characters

**ID**: EMAIL-003

**Name**: User is not able to register when he provide email with two "@" characters

**Priority** (high/medium/low): medium

**Description**: 

**Preconditions**:  

**Steps**:

Step 1. Put such values in fields:

>+ E-mail: example@example@example.com

>+ Password: password

>+ Confirm Password: password

>+ Last Name: Smith

Step 2: Press "Register" button

**Expected**:

+ "User is registered" page is not visible.

+ Alert message about incorrect email is visible.



### <a name="email004"></a> EMAIL-004 User is not able to register when he provide email with multiple dots


**ID**: EMAIL-004

**Name**: User is not able to register when he provide email with multiple dots

**Priority** (high/medium/low): medium

**Description**: 

**Preconditions**:  

**Steps**:

Step 1. Put such values in fields:

>+ E-mail: example@example..com

>+ Password: password

>+ Confirm Password: password

>+ Last Name: Smith

Step 2: Press "Register" button

**Expected**:

+ "User is registered" page is not visible.

+ Alert message about incorrect email is visible.



### <a name="email005"></a> EMAIL-005 User is not able to register when he provide email with text followed


**ID**: EMAIL-005

**Name**: User is not able to register when he provide email with text followed

**Priority** (high/medium/low): medium

**Description**: 

**Preconditions**:  

**Steps**:

Step 1. Put such values in fields:

>+ E-mail: example@example.com RandomText

>+ Password: password

>+ Confirm Password: password

>+ Last Name: Smith

Step 2: Press "Register" button

**Expected**:

+ "User is registered" page is not visible.

+ Alert message about incorrect email is visible.



## <a name="passtest"></a> Password and Confirm Password fields tests


### <a name="pass001"></a> PASS-001 User is not able to register when he didn’t provide password

**ID**: PASS-001

**Name**: User is not able to register when he didn’t provide password 

**Priority** (high/medium/low): high 

**Description**: 

**Preconditions**:  

**Steps**:

Step 1. Put such values in fields:

>+ E-mail: example@example.com

>+ Last Name: Smith

Leave "Password" and "Confirm Password" fields empty 

Step 2: Press "Register" button

**Expected**:

+ "User is registered" page is not visible.

+ Alert message about incorrect password is visible.




### <a name="pass002"></a> PASS-002 User is not able to register when he didn’t fill "Confirm Password"


**ID**: PASS-002

**Name**: User is not able to register when he didn’t fill "Confirm Password"

**Priority** (high/medium/low): high 

**Description**: 

**Preconditions**:  

**Steps**:

Step 1. Put such values in fields:

>+ E-mail: example@example.com RandomText

>+ Password: password

>+ Last Name: Smith

Leave "Confirm Password" field empty.

Step 2: Press "Register" button

**Expected**:

+ "User is registered" page is not visible.

+ Alert message about empty "Confirm Password" is visible.




### <a name="pass003"></a> PASS-003 User is not able to register when values from password fields are not equal.


**ID**: PASS-003

**Name**: User is not able to register when values from password fields are not equal.

**Priority** (high/medium/low): high 

**Description**: 

**Preconditions**:  

**Steps**:

Step 1. Put such values in fields:

>+ E-mail: example@example.com

>+ Password: password

>+ Confirm Password: password1

>+ Last Name: Smith

Step 2: Press "Register" button

**Expected**:

+ "User is registered" page is not visible.

+ Alert message about values from password fields are not equal is visible.



### <a name="pass004"></a> PASS-004 User is not able to copy password between "Password" and "Confirm Password" fields using mouse commands.


**ID**: PASS-004

**Name**: User is not able to copy password between "Password" and "Confirm Password" fields using mouse commands.

**Priority** (high/medium/low): low

**Description**: 

**Preconditions**:  

**Steps**:

Step 1. Put such values in fields:

>+ E-mail: example@example.com

>+ Password: password

>+ Last Name: Smith

Leave "Confirm Password" field empty.

Step 2: Mark data in "Password" field by mouse.

Step 3: By right click of mouse try to copy value from "Password" field to "Confirm Password" field.

Step 4: Press "Register" button. Check if result is as in Expected result.

Step 5: Repeat steps 1-4 but this time put such data in field:

>+ E-mail: example@example.com

>+ Confirm Password: password

>+ Last Name: Smith

Leave "Password" field empty.

And try to copy password from "Confirm Password" to "Password" field.

**Expected**:

+ "User is registered" page is not visible.

+ Alert message that user is not able to copy password is visible. 




### <a name="pass005"></a> PASS-005 User is not able to copy password between "Password" and "Confirm Password" fields using keyboard shortcuts.

**ID**: PASS-005

**Name**: User is not able to copy password between "Password" and "Confirm Password" fields using keyboard shortcuts.

**Priority** (high/medium/low): low

**Description**: 

**Preconditions**:  

**Steps**:

Step 1. Put such values in fields:

>+ E-mail: example@example.com

>+ Password: password

>+ Last Name: Smith

Leave "Confirm Password" field empty.

Step 2: Mark data in "Password" field by keyboard shortcuts (try puting cursor in field and press CTRL + A or put cursor at end of password and hold SHIFT + LEFT ARROW).

Step 3: Using combination CTRL+C and CTRL+V try to “copy” value from "Password" field to "Confirm Password" field.

Step 4: Press "Register" button. Check if result is as in Expected result.

Step 5: Repeat steps 1-4 but this time put such data in field:

>+ E-mail: example@example.com

>+ Confirm Password: password

>+ Last Name: Smith

Leave "Password" field empty.

And try to copy password from "Confirm Password" to "Password" field.

**Expected**:

+ "User is registered" page is not visible.

+ Alert message that user is not able to copy password is visible. 





### <a name="pass006"></a> PASS-006 Password field have correct type


**ID**: PASS-006

**Name**: Password field have correct type

**Priority** (high/medium/low): low

**Description**: 

**Preconditions**: If it’s not specified in test strategy what system browsers project should support, tester should use Google Chrome browser in newest version in production build, as this is currently most commonly used browser (state for January 2017).

**Steps**:

Step 1: 

Write some standard letter in Password field.

*Expected*: When user is writing any character in Password field he see "*" or similar signs. No other characters should be displayed. 

Step 2. 

Write some number in Password field.

*Expected*: When user is writing any character in Password field he see "*" or similar signs. No other characters should be displayed. 

Step 3. 

Write some special character in Password field. 

*Expected*: When user is writing any character in Password field he see "*" or similar signs. No other characters should be displayed. 

Step 4: 

Right click on “password” field. Choose “Inspect element” from menu.

Step 5: 

Check that entry field for password have type="password" attribute. Below there is code from such field on Google Gmail page with such attribute.

> `<input id="Passwd" name="Passwd" type="password" placeholder="Password" class="">`


*Expected*: Password field should have type="password" attribute.



## <a name="nametest"></a> Name field tests




### <a name="name001"></a> NAME-001 User is not able to register when he put only space in Last Name field

**ID**: NAME-001

**Name**: User is not able to register when he put only space in Last Name field

**Priority** (high/medium/low): medium

**Description**: 

**Preconditions**:  

**Steps**:

Step 1. Put such values in fields:

>+ E-mail: example@example.com

>+ Password: password

>+ Confirm Password: password

Put space character in in Last Name.

Step 2: Press "Register" button

**Expected**:

+ "User is registered" page is not visible.

+ Alert message about empty Last Name field is visible.




### <a name="name002"></a> NAME-002 User is able to register when he use arabic or japanese characters in Last Name field

**ID**: NAME-002

**Name**: User is able to register when he use arabic or japanese characters in Last Name field

**Priority** (high/medium/low): medium

**Description**: 

**Preconditions**:  

**Steps**:

Step 1. Put such values in fields:

>+ E-mail: example@example.com

>+ Password: password

>+ Confirm Password: password

Step 2: Put “ウィキペディアについて“  in Last Name.

Step 3: Press "Register" button

*Expected*: 

+ "User is registered" page is visible.

+ User is registered in system

Step 4: Repeat steps 1-3 but with such values:

>+ E-mail: example@example.com

>+ Password: password

>+ Confirm Password: password

>+ Last Name: الصفحة الرئيسية


*Expected*: 

+ "User is registered" page is visible.

+ User is registered in system



## <a name="othertest"></a> Other tests





### <a name="other001"></a> USABILITY-001 Tabindex is set correct


**ID**: USABILITY-001

**Name**: Tabindex is set correct

**Priority** (high/medium/low): medium

**Description**: 

**Preconditions**:  Registration Form component is only component on page and no other part of page should have tabindex set.

**Steps**:

Step 1: Open page with Registration Form component.

Step 2: Put cursor in E-Mail entry field. 

Step 3: Press TAB button

*Expected*: Cursor is in Password entry field.

Step 4: Press TAB button

*Expected*: Cursor is in Confirm Password entry field.

Step 5: Press TAB button.

*Expected*: Cursor is in Last Name entry field.

Step 6: Press TAB button.

*Expected*: Button Register is marked.

Step 7: Press TAB button

*Expected*: Cursor is in E-Mail entry field.




