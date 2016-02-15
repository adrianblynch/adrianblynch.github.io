---
layout: post
title: Multi-line bash commands for easier to read Jenkins projects
summary: 
tags: ['bash', 'jenkins']
---

I have a Jenkins project that runs a loooooong command:

```
node -v
npm -v
npm install
node index.js --sql "SELECT column FROM table WHERE column = 123; SELECT anotherColumn FROM anotherTable WHERE anotherColumn = 456;" --host "a.host.name.for.my.database" --user "user" --password $SUPER_SECRET_PASSWORD --database "database"
```

To make it more readable you can break it onto new lines with a backslash:

```
node -v
npm -v
npm install
node index.js \
    --sql "SELECT column FROM table WHERE column = 123; SELECT anotherColumn FROM anotherTable WHERE anotherColumn = 456;" \
    --host "a.host.name.for.my.database" \
    --user "user" \
    --password $SUPER_SECRET_PASSWORD \
    --database "database"
```
 
Much nicer!

Let's not comment on the long SQL statement, that's there to make a point. Using [yargs](https://www.npmjs.com/package/yargs) I could use multiple `--sql` flags like so:

```
node index.js \
    --sql "SELECT column FROM table WHERE column = 123" \
    --sql "SELECT anotherColumn FROM anotherTable WHERE anotherColumn = 456;"
```

And then join them in the script, but now we're getting off topic...
