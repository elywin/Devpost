---
layout: post
title: Install Jekyll (Ubuntu)
---
Jekyll is a static site generator for personal, project, or organization sites that transforms plain text into static websites and blogs.

**Installation**

Install Ruby and other prerequisites: 

    sudo apt-get install ruby-full build-essential zlib1g-dev

> Avoid installing RubyGems packages (called gems) as the root user. Instead, set up a gem installation directory for your user account. 

Add environment variables to your **~/.bashrc** file to configure the gem installation path:

    echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
    echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
    echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
    source ~/.bashrc

Finally, install Jekyll and Bundler:

    gem install jekyll bundler

In the terminal run the following command to create a blog:

    jekyll new blog

Run the project:
    
    bundle exec jekyll serve

And go to **[http://localhost:4000](http://localhost:4000)** in your browser to see your blog.