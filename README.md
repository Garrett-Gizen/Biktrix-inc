# Shopify V2
This is the "Warehouse" template and a place for our new template for our Shopify account.
<br><br><br>
# How To Setup Locally [WINDOWS ONLY]

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

<li>Export the theme you would like to edit that is a virgin or editted copy and place it in a directory of your choosing. Than load that directory into VSC.</li>
<br>

<li>Install Chocolatey. You can find the following how to do this on the following link;<br>
https://chocolatey.org/install
<br>
<i>We need Chocolatey to install the Themekit that Shopify provides and a commandline</i></li>
<br>

<li>In VSC, pull up the terminal and type the following to install the Themekit [without quotations]

  
"choco install themekit"</li>
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
"development:
  password: 
  theme_id:
  store:"</li>
<br>

<li>Back in the terminal in VSC, run the code theme get --list -p=[your-api-password] -s="[your-store.myshopify.com]" and replace the following information. 
<br>

<i>You can find your new API password in the new private applicatio you just created.</i></li>
<br>

<li>After running the command, a list of theme's will popup. It should look something like this;</li>
<br>
  [119224893593] Biktrix-inc theme (Feb-18-2021)
  <br>
  [120195055769][live] Warehouse
  <br>
  [120203215001] Theme export  www-biktrix-com-virgin-warehouse ...<br>
  <br>
  
  The idea is to copy the theme we want to work on, in this case "120203215001" and place it as the "theme_id" in our configiration file.
  <br>  <br>
  
  <li>After that, fill in the rest of the information by adding your API password as "password:" and "store:" as the Shopify store link.</li>
  <br>
  
  <li>Lastly, type the following command in the terminal and vola, you are done. Everytime you save now, it automatically saves to the Shopify theme locally and will be visable
  on the theme's webpage.
  <br> <br>
  theme watch --allow-live
  
  <i>Just a reminder that this doesn't count for assets, so if you are using any assets locally, you will need to transfer them directly into the theme's folder in Shopify</i>
</ol>

<br><hr>

<p>If you have any further questions, please let me know through, garrett@biktrix.com or check out this link for a more indepth walkthrough;<br>
https://joepichardo.com/blogs/shopify-liquid-for-beginners/local-shopify-theme-development-with-theme-kit
