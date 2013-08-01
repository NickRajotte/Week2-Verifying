Week2-Verifying
===============
<!DOCTYPE html>
<html>
<head>
<style>
  html, body {
		font-size: 100%;
	}
	
	label {
		font-weight: bold;
		font-size: 130%;
	}
	
	fieldset {
		width: 800px;
		margin-left: 30px;
		margin-right: auto;
	}
	
	input {
		font-size: 120%;
	
	}
	
	input[type=button] {
		border: 1px solid #6E329D;
		border-radius : 25px;
		color: #fff;
		text-decoration: none;
		padding: 0.2em 0.5em;
		margin: 0.5em;
		margin-left: auto;
		margin-right: auto;
		
		background: #000;
	}
	
	input[type=text] {
		border: 1px solid green;
	}
	
	input[type=button]:hover {
		background: #00c;
	}
	
	input[type=text]:hover {
		background-color: #e9f6fd;
	}
	
	
	.error {
		color: red;
	}
	
	input[type=text].bad {
		border: 4px solid red;
	}
	
	input[type=text].good {
		border: 4px solid green;
	}
	
	textarea.bad {
		border: 4px solid red;
	}
	
	textarea.good {
		border: 4px solid green;
	}
	
	
</style>
</head>
<body>

<form name="mainform" action="">
	<fieldset>
		<legend>Contact information:</legend>
		<label for="firstname">First Name:</label> <input id="fname" name="fname" type="text" size="30" placeholder="First Name"  /> <span class="error" id="err_fname"></span> <br /><br />
		
		<label for="lname">Last Name:</label> <input id="lname" name="lname" type="text" size="30" placeholder="Last Name"  /> <span class="error" id="err_lname"></span> <br /><br />
		
		<label for="email">E-mail:</label> <input id="email" name="email" type="text" size="30" placeholder="sample@email.com"  /> <span class="error" id="err_email"></span> <br /><br />
		
		<label for="Comments">Comments:</label>
		<textarea rows="5" cols="45" name="comments"  id="Comments">

		</textarea><span class="error" id="err_Comments"></span>
		<br /><br />
		
		<input type="button" value="submit" onclick="submitForm();" />
	</fieldset>
</form>

<script>
	function submitForm() {
		
		var fname = document.getElementById('fname');
			
			
		
			
		if ( !fname.value.length ) {
			err_fname.innerHTML = "*";
			fname.className = "bad";
			hasErrors = true;
		} else {
			err_fname.innerHTML = "";
			fname.className = "good";
		}
		
		/*
		if ( hasErrors ) {
			alert("First Name is no good");
		} else {
			alert("First Name is good");
		}
		*/
		var lname = document.getElementById('lname');
			
			
		var hasErrors = false;
			
		if ( !lname.value.length) {
			err_lname.innerHTML = "*";
			lname.className = "bad";
			hasErrors = true;
		} else {
			err_lname.innerHTML = "";
			lname.className = "good";
		}
		
		/*
		if ( hasErrors ) {
			alert("Must Enter a last name");
		} else {
			alert("Last name is good to go");
		}
			*/
var email = document.getElementById('email');
			
			
		var hasErrors = false;
			
		if ( !email.value.length || email.value.indexOf("@") == -1 || email.value.indexOf(".") == -1 ) {
			err_email.innerHTML = "*";
			email.className = "bad";
			hasErrors = true;
		} else {
			err_email.innerHTML = "";
			email.className = "good";
		}
		
		/*
		if ( hasErrors ) {
			alert("Email is no good");
		} else {
			alert("Email is good");
		}	
		*/
		
		
		var Comments = document.getElementById('Comments');
		var err_Comments = document.getElementById('err_Comments');
			
		
			
		if ( !Comments.value.length ) {
			err_Comments.innerHTML = "<em>*</em>";
			Comments.className = "bad";
			hasErrors = true;
		} else {
			err_Comments.innerHTML = "";
			Comments.className = "good";
		}
	
	}
	
	
</script>
</body>
</html>
