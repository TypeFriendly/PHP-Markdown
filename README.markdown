PHP Markdown Extra Fork
=======================

This fork has been created to fix a bug (or bugs) in PHP Markdown Extra, found during writting docs in TypeFriendly.

HTML tags in code block in blockquote bug
-----------------------------------------

*Reported to Michel, no response on that.* HTML code put in code block breaks a blockquote. There is a one line of Regex responsible for that, when removed - it works OK. However, I'm not sure what was the purpose of that line. I tested my version on Michel's test suite, also on tons of my makrdown files and I don't see any side effects. 

#### Markdown source:

    something
    
    > lorem ipsum
    > 
    >     Neva use teh power.
    >
    > result
    > 
    >     w00t?
    >     <p>Neva use teh power.</p>
    >     why?
    > 
    > foo bar
    
    whatever
    
#### Generated output:

    <p>something</p>
    
    <blockquote>
      <p>lorem ipsum</p>

    <pre><code>Neva use teh power.
    </code></pre>
      
      <p>result</p>

    <pre><code>w00t?
    </code></pre>
    </blockquote>

    <p>Neva use teh power.</p>

    <blockquote>
    <pre><code>why?
    </code></pre>
      
      <p>foo bar</p>
    </blockquote>

    <p>whatever</p>
    
Copyright and License
=====================

PHP Markdown Extra Fork  
Copyright (c) 2009-2010 Jacek Jędrzejewski  
<http://www.jacek.jedrzejewski.name/>  
All rights reserved.

PHP Markdown & Extra  
Copyright (c) 2004-2009 Michel Fortin  
<http://michelf.com/>  
All rights reserved.

Based on Markdown  
Copyright (c) 2003-2006 John Gruber   
<http://daringfireball.net/>   
All rights reserved.