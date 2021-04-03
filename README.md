
[![Patrick's GitHub stats](https://github-readme-stats.vercel.app/api?username=patrickellis&theme=vue-dark&show_icons=true)](https://github.com/patrickellis/github-readme-stats)

![Metrics](https://metrics.lecoq.io/patrickellis?template=classic&isocalendar=1&languages=1&activity=1&isocalendar.duration=half-year&languages.colors=github&languages.threshold=0%25&activity.limit=5&activity.days=14&activity.filter=all&activity.visibility=all&activity.timestamps=false&config.timezone=Europe%2FLondon)
# Visit https://github.com/lowlighter/metrics/blob/master/action.yml for full reference
name: Metrics
on:
  # Schedule updates (each hour)
  schedule: [{cron: "0 * * * *"}]
  # Lines below let you run workflow manually and on each commit
  workflow_dispatch:
  push: {branches: ["master", "main"]}
jobs:
  github-metrics:
    runs-on: ubuntu-latest
    steps:
      - uses: lowlighter/metrics@latest
        with:
          # Your GitHub token
          token: ${{ secrets.METRICS_TOKEN }}

          # Options
          user: patrickellis
          template: classic
          base: header, activity, community, repositories, metadata
          config_timezone: Europe/London
          plugin_activity: yes
          plugin_activity_days: 14
          plugin_activity_filter: all
          plugin_activity_limit: 5
          plugin_activity_visibility: all
          plugin_isocalendar: yes
          plugin_isocalendar_duration: half-year
          plugin_languages: yes
          plugin_languages_colors: github
          plugin_languages_threshold: 0%
