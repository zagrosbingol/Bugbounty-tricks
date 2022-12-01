**basic**

<div>
  <link rel="stylesheet" href="https://pentesterlab.com/onedark.min.css">
</div>

<div class="display-9 l-space-half fw-bold mb-1 text-uppercase">This challenge</div>

<p>Here, you need to start using the functionality as it was intended to be used. This will give you an idea of what the code does.</p>

<p>You can see that you provide an IP address and that the application is running the command <code class="code-alt">ping</code> with the IP address we provided.</p>

<p>It’s running a command. Let see if there is some way to abuse this functionality.</p>

<p>By doing some research, you will find that there is a type of attack referred to as command injection.</p>

<div class="display-9 l-space-half fw-bold mb-1 text-uppercase">Command injection</div>

<p>Command injection can be used to run arbitrary commands on a server. </p>

<p>Multiple payloads can be used to trigger this behaviour. For example, let’s say that the initial command is: </p>

<pre class="shadow"><code>ping [parameter]</code></pre>

<p>Where <code class="code-alt">[parameter]</code> is the value you provided in the form or in the URL.</p>

<p>If you look at how the command line works, you will find that there are multiple ways to add more commands:</p>

<ul>
  <li><code class="code-alt">command1 && command2</code> that will run <code class="code-alt">command2</code> if <code class="code-alt">command1</code> succeeds.</li>
  <li><code class="code-alt">command1 || command2</code> that will run <code class="code-alt">command2</code> if <code class="code-alt">command1</code> fails.</li>
  <li><code class="code-alt">command1 ; command2</code> that will run <code class="code-alt">command1</code> then <code class="code-alt">command2</code>.</li>
  <li><code class="code-alt">command1 | command2</code> that will run <code class="code-alt">command1</code> and send the output of <code class="code-alt">command1</code> to <code class="code-alt">command2</code>.</li>
  <li>...</li>
</ul>

<p>In this application, we can provide a parameter to <code class="code-alt">command1</code>, but there is no <code class="code-alt">command2</code>. What we are going to do is add our own command.</p>

<p>Instead of sending the <code class="code-alt">[parameter]</code> to the command:</p>

<p><code class="code-alt">ping 127.0.0.1</code></p>

<p>Where <code class="code-alt">127.0.0.1</code> is our <code class="code-alt">[parameter]</code>. We are going to send a malicious <code class="code-alt">[parameter]</code> that will contain another command:</p>

<pre class="shadow"><code>ping <b>127.0.0.1 ; cat /etc/passwd</b></code></pre>

<p>The application will think that <code class="code-alt">127.0.0.1 ; cat /etc/passwd</code> is just a parameter to run <code class="code-alt">command1</code>. But we actually injected <code class="code-alt">command2</code>: <code class="code-alt">cat /etc/passwd</code>.</p>


---------------------------------------

**Filter bypasses:**
add these at the nd of the parameter, try as well sepearting with above delimitators
$(ls)
`ls`
