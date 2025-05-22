# Jekyll Development Container

This repos aims to provide a container to test your jekyll website using a container. I decided to develop this in order to facilitate the development of my github pages site. Advantages provided by this project:
- Get rid of some tools/ruby dependencies issues on your host OS
- Auto reload of your website posts
- Isolate the execution of your website from your git repos
- Test your website in an isolated environment in a **rootless** container

## Usage
> The full script is available at the end of the section

- Clone the repo: `git clone https://github.com/acmo0/jekyll-development-container.git`
- Copy the files of the repo to your jekyll project : `cp jekyll-development-container /path/to/your/project`
- Go to your jekyll project : `cd /path/to/your/project`
- (Edit the docker compose to match the ruby version)
- (Edit the docker compose to match your posts directory)
- Run the website : `docker compose up --build`
- Access to `http://localhost:4000/` (refresh the website to get your modifications on your posts)

```bash
git clone https://github.com/acmo0/jekyll-development-container.git
cp jekyll-development-container /path/to/your/project
cd /path/to/your/project

// potential edition of the docker compose file

docker compose up --build
```

## Troubleshooting

- If no posts are loaded, please check that your posts are under the `_posts` folder in the current directory
- If there is dependencies issues, check your *Gemfile* and the ruby version you use to run the container
- If no website is available at `http://localhost:4000/`, check the docker compose logs to ensure that the website is running on *0.0.0.0:4000*

## Limitation

This repos has been tested only on the theme [Beautiful Jekyll](https://beautifuljekyll.com/), you may need to edit some minor parts of the Dockerfile/docker-compose.yml