# Reflections

I started out with a log in error and attempted to debug this initially by setting "debug" to "true" in auth.js to get more insight. I was getting an error regarding not being able to fing "u.id", whihc it later turned out affected everyone who had had to name their "users" table something else due to awaiting marking for another project that laready used a "users" table. I went through all the code replacing the template table names, checking and rechecking.

I tried changing the code in middleware.js as it did not match current docs, but found that what was in the template had been correct for the version of auth.js in use.
I also tried editing parts of auth.js with no luck.
I made changes to the GitHub callback url to address another issue and this resolved it, allowing me to deploy successfully to Vercel after fixing some more errors. However, it was still impossible to log in.

I tried using the Oauth app option in GitHub instead fo the GitHub app optin, but this did not worlk, so I changed back. Fnally I tried changing references to "user" in auth.js to the table name I had in place instead of "user", but this broke to app. When i reverted my changes the app was still broken, wiht ESlint showing "Cannot find type definition file for 'cookie'", which had not appeared before. This was at some point around 4.15pm, at whihc point no further support was available and I was unable to find any clear information on how to correct it.

Bertie can attest to the app having deployed successfully in Vercel, but at this point it is effectively broken (you can view the home page, that's all). As I had a table called "users" from my currently unmarked week9 assignment I had no realistic option but to name my users table something else, which the class was told explicitly would be fine (undoubtedly an honest mistake). I spent the entire day trying to fix an issue that, as I understand it, was not meant to be part of this challenge, and therefore missed out on the chance to complete stretch goals, so I would very much appreciate if this was taken into consideration.
