# Login-Page-WebSite---MYSQL
Login Page WebSite - MYSQL


<!DOCTYPE html>
<html lang="en">
<head>

    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dadiva Jovem</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Raleway:wght@300;400;500;600&family=Oswald:wght@600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="css/all.min.css"> <!-- fontawesome -->
    <!-- <link href="https://unpkg.com/tailwindcss@^2/dist/tailwind.min.css" rel="stylesheet"> -->
    <link rel="stylesheet" href="css/tailwind.css">
    <link rel="stylesheet" href="css/tooplate-antique-cafe.css">
    <title>Document</title>
</head>
<body style="background-image: url('antique-cafe-bg-01.jpg'); background-size: cover">
    
   <div style="height: 50px">
        <div id="intro" class="parallax-window" data-parallax="scroll" >
            <nav id="tm-nav" class="fixed w-full">
                <div class="tm-container mx-auto px-2 md:py-6 text-right">
                    <button class="md:hidden py-2 px-2" id="menu-toggle"><i class="fas fa-2x fa-bars tm-text-gold"></i></button>
                    <ul class="mb-3 md:mb-0 text-2xl font-normal flex justify-end flex-col md:flex-row">
                        <li class="inline-block mb-4 mx-4"><a href="index.html" class="tm-text-gold py-1 md:py-3 px-4">Home</a></li>
                        <li class="inline-block mb-4 mx-4"><a href="index.html#about" class="tm-text-gold py-1 md:py-3 px-4">Quem Somos</a></li>
                        <li class="inline-block mb-4 mx-4"><a href="registo.php" class="tm-text-gold py-1 md:py-3 px-4">Registo</a></li>
                    </ul>
                </div>            
            </nav>
        </div>
    </div>

        <div class="flex-1 rounded-xl p-12 pb-14 m-5 bg-black bg-opacity-50 tm-item-container" style="margin-top: 70px; margin-left: 450px">
        <h3 style="color: white;  text-align: center;">Faça login para fazer a sua marcação</h3>   
        <form  method="POST" class="text-lg" action="">
                    <input type="email" name="email" class="input w-full bg-black border-b bg-opacity-0 text-white px-0 py-4 mb-4 tm-border-gold" placeholder="Email" required="" />
                    <input type="password" name="senha" class="input w-full bg-black border-b bg-opacity-0 text-white px-0 py-4 mb-4 tm-border-gold" placeholder="Password"/>
                    <div class="text-right">
                    <button type="submit" class="text-white hover:text-yellow-500 transition">Send it</button>
                </div>                        
                </form>
        </div>

    </body>
</html>

<?php

	require_once 'user.php';
	$Userssession=new Session;
	if (isset($_POST['email']))
	{
		if(!empty($_POST['email']) && !empty($_POST['senha'])){
	
		$Userssession->connect("pap","localhost","root","");
		$Userssession->login($_POST['email'], $_POST['senha']); 
        $_SESSION["Email"] = $_POST['email']; 

		}else{

		echo "preencha os campos";

		}
		
	}
	

?>
