Sphinx Deco
===========


Overview
--------

Sometimes you'd like for documentation rendered within a Sphinx framework to "match"
the rest of your site theme.  Because all HTML pertinent to Sphinx-generated docs ultimately comes from .rst files, traditional coding of HTML source, CSS and JS to render HTML
doesn't work quite the same. 

This handy guide to help content authors, editors and web designers work together. Time spent developing and contributing to this guide has the potential to significantly reduce lag in release cycles when efforts are coordinated.



Styling Docs with Sphinx ReST
-----------------------------

Web developers familiar with HTML5 and CSS3 will recognize these W3C standards. 
They are followed by their respective :literal:`.rst` definitions.

::

	===========================				=================================
	HTML5 + CSS						ReST with directives
	===========================				=================================							
	<container class="classname">	  			.. container:: [container classname]
	---------------------------				---------------------------------
	<img src="img.png">					..img:: img.png
	.img {								
		height: 80px;			  		:height: 80px
		width: 30px;			  		:width:  30px
		align: left;			  		:align:  left
		target: target.ref;				:target: target.ref
	}					   									
	---------------------------				---------------------------------
	<strong>						*Bold Text*
	---------------------------				---------------------------------
	<em>							**Emphasized Italics Text**
	---------------------------				---------------------------------
	<ul>							* Bullet item A 
	   <li>							* Bullet Item B
	                              		  		  * Sub-bullet item A
	                              		  		  * Sub-bullet item B
	---------------------------				--------------------------------- 			
	<ol>							#. Ordered bullet item 1
	   <li>							#. Ordered bullet item 2
  
	---------------------------				--------------------------------- 			
	<sup>Superscript</sup>					:sup:`Superscript`\
	
	<sub>Subscript</sub>					:sub:`Subscript`\

	---------------------------				---------------------------------
	<a link="#anchorref">					.._anchorref: /*internal to doc or project*/
								.._anchorref text Link:
	---------------------------				--------------------------------- 			
	<a href="http://intel.com">Intel</a>			.._externallink: http://intel.com
	
	
	---------------------------				--------------------------------- 			
	Various							.. [1] footnote_1
	
								Text point to footnote_1 [1]_
	
	---------------------------				--------------------------------- 			
	<div id="admonition" title="">				.. admonition:: title
	 #admonition {
	 /** block-level css **/
 	     background: red;
	     font: bold;  
		 .title { 
		 /** class-level css **/ }
		 text-shadow: 0.2 em;
	 }

	---------------------------				--------------------------------- 			

	<div id="important"></div>				.. important::
	 #important {
	  /** block-level css **/ 				   Skip a line and enter imporant content.
	  }				
	
	<div id="attention"></div>				.. attention::
	 #attention {
	 /** block-level css **/
	 }
	 
	<div id="note">						.. note::
	<div id="notice">					.. notice::
	<div id="hint">						.. hint::
	<div id="warning">					.. warning::
	...							...
	
	etc.							etc.

	---------------------------				--------------------------------- 			

	<div class="guilabel">					:guilabel:
	.guilabel {
	/** class-level css **/
	font-size: 1.3em;
	color: #555;
	background-color: #e0e0e0;
	}

	---------------------------				--------------------------------- 			

	<!-- This is a source-readable
	HTML comment. -->					.. This is a source-readable ReST comment.

	---------------------------				--------------------------------- 			
	
	<img src="FIGURE-1.png">				.. figure::
	<div class="caption">caption text</div>			   :height: 133 px
	img {margin-left: 10%;					   :caption: caption text	
	      margin-top: 20px; } 					
	.caption {font-size: 80%;
		  text-align: left;
		  font-weight: lighter; }

	---------------------------				--------------------------------- 			
	Annotate as raw code					Annotate as raw w/syntax highlighting
	++++++++++++++++++++					+++++++++++++++++++++++++++++++++++++
	
	<code class="inline">inline code</code>			``inline code``
	
	<code>							.. codeblock::
								   :name: block target name	

	# test a 'Hello world' code block in Prolog		.. codeblock:: prolog
  	main :- write('Hello, world!'), nl.			    main :- write('Hello, world!'), nl.			  

  	# test a 'Hello, world' code block in Python 3		.. codeblock:: python
	print ("Hello, world")					   print ("Hello, world") 		
										
	# test a 'Hello, world' code block in Ruby		.. codeblock:: ruby
  	puts "Hello, world"					   puts "Hello, world"		
	</code>
	---------------------------				--------------------------------- 			
	Raw and literals					Raw and literals
	++++++++++++++++					++++++++++++++++

	<pre> plain txt </pre>					.. raw:: plain txt
	
	---------------------------				--------------------------------- 					
	<pre>							Preface to a literal code block::
	  <code>						
		Literal code block					Literal code block
	  </code>
	</pre>  
	
	===========================				=================================
