[//]: # ( -*- mode: markdown; mode: auto-fill; mode: visual-line; -*- )

# `instatty` - read your Instagram feed in your terminal

## Why

I like [posting cat and coffee pictures to Instagram][insta-gnomon027]
and interacting with folks in on the joke.  However, I can't stand
notification interruptions, so I poll for comments instead; and I
spend so much time in a terminal that polling via the CLI felt like a
sufficiently absurd idea.

Hence this script!

## How

Run `instatty` to poll the list of configured accounts for each of
their most recent posts.  (20, I think?)  This list is then sorted
chronologically (**!!!**) and spammed to your terminal.

Because this program does not auth against the API, you don't need to
configure your own user account; but by that same token you won't be
able to poll any private accounts.

Run `instatty-comments [post URL] [...post URLs...]` to pull down
comments and likes from one or more Instagram post URLs.

You'll almost certainly want to pipe the output of both programs
through `less`; you'll also possibly want to pipe it through `fmt -s`
first to wrap long lines.

## What

At first I tried using [the Instagram API][insta-api], but it is
_very_ obviously hostile to this use case.  So instead I ended up
screen scraping the GraphQL JSON baked into the HTML of the web
interface.  And of course it ended up being a shell script because it
started life as an interactive one-liner which I poached out of my
`~/.bash_history` and saved into a file.

Yes, it's an abomination.

`¯\_(ツ)_/¯`


[//]: # ( ------------------------------------------------------ )


[insta-gnomon027]: https://instagram.com/gnomon027

[insta-api]: https://www.instagram.com/developer/
