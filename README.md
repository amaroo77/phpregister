<h1>Secure Register System Using PHP and mySQL.</h1>

<h3>Requirements</h3>

If you haven't got a local web server set-up, you will need to download and install XAMPP. XAMPP is a server-side web development environment that includes the essentials for back-end web developers.

<p>Follow the below instructions if you're using <i>phpMyAdmin</i>.</p>

<ul>
<link rel="stylesheet" type="text/css" href="readme.css">
<li>Navigate to: <i>http://localhost/phpmyadmin/</i></li>
<li>Click the <i>Databases</i> tab at the top</li>
<li>Under <i>Create database</i>, type in <i>phplogin</i> in the text box</li>
<li>Select <i>utf8_general_ci</i> as the collation</li>
<li>Click <i>Create</i></li>
</ul>
<p>You can use your own database name, but for this tutorial, I'm using <i>phplogin</i>.</p>
<p>What we need now is an <i>accounts</i> table as this will store all the accounts (usernames, passwords, emails, etc) that are registered with the system.</p>
<p>Click the database on the left side panel (<i>phplogin</i>) and execute the following SQL statement:</p>
<div class="code-header">
</div>
<pre>
<code class="language-sql">CREATE TABLE IF NOT EXISTS `accounts` (
	`id` int(11) NOT NULL AUTO_INCREMENT,
  	`username` varchar(50) NOT NULL,
  	`password` varchar(255) NOT NULL,
  	`email` varchar(100) NOT NULL,
    PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=2 DEFAULT CHARSET=utf8;

<p>INSERT INTO `accounts` (`id`, `username`, `password`, `email`) VALUES (1, &#039;test&#039;, &#039;$2y$10$SfhYIDtn.iOuCW7zfoFLuuZHX6lja4lF4XA4JqNmpiH/.P3zB8JCa&#039;, &#039;test@test.com&#039;);</p>
</code>
</pre>
<br>
<p>On <i>phpMyAdmin</i> this should look like:</p>
<div class="browser">

<img width="750" height="489" alt="phpMyAdmin Accounts Table" src="https://codeshack.io/web/img/phplogin/phpmyadmin-accounts-table.png" onerror="this.onerror=null;pagespeed.lazyLoadImages.loadIfVisibleAndMaybeBeacon(this);">
</div>

<p>The above SQL statement code will create the accounts table with the columns <i class="hl">id</i>, <i class="hl">username</i>, <i class="hl">password</i>, and <i class="hl">email</i>.</p>

<p>The SQL statement will insert a test account with the username: <i class="hl">test</i>, and the password: <i class="hl">test</i>. The test account will be used for testing purposes to make sure our login system is functioning correctly.</p>
