# Shopify V2
This is the "Warehouse" them and a place for our ne Shopify template.
<br><br><br>
## How To Setup Locally [WINDOWS ONLY]

If you wanting to work on any template in the future locally through Shopify, this how you do it.

<ol>
<li>Install Visual Studio Code for your editing software. I know it sounds crazy but with the extensions that are listed in the program, it's very simple.</li>
<br>

<li>Download the following applications for VSC;
<ul>
<li>Shopify Liquid Template Snippet</li>
<li>Liquid Language Support</li>
<li>Shopify Liquid Preview</li>
<li>Highlight Matching Tag</li>
</ul>

<i>All of these applications are NEEDED in order to not only code in liquid but to make sure the taglines exist in your code for easier access.</i></li>
<br>

<li>Export the theme you would like to edit, that is either a virgin or editted copy and place it in a directory of your choosing. Than load that directory into VSC.</li>
<br>

<li><a href="https://chocolatey.org/install">Install Chocolatey</a>
  
<i>We need Chocolatey to install the Themekit that Shopify provides and a command line</i></li>
<br>

<li>In VSC, pull up the terminal and type the following to install the Themekit;
  
`choco install themekit`</li>
<br>

<li>Create a Private Shopify Application on the Shopify webpage you want to work on. These are the following steps;
<ul>
<li>Admin > Apps > Manage Private Apps</li>
<li>Enable Private App Development is checked</li>
<li>Create the new private app and select in the "Themes" category "Reading and Write" permissions.</li>
</ul>
</li>
<br>

<li>Back into VSC, create the following file in the main directory of your local theme;
"config.yml"</li>
<br>

<li>Now in this file, you are wanting to paste the following code inside of it;

```
development:
  password: 
  theme_id:
  store:
  ```
  </li><br>

<li>Back in the terminal in VSC, run the following code;
  
`theme get --list -p=[your-api-password] -s="[your-store.myshopify.com]"`

<i>Replace the variables with the correct information. You can find the password in your new Private Application.</i>
<br><br>

<li>After running the command, a list of theme's will popup. It should look something like this;</li>

```
  [119224893593] Biktrix-inc theme (Feb-18-2021)
  [120195055769][live] Warehouse
  [120203215001] Theme export  www-biktrix-com-virgin-warehouse ...
 ```
  
  The idea is to copy the theme variable we want to work on, in this case `120203215001` and place it as the `theme_id` in our configiration file.
  <br>  <br>
  
  <li>
  
  After that, fill in the rest of the information by adding your API password as `password:` and `store:` as the Shopify store link.
</li>
  <br>
  
  <li>Lastly, type the following command in the terminal and voilà, you are done.:+1: 
  
  Everytime you save now, it automatically updates the changes to the Shopify theme online.
  
 `theme watch --allow-live`
  
  <i>Just a reminder that this doesn't count for assets though, so if you are using any assets locally, you will need to transfer them directly into the theme's folder in Shopify account.</i>
</ol>

<br><hr>

@Garrett-Gizen If you have any further questions, please let me know or <a href="https://joepichardo.com/blogs/shopify-liquid-for-beginners/local-shopify-theme-development-with-theme-kit">click here</a> for a more in-depth walkthrough
