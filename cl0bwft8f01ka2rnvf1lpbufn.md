## How to show code diffs in your Hashnode Blog?

Code Diffs was something I wanted to use for a while in Hashnode but I didn't know that it was already there to be used in markdown. The way you can implement this is like follows:
~~~
```diff
+ const port = process.env.PORT || 3000;
- app.listen(3000, () => {
-   console.log(`🚀 Server started on port 3000`)
- }
+ app.listen(port, () => {
+   console.log(`🚀 Server started on port ${port}`);
+ });
```
~~~
> This example is from on of my [articles](https://livecode247.com/start-a-web-server-with-nodejs-and-express)

So, the way this works is, hashnode uses a plugin called [highlight.js](https://highlightjs.org/) to convert the codeblocks. Highlight.js already has this feature implemented.
Now this looks like this:

![Code Block with diff without Custom CSS](https://cdn.hashnode.com/res/hashnode/image/upload/v1646366426943/nJqnhH8Tm.png)

You can definitely go forward with this, but the colors and design wasn't something I was satisfied with.
So, I decided to tweak my custom css to make it look better.
> You can get access to Hashnode's [Custom CSS](https://hashnode.com/post/style-your-hashnode-blog-with-custom-css-ckfwpesyg00ut0es10jgk5uwl) feature by becoming a [Hashnode Ambassador](https://hashnode.com/ambassador)

I added the following to my custom css:
```css
.hljs-addition {
    color: green !important;
    box-shadow: inset 10.5px 0 green !important;
    padding: 4.4px 0 !important;
    background: rgb(0, 255, 0, 0.1);
}

.hljs-deletion {
    color: red !important;
    box-shadow: inset 10.5px 0 red !important;
    padding: 4.4px 0 !important;
    background: rgb(255, 0, 0, 0.2);
}
```
Now, this definitely can be refactored a little bit, but this is what I got:

![Code block with diff with custom css](https://cdn.hashnode.com/res/hashnode/image/upload/v1646366739833/SXWSU8vS_.png)

Now, I'm pretty satisfied with this! You can go ahead and use this feature and you're welcome to use my custom css and if you want tweak it a little bit and I would love to see your implementation in the comments!

> NOTE: This has one drawback that I couldn't find a way where you could have both the diff highlighting and the syntax highlighting for a certain language together in a code block. That is something we might have to wait for @Hashnode to implement, if they do.
