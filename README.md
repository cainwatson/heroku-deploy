# Heroku Deploy

A simple action to build, push, and deploy containers to Heroku.

## How to use it

```yml
name: '' # set whatever name you want for your github job
on: {} # set the events you would like to trigger this job
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2

      - name: Build, Push and Deploy to Heroku
        id: heroku
        uses: cainwatson/heroku-deploy@v3.0.0 # use the latest version of the action
        with:
          email: ${{ secrets.HEROKU_EMAIL }} # your heroku email
          api_key: ${{ secrets.HEROKU_API_KEY }} # your heroku api key
          app_name: ${{ secrets.HEROKU_APP_NAME }} # your application name
          dockerfile_path: '' # The path to the folder where the Dockerfile is located
          push_options: '' # Heroku container:push options
```

| Variables       | Description                 | Required      |
|:---------------:|:---------------------------:|:-------------:|
| email           | Heroku Email Account        | ✅            |
| api_key         | Heroku API Key              | ✅            |
| app_name        | Heroku App Name             | ✅            |
| dockerfile_path | Path to your Dockerfile     | ✅            |
| push_options    | Heroku Push Options         | ❌            |
