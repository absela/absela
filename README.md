# Hi 👋 My name is Anass Bsela
[![absela's 42 stats](https://badge.mediaplus.ma/greenbinary/absela)](https://github.com/oakoudad/badge42)



name: Latest blog post workflow
on:
  schedule:
    - cron: '0 0 * * 1'
  workflow_dispatch:

jobs:
  update-readme-with-blog:
    name: Update repo's README with latest blog posts
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      - name: Pull in recent blog posts
        uses: gautamkrishnar/blog-post-workflow@master
        with:
          max_post_count: "4"
          feed_list: "https://martinheinz.dev/rss/"
