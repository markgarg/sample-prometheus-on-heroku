# Sample repo to host Prometheus on Heroku

Uses [Heroku's unofficial buildpack](https://elements.heroku.com/buildpacks/heroku/heroku-buildpack-prometheus).

More configuration to get it to actually deploy to Heroku.

## Installation
1. Login to Heroku via CLI
2. Run 
    ```bash
    heroku create --buildpack https://github.com/heroku/heroku-buildpack-prometheus.git
    ```
3. It will create a Heroku app, sets the buildpack and gives us a git URL for the repo like this: 
    ```bash
    Creating app... done, ⬢ shielded-beach-38076
    Setting buildpack to https://github.com/heroku/heroku-buildpack-prometheus.git... done
    https://shielded-beach-38076.herokuapp.com/ | https://git.heroku.com/shielded-beach-38076.git
    ```

4. Copy the Heroku git repo URL. In our example, that's `https://git.heroku.com/shielded-beach-38076.git`
5. Clone the current repo to your local machine `git clone https://github.com/markgarg/sample-prometheus-on-heroku.git`
6. Add the Heroku git repo URL as a remote: 
    ```bash
    git remote add heroku https://git.heroku.com/shielded-beach-38076.git
    ```

7. You will now have two remotes: one for origin (the git repo where you develop) and one for Heroku (that it uses to deploy your app)
8. Push the current repo to Heroku remote:
    ```bash
    git push heroku master
    ```

9. That's it, you've now got a running Prometheus that is deployed to Heroku! Open the app from UI or from CLI using `heroku open`.