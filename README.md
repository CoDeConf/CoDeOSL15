#Continuous Delivery & DevOps conference Oslo 2015

__GiJeLi Pages for www.code-conf.com/osl15__

The site is designed to be a sub site to www.code-conf.com hosted from a subdirectory named `osl15`.

The site is hosted by Github pages as a project (sub) site, therfore the live branch is `gh-pages` and not `master`. This is by convention, study the difference between [project sites and user/organisation sites](https://help.github.com/articles/user-organization-and-project-pages/) if your curious about the details.

To serve a jekyll site you fire it up with a `baseurl` setting as a parameter when you start the server:

    jekyll serve --baseurl /osl15 --watch

Use this approach when you are testing locally. Don't fall for the trick and set this setting permanently in your `_config.yml` since this is also read by Github pages and sice it's already served as a project (sub) site it will und up as www.code-conf.com/osl15/osl15.

To mimic the `baseurl` without actually setting it in the `_config.yml` we have introduced another variable there called `root`. So our `_config.yml` looks contains:

    root: /osl15

__Remember__ to use this variable as a prefix to all your file references. An example: If you have an image located in `/images/my.pgn` and you want to include it use:

   ![My beautiful pic]({{site.root}}/images/my.png)
   
Or if you want to link to a internal site at `/speakers/lars+kruse.html` you should use the same approach:

    [Lars Kruse]({{site.root}}/speakers/lars+kruse.html)
    
To test that you have used this approach consistently simply serve your site form the site root when you fire it up, as demonstrated earlier. If anything is broken you will see it.

