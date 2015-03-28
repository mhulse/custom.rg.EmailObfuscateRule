## About:

E-mail obfuscation RULE/tag for DTI's Content Publisher system. [CSP (Caché Server Page) / COS (Caché Objectscript)]

## Examples:

__Example 01: Container tag__

    
    <rg:email:obfuscate email="bob@bob.com" simple="" mode="" cc="bob@cc.com" bcc="bob@bcc.com" subject="My Subject" body="My body" id="myId" class="myClass" rel="myRel" title="Title goes here" text="" var="foo">#(foo)#</rg:email:obfuscate>
    

__Example 02: Self-closing tag__

    
    <rg:email:obfuscate email="bob@bob.com" simple="" mode="" cc="bob@cc.com" bcc="bob@bcc.com" subject="My Subject" body="My body" id="myId" class="myClass" rel="myRel" title="Title goes here" text="Click here to e-mail Bob" />
    

__Example 03: Return just the obfuscated e-mail address__

    
    <rg:email:obfuscate email="bob@bob.com" simple="true" />
    

__Example 04: Return the obfuscated e-mail address and build the link manually__

    
    <rg:email:obfuscate email="bob@bob.com" simple="true" var="foo"><a #("href=""&amp;#x6D;&amp;#97;&amp;#x69;&amp;#x6C;&amp;#x74;&amp;#x6F;&amp;#x3A;" _ foo _ """")#>#(foo)#</a></rg:email:obfuscate>
    

## Non-DTI customers:

If you don't use DTI software, but you still want to use this code, then all you have to do is remove these lines of code:

    <csr:class super="dt.common.page.Rule" />

    <script language="cache" runat="compiler">
    	do ..RenderDTStartTag()
    </script>

    <script language="cache" runat="compiler">
    	do ..RenderDTEndTag()
    </script>

## Rule parameters:

* __"email"__ Required. E-mail address to obfuscate.
* __"simple"__ Set to 'true' if you want to return just the obfuscated e-mail address. Default is 'false'.
* __"mode"__ Obfuscation mode. 1 = decimal, 2 = hexidecimal, 3 = mixture of modes 1 and 2. Default is mode 3.
* __"cc"__ CC?
* __"bcc"__ BCC?
* __"subject"__ Subject?
* __"body"__ Body?
* __"id"__ Link 'id' attribute?
* __"class"__ Link 'class' attribute?
* __"rel"__ Link 'rel' attribute?
* __"title"__ Link 'title' attribute? Note: This value is not obfuscated.
* __"text"__ Link text. Default is the e-mail address.
* __"var"__ Advanced: Local variable name to use when using this RULE as a container tag (vs. self-closing tag). Variable name MUST BE UNIQUE!

-----

## Changelog:

* __2011/04/04__
	* Deleted old repository on Github.
	* Created new repository on Github that reflects naming/storage changes to DTI system.
	* Added DTI required tags/code to RULE. See "Non-DTI customers" section above.
	* Minor syntax tweaks.
* __2010/03/07__
	* Initial public release.