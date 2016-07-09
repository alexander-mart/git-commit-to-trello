# Git commit to Trello card comment
Connect GitLab to Trello. Now anytime you mention a card number in a commit message like this : “#44 Some message”. Your comment should appear on your card.

Original: http://joelherber.com/connect-gitlab-to-trello/

One of the things that I have always found useful when working with task tracking software, is the ability to see a list of all git commits associated with a given issue. Currently commit tracking is only supported for Business class users, and so far only GitHub is supported.
Here I will explain how you can get Git to automatically link your trello cards with your git commits.

1. Firstly, install [node](https://nodejs.org/en/download/) and node trello,

```
$ sudo npm install -g node-trello
```

2. Next get an app key from trello using the folowing link: https://trello.com/1/appKey/generate

3. Allow Git-hook to use your account –
```
https://trello.com/1/connect?key=KEY_YOU_OBTAINED_FROM_STEP_TWO&name=git-hook&expiration=never&response_type=token&scope=read,write
```

4. Unzip the attached ZIP file into your .git directory for your project (this file may be hidden for you). So the path should be your_project_path/.git/hooks

hooks (2 files)

5. You may need to make the script executeable

```
# chmod +x your_project_path/.git/hooks/*
```

6. Open the post-to-trello file in the hooks folder and fill in your key, token, repo link, and board id. To get you board ID, go to your trello board in a browser and append “.json” on the end of the URL e.g. https://trello.com/e/aaaaaa/my-board.json

Now anytime you mention a card number in a commit message like this:
```
“#44 Some message”
```
Your comment should appear on your card. Credit to [mashihua](https://gist.github.com/mashihua/2952814) for the initial Git -> trello code.
