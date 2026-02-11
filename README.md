# Reflections

I started out with a log in error and attempted to debug this initially by setting "debug" to "true" in auth.js to get more insight. I was getting an error regarding not being able to fing "u.id", whihc it later turned out affected everyone who had had to name their "users" table something else due to awaiting marking for another project that laready used a "users" table. I went through all the code replacing the template table names, checking and rechecking.

I tried changing the code in middleware.js as it did not match current docs, but found that what was in the template had been correct for the version of auth.js in use.
I also tried editing parts of auth.js with no luck.
I made changes to the GitHub callback url to address another issue and this resolved it, allowing me to deploy successfully to Vercel after fixing some more errors. However, it was still impossible to log in.

I tried using the Oauth app option in GitHub instead fo the GitHub app optin, but this did not worlk, so I changed back. Fnally I tried changing references to "user" in auth.js to the table name I had in place instead of "user", but this broke to app. When i reverted my changes the app was still broken, wiht ESlint showing "Cannot find type definition file for 'cookie'", which had not appeared before.

Bertie can attest to the app having deployed successfully in Vercel, but at this point it is effectively broken (you can view the home page, that's all). As I had a table called "users" from my currently unmarked week9 assignment I had no realistic option but to name my users table something else, which the class was told explicitly would be fine (undoubtedly an honest mistake). I spent the entire day trying to fix an issue that, as I understand it, was not meant to be part of this challenge, and therefore missed out on the chance to complete stretch goals, so I would very much appreciate if this was taken into consideration.

## Upvote

Upvote is a Reddit-esque web application that allows users to create posts, upvote and downvote posts, and comment on posts in a multi-threaded, nested list.

The project is built using Next.js with the /app router and [Tailwind CSS](https://tailwindcss.com/), and uses [Auth.js (formerly Next Auth)](https://authjs.dev/) for user authentication. The data is stored in a Postgres database, which is created and accessed with raw SQL queries using the `pg` package.

The project is a work in progress and is not yet complete.

## Features

- [x] View a list of posts
- [x] View a single post
- [x] Create a post
- [x] Upvote and downvote posts
- [x] Pagination of posts
- [x] Comment on posts
- [x] Nested comments (recursive lists)
- [x] User authentication

## Setup instructions

1. Fork the repository (check "copy the main branch only") and clone your fork to your local machine
2. Run `npm install`
3. Create a `.env.local` file in the root directory and add the following environment variables:
   - `DATABASE_URL` - the URL of your Postgres database (eg. the Supabase connection string)
   - `AUTH_SECRET` - the Next Auth secret string (this can be anything at all like a password, but keep it secret!)
   - `AUTH_GITHUB_ID` - the GitHub OAuth client ID (create yours in [Github developer settings](https://github.com/settings/developers))
   - `AUTH_GITHUB_SECRET` - the GitHub OAuth client secret (create this in [Github developer settings](https://github.com/settings/developers))
4. Create the database schema by running the SQL commands in `schema.sql` in your database (eg. by running the commands in Supabase Query Editor)
5. Run `npm run dev` to start the development server
6. Open [http://localhost:3000](http://localhost:3000) with your browser to see the site

## Potential future features

- [ ] User profiles
- [ ] Sorting posts by recent (date posted), top (most upvotes), and most controversial (most upvotes _and_ downvotes)
- [ ] User karma scores
- [ ] User badges / trophies (awards for achievements like number of posts, years on the site, etc.)
- [ ] User settings (eg. number of posts per page, theme, etc.)
- [ ] Moderation tools / reporting or flagging objectionable comments for removable by admins
- [ ] Searching posts (possibly using simple SQL LIKE '%some search%', or [Postgres text search](https://www.crunchydata.com/blog/postgres-full-text-search-a-search-engine-in-a-database))
- [ ] Subreddits (separate communities, that isn't just one big list of posts, that can be created by users)
- [ ] User notifications
- [ ] User private messaging
- [ ] User blocking
- [ ] User following
- [ ] User feed (posts from users you follow)
- [ ] User flair
