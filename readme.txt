Readme to integrate Instagram Hashtag module on Shopify site

// NOTE: This is not my code. I simply put this together based on different scripts I found on the internet.
// Initial inspiration is from the BlackMilk site http://blackmilkclothing.com/products/hacky-sack-leggings-limited
// Instagram JQUERY with Slimbox2 implementation is from http://notes.madebyfinn.com/post/21266413592/adding-an-instagram-feed-to-a-website



1) Get your CLIENT ID from Instagram by going to http://instagram.com/developer/clients/manage
It should be a long string of characters, not to be confused with your Instagram username. If you don't have any clients, register a new one. You will have to enter in this information;

Application Name: Type in your website name (not really important)
Description: Type in whatever you need to remember this application name (not really important)
Website: Your website URL (not really important)
OAuth redirect_url: Your website URL again (not really important)

Once you hit register, it will display the client information. Copy the CLIENT ID string and paste it into instagramhash.liquid where it asks for CLIENT ID.

2) While you are in the instagramhash.liquid file, you should also update the following;

hash: 'This is where you put the hash tag search word' (you do not need the actual '#' sign). You can also use the Shopify liquid tag to dynamically put in a hash tag from your product page. In the file I included, I wanted to create a dynamic hash tag for each product page preceded by the letters 'lb'. So if the product name was 'Maxi Dress', my hash tag would be 'lbMaxi Dress'. To get rid of potential long hash tags, I used the Truncate Words function and also forced the hash tag into lowercase.

So in the instagramhash.liquid file you'll see;
hash: 'lb{{ product.title | truncatewords: 1,'' | downcase }}'
I'm taking the product title and just taking the first word and removing the automatic ellipses that Truncate Words puts in and then forcing the word to lowercase.

If you want to use some other dynamic variable, check out this site for a list of variables. http://cheat.markdunkley.com/

show: you can put in any value here.
clientId: this is where you paste in your Instagram clientId.

3) In the instagramhash.liquid file after the javascript, I also included a call to action that prompts users on how the images are pulled in, prompting them to tag their Instagram photos to be included on the site.

The last line <div class="instagram"></div> is where the images will be populated by JQUERY.

4) If you want to adjust the CSS or incorporate it into the main Shopify CSS file, I've also included it in the /asset/ directory along with the lightbox images.

// Drop me a line if you use the code, would love to see if you benefitted from my 2 days of patching this stuff together. jaepaik@me.com