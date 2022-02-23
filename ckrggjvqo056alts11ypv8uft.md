## A Discord bot for task management!

A few days back, I created a Discord Bot solely for task management! A minimal bot with only what's required without any of those confusing functionalities. Just add, assign(if needed) and tick off.

You can get to know more at the [Website](https://task-manager-bot.github.io)

## How to use it in your server?
The bot is published on top.gg and you can find it at https://kvnv.xyz/discord-task-bot. Just click on the invite button and follow the steps.
![Screenshot 2021-07-23 at 8.03.38 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1627050822851/OSlJRMFxw.png)

## Prefix
Like most discord bots, the `Task Manager` bot has a prefix, `t!`.

## Add a task
You can add a task by typing `t!add <task>`. You can also `assign` someone a task by mentioning them in the `t!add` command.

Examples:
1. `t!add This is a new task`
2. `t!add This is a new task @mentioned-user`

![Screenshot 2021-07-23 at 8.08.41 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1627051126916/0todhdzFv.png)

## List all tasks
You can list all of the **remaining** tasks by typing `t!list`

![Screenshot 2021-07-23 at 8.09.03 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1627051146769/9LbV1M7vk.png)

## Tick off a task
You can tick off a task from the list by typing `t!done <id of task>`. The `ID` of the task is the number which appears at the end of a task during `t!list`. In the screenshot attached earlier, it is `65`

![Screenshot 2021-07-23 at 8.10.33 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1627051237054/DYNInrfOv.png)

## Show all done tasks
You can list all the tasks done by typing `t!done-list`

![Screenshot 2021-07-23 at 8.11.27 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1627051293020/9s5-sAPHrX.png)

## Remove a task from done and put it back in to be done
You can put a task back in the todo list by typing `t!undo <id of task>`

![Screenshot 2021-07-23 at 8.12.33 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1627051359193/aslV3Jd32.png)

## Help command
Finally, there is also a help command which lists all the commands you can use which you can get by typing `t!help`

![Screenshot 2021-07-23 at 8.13.39 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1627051424547/b_iBlrtLe.png)

That's it. And that's mostly everything you need in a task manager.
> Note that the tasks are server specific and you cannot manipulate tasks across servers

## Code
The code for the bot can be found at the following Github Repo. You're welcome to create any issues or contribute by creating a PR.

%[https://github.com/Task-Manager-Bot/discord-task-bot]