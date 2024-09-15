name: Publish to Social Media

on:
  push:
    branches:
      - main

jobs:
  publish:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2
      - name: Publish to LinkedIn
        uses: linkedin/publish@v1
        with:
          url: ${{ secrets.LINKEDIN_URL }}
          token: ${{ secrets.LINKEDIN_TOKEN }}
      - name: Publish to Twitter
        uses: twitter/publish@v1
        with:
          url: ${{ secrets.TWITTER_URL }}
          token: ${{ secrets.TWITTER_TOKEN }}
      - name: Publish to Facebook
        uses: facebook/publish@v1
        with:
          url: ${{ secrets.FACEBOOK_URL }}
          token: ${{ secrets.FACEBOOK_TOKEN }}
      - name: Publish to Instagram
        uses: instagram/publish@v1
        with:
          url: ${{ secrets.INSTAGRAM_URL }}
          token: ${{ secrets.INSTAGRAM_TOKEN }}
      - name: Publish to YouTube
        uses: youtube/publish@v1
        with:
          url: ${{ secrets.YOUTUBE_URL }}
          token: ${{ secrets.YOUTUBE_TOKEN }}