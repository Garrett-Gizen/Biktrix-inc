![Shopify](https://cdn.shopify.com/s/files/1/1616/8731/articles/biktrix-logo_800x.jpg?v=1592000121)
# Shopify V2
This is the "Warehouse" them and a place for our ne Shopify template.
<br><br>
## What Files Should I Edit?
Below are the files you can either edit or fix for small changes, such as sections.
- Sections
- Snippets
- Templates
- Assets

Anything else can jeopardizing the majority of the website and can affect all pages. If you still need any questions, please let me know @Garrett and I will inform you how to tackle your request.
<br><br>
## How To Setup Locally [WINDOWS ONLY]

If you wanting to work on any template in the future locally through Shopify, this how you do it.

1. Install Visual Studio Code for your editing software. I know it sounds crazy but with the extensions that are listed in the program, it's very simple.
<br><br>
2. Download the following applications for VSC;
  - Shopify Liquid Template Snippet
  - Liquid Language Support
  - Shopify Liquid Preview
  - Highlight Matching Tag
<br><br>

3. All of these applications are NEEDED in order to not only code in liquid but to make sure the taglines exist in your code for easier access.
<br><br>

4. Export the theme you would like to edit, that is either a virgin or editted copy and place it in a directory of your choosing. Than load that directory into VSC.
<br><br>

5. [Install Chocolatey](https://chocolatey.org/install). 
We need Chocolatey to install the Themekit that Shopify provides and a command line
<br><br>

6. In VSC, pull up the terminal and type the following to install the Themekit;

`choco install themekit`
<br><br>

7. Create a Private Shopify Application on the Shopify webpage you want to work on. These are the following steps;
  - Admin > Apps > Manage Private Apps</li>
  - Enable Private App Development is checked</li>
  - Create the new private app and select in the "Themes" category "Reading and Write" permissions.</li>
<br><br>
 
8. Back into VSC, create the following file in the main directory of your local theme;
"config.yml"
<br><br>

10. Now in this file, you are wanting to paste the following code inside of it;

```
development:
  password: 
  theme_id:
  store:
  ```
  <br>

11. Back in the terminal in VSC, run the following code;
  
`theme get --list -p=[your-api-password] -s="[your-store.myshopify.com]"`

***Replace the variables with the correct information. You can find the password in your new Private Application.***
<br><br>

12. After running the command, a list of theme's will popup. It should look something like this;

```
  [119224893593] Biktrix-inc theme (Feb-18-2021)
  [120195055769][live] Warehouse
  [120203215001] Theme export  www-biktrix-com-virgin-warehouse ...
 ```
  
  The idea is to copy the theme variable we want to work on, in this case `120203215001` and place it as the `theme_id` in our configiration file.
  <br><br>
  
13. After that, fill in the rest of the information by adding your API password as `password:` and `store:` as the Shopify store link.
<br><br>

14. Lastly, type the following command in the terminal and voilà, you are done.:+1: 
  
  Everytime you save now, it automatically updates the changes to the Shopify theme online.
  
 `theme watch --allow-live`
  
***Just a reminder that this doesn't count for assets or edits for JSON though, so if you are using any assets locally, you will need to transfer them directly into the theme's folder in Shopify account.***
<br><hr>
@Garrett-Gizen If you have any further questions, please let me know or [click here](https://joepichardo.com/blogs/shopify-liquid-for-beginners/local-shopify-theme-development-with-theme-kit) for a more in-depth walkthrough.
