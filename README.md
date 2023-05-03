Download Link: https://assignmentchef.com/product/solved-cs2123-data-structures-assignment-2-stacks
<br>
<strong style="font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen-Sans, Ubuntu, Cantarell, 'Helvetica Neue', sans-serif;">Evaluate Postfix (10 points)</strong>

Sketch of algorithm for evaluating postfix strings:

<ul>

 <li>Create stack <em>s</em>.</li>

 <li>For each token, <em>x</em>, in the postfix expression: 1 If <em>x </em>is T or F push it into the stack <em>s</em>.

  <ul>

   <li>Else if <em>x </em>is a unary operator i pop an operand, <em>op</em>1, from <em>s</em>

    <ul>

     <li>compute <em>x op</em>1 (see unary table below)</li>

     <li>push the result into <em>s</em></li>

    </ul></li>

   <li>Else if <em>x </em>is a binary operator i pop an operand, <em>op</em>2, from <em>s </em>ii pop an operand, <em>op</em>1, from <em>s</em></li>

  </ul></li>

</ul>

iii compute <em>op</em>1 <em>op</em>2 <em>x </em>iv push the result into <em>s</em>

<ul>

 <li>If you do not have enough operands in <em>s </em>to perform an operation you should return an error in the boolean.</li>

 <li>Likewise, if <em>s </em>contains more than one operand after all of the tokens are evaluated you should return an error in the boolean.</li>

 <li>Otherwise pop and return the only value in <em>s</em>.</li>

</ul>

Unary operations:

<table width="410">

 <tbody>

  <tr>

   <td width="205"><em>op</em>1 NOT</td>

   <td width="205">!<em>op</em>1</td>

  </tr>

 </tbody>

</table>

Binary operations:

<table width="410">

 <tbody>

  <tr>

   <td width="205"><em>op</em>1 <em>op</em>2 AND</td>

   <td width="205"><em>op</em>1 &amp;&amp; <em>op</em>2</td>

  </tr>

  <tr>

   <td width="205"><em>op</em>1 <em>op</em>2 NAND</td>

   <td width="205">!(<em>op</em>1 &amp;&amp; <em>op</em>2)</td>

  </tr>

  <tr>

   <td width="205"><em>op</em>1 <em>op</em>2 OR</td>

   <td width="205"><em>op</em>1 || <em>op</em>2</td>

  </tr>

  <tr>

   <td width="205"><em>op</em>1 <em>op</em>2 NOR</td>

   <td width="205">!(<em>op</em>1 || <em>op</em>2)</td>

  </tr>

  <tr>

   <td width="205"><em>op</em>1 <em>op</em>2 XOR</td>

   <td width="205"><em>op</em>1 ! = <em>op</em>2</td>

  </tr>

  <tr>

   <td width="205"><em>op</em>1 <em>op</em>2 COND</td>

   <td width="205">!<em>op</em>1 || <em>op</em>2</td>

  </tr>

  <tr>

   <td width="205"><em>op</em>1 <em>op</em>2 BICOND</td>

   <td width="205"><em>op</em>1 == <em>op</em>2</td>

  </tr>

 </tbody>

</table>

<strong>Convert Infix to Postfix (10 points)</strong>

Sketch of algorithm for converting postfix strings to infix strings:

<ul>

 <li>Create stack <em>s</em>.</li>

 <li>For each token, <em>x</em>, in the postfix expression: 1 If <em>x </em>is T or F push it into the stack <em>s</em>.

  <ul>

   <li>Else if <em>x </em>is a unary operator i pop an operand, <em>op</em>1, from <em>s</em>

    <ul>

     <li>push the string “(<em>op</em>1 <em>x</em>)” into <em>s</em></li>

    </ul></li>

   <li>Else if <em>x </em>is a binary operator i pop an operand, <em>op</em>2, from <em>s </em>ii pop an operand, <em>op</em>1, from <em>s</em>

    <ul>

     <li>push the string “(<em>op</em>1 <em>x op</em>2)” into <em>s</em></li>

    </ul></li>

   <li>You assume that the postfix string is well formatted (feel free to implement error checking if you would like).</li>

   <li>pop and return the value in <em>s</em>.</li>

  </ul></li>

</ul>

<strong>Hints for memory management:</strong>

<ul>

 <li>Every string that you push into your stack should be malloc-ed.</li>

 <li>You should free strings after popping them (be sure to use them before freeing them).</li>

 <li>Operator tokens will be freed after usage since they are not put into the stack.</li>

</ul>

<strong>Deliverables:</strong>

Your solution should be submitted as “booleanEvaluation.c”,

“booleanEvaluation.h”, and “makefile”. Also attach any additional files you create to solve this problem.

Upload these file to Blackboard under Assignment 2. <strong>Do not zip your files</strong>.

To receive full credit, your code must compile and execute. You should use valgrind to ensure that you do not have any memory leaks.


