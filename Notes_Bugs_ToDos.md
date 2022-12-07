# Partisan Website

## Notes

**URL:** https://erc-partisan.github.io



## Step-By-Step Guide

1. Requirements: Homebrew, Ruby, and Jekyll, Bundler

   - Install Homebrew

   - https://jekyllrb.com/docs/installation/macos/
   - Do not use 'chruby' since it does not allow to install the newest Ruby version due to a bug
   -  Instead, use rbenv to install ruby: https://www.engineyard.com/blog/how-to-install-ruby-on-a-mac-with-chruby-rbenv-or-rvm/ 
     - scroll down until rbenv instructions
   - install Jekyll
   - install bundler

2. Remove the 'ruby-version' file in the github repo

   - see issue discussion https://github.com/amitmerchant1990/reverie/issues/57

3. Navigate with the terminal to the working directory

   - use the command 'ls' to see where you currently are
   - use the command 'cd' to change the directory (navigate through the folders with 'cd')

4. Create a new 'Gemfile'

   - A gemfile is just a simple text document without a file ending - the document name has to be just 'Gemfile'

   - The Gemfile need to include

     ```Gemfile
     source 'https://rubygems.org'
     gem 'jekyll-sitemap'
     gem 'jekyll-feed'
     gem 'jekyll-seo-tag'
     gem 'jekyll-paginate'
     ```

   - the gems are specified the '_config.yml' file

5. Install the gem dependencies

   ```Terminal
   bundle add jekyll-seo-tag jekyll-paginate jekyll-sitemap jekyll-feed
   ```

6. Install a further needed dependency

   ```Terminal
   gem install github-pages webrick
   ```

7. Test the Website locally

   ```Terminal
   jekyll serve
   ```

   - The terminal has to be in the correct working directory!
   - copy the server address and test the website in a browser

8. Change individual pages

   - open the md files
   - in the header sections meta data can be included
   - then just use markdown



## NEW Protocol

1. Navigate with the terminal to the working directory

   - use the command 'ls' to see where you currently are
   - use the command 'cd' to change the directory (navigate through the folders with 'cd')

2. Run in terminal

   ```
   bundle install
   ```

3. Start the Jekyll local development server

   ```
   bundle exec jekyll serve
   ```

4. To build the theme (not necessary!)

   ```
   bundle exec jekyll build
   ```




#### UPDATING THE WEBSITE

- **Landing Page**

  - Do not make updates in the *_site* folder since it is generated based on the .md files!
  - *_include* → *_layouts* → *home.html*
  - *_data* → *features.json* 

- **CSS files**

  - folder: *_sass* → *components*

- **Contact Box**

  - define contact box in folder *_includes* → *call_html*
  - *css* for social media icons in contact box: 

- **Creating a new subpage**

  1. create a new md file in main folder (can be access directly through permalink page_url/page_name)
  2. add new page to navigation bar in the header
     - *data* → *menus.yml* add there the name, url and weight (order of sites in nav-bar)

- **Remove subpages**

  1. Add to the front matter of the respective subpage .md file in the main folder. This will make the website offline but it is still in the nav-bar.

     ```
     ---
     published: false
     ---
     ```

  2. Remove the subpage title from the navbar: *_data* → *menus.yml* → remove *name* and *weight* (e.g., name: ).

- **Team**

  - *team* folder
  - all information is in the respective team member .md files
  - front matter *promoted: false* then the name does not appear on a card but in a smaller icon below
  - Name as a link to personal website: → *_data* → *_layouts* → *teams.html*
    - personal webpage link in respective team member .md file

- **Change mailadress**

  - *_data* → *contact.yml*

- **GitHub and Twitter**

  - *_data* → *social.json* and *seo.yml*
  - Icons: *images* → *features* → *social*

- **Cards on landing page**

  - *_data* → *features.json*

- **Image on landing page (top)**

  - *_sass* → *components* → *intro-image.scss*

- **Logo in header**