name: nightfalldlp
on:
  push:
    branches:
      - master
  pull_request:
jobs:
  run-nightfalldlp:
    name: nightfalldlp
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repo Action
        uses: actions/checkout@v2

      - name: nightfallDLP action step
        uses: nightfallai/nightfall_dlp_action@v1.0.0
        env:
          NIGHTFALL_API_KEY: ${{ secrets.NIGHTFALL_API_KEY }}
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          EVENT_BEFORE: ${{ github.event.before }}
