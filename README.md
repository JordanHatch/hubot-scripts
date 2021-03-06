# hubot-scripts

These are a collection of community scripts for
[Hubot](https://github.com/github/hubot), a chat bot for your company.

## Installing

Once you have Hubot installed, you can drop new scripts from this repository
right into your generated Hubot installation. Just put them in `scripts`,
restart your robot, and you're good to go.

All the scripts in this repository are located in
[`src/scripts`](https://github.com/github/hubot-scripts/tree/master/src/scripts).

## Writing

Want to write your own Hubot script? The best way is to take a look at an
[existing script](https://github.com/github/hubot-scripts/blob/master/src/scripts/tweet.coffee)
and see how things are set up. Hubot scripts are written in CoffeeScript, a
higher-level implementation of JavaScript.

You'll also want to [add tests](https://github.com/github/hubot-scripts/blob/master/test/tests.coffee)
for your script; no one likes untested code. It makes Hubot sad.

Additionally, it's extremely helpful to add [TomDoc](http://tomdoc.org) to the
top of each file. (Check out [an example](https://github.com/github/hubot-scripts/blob/master/src/scripts/speak.coffee#L1-5)).
We'll pull out the commands from those lines and display them in the generic,
robot-wide `hubot help` command.

## Scripts

## spin.coffee

### Spin me

__Format:__

    (@yourbot )spin me <query> - Returns a spun version of the input.

__Input:__

    spin me {Hi there|Greetings|Hi|Hello|Hello There}{!|,}

    I {really|simply|totally} {love|respect|admire} your {blog|article|post|opinion} and {will tell all my friends about it|will be back again tomorrow|also the design of your website}.

    {Thanks|Thank you|Cheers|Bye for now}!

__Output:__

    Greetings!

    I simply admire your blog and also the design of your website.

    Cheers!

### Spun me

__Format:__

    (@yourbot )spun me <query> - Returns a spintax version of the input using articlemanager.us spinner API.

__Input:__

    spun me Below it sat a wooden case of trophies and other awards. Several more were stacked into other corners, joining marble statues, weapon stands and a flat screen television. They all shined in the fire’s light. At least he knew his mother and sister, who were overseas visiting the Queen of England, would be proud. He settled on calling them later, envisioning how they would congratulate him on bringing even more fame and wealth to the family. The invention cooking up in his basement right now was going to make him bigger than the internet.

__Output:__

    Below it sat {a|the} wooden case of trophies {and other|along with other|as well as other} awards. Several more {were|had been} stacked into other {corners|edges}, joining marble statues, weapon stands {and a|along with a} flat screen television. {They all|All of them} shined in the fire’s {light|lighting|mild}. At least he {knew|realized} his mother and {sister}, who were overseas {visiting|going to} the Queen of {England|Britain}, would be proud. {He|This individual|He or she} settled on calling {them|all of them} later, envisioning how {they would|they might} congratulate him on bringing {even more|much more} fame and wealth {to the|towards the} family. The invention cooking {up|upward} in his basement right now {was going to|would definitely} make him bigger {than the|compared to} internet.

### Spin the last spun

__Format:__

    (@yourbot )spun the last spun - Returns a spun version of the input generated by the last spun me call.

__Output:__

After previous spun me command output could be for example:

    Below it sat a wooden case of trophies and other awards. Several more had been stacked into other corners, joining marble statues, weapon stands along with a flat screen television. They all shined in the fire’s mild. At least he realized his mother and sister, who were overseas visiting the Queen of Britain, would be proud. He or she settled on calling all of them later, envisioning how they would congratulate him on bringing much more fame and wealth towards the family. The invention cooking upward in his basement right now would definitely make him bigger compared to internet.

Or if storage is empty: `Nothing so spin. Please use spun first.`

### Spun and spin me

__Format:__

    (@yourbot )spun and spin me <query> - Returns a spun version of the input using spun me command first.

__Input:__

    spun and spin me And please do not expect anything like Goethe or Schiller from my work, no expect everything, everything, but please no niveau! Because I am orientating myself way more direction Charles Bukowski and Hank was according to common knowledge born in a German town on the left river bank of the Rhine. I myself do live coincidentally in a small town along the Rhine, where triumphantly wins of the Handball team and disturbances in the local chemical plants are holding each other in suspense. Happily or sadly, both of them happen rather seldom.

__Output:__

For example:

    And please do not expect anything like Goethe or Schiller from my work, no expect everything, everything, but please no niveau! Because I am orientating myself way more direction Charles Bukowski and Hank was according to common knowledge born in a German town on the left river bank of the Rhine. I myself do live coincidentally in a small town along the Rhine, where triumphantly wins of the Handball team and disturbances in the local chemical plants are holding each other in suspense. Happily or sadly, both of them happen rather seldom.

## oauth.coffee

__Get authorization URL__

    get <api> authorization url - get a link to authorization place

__Set verifier__

    set <api> verifier <verification_code> - set verification code and access token after first step

__Set access token__

    set <api> access token <code> - set access token manually, for OAuth 2.0 (Facebook) only

__Refresh token__

    refresh <api> token - refresh access token if it expires, for OAuth 2.0 only

__Get request token__

    get <api> request token - retrieves request token public value

__Get access token__

    get <api> access token - retrieves access token public value

__Get verifier__

    get <api> verifier - retrieves verification code

__Remove authorization__

    remove <api> authorization - clears tokens from memory if user is same who verified the last authorization