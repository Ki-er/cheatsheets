Building your site in production mode

`JEKYLL_ENV=production bundle exec jekyll b`

Reset Docs

```bash
git pull; 
sudo docker stop docs; 
sudo docker rm docs; 
JEKYLL_ENV=production bundle exec jekyll b;
sudo docker build -t docs .; 
sudo docker run -d --name=docs -p 2001:80  docs:latest
```

Reset Blog

```bash
git pull; 
sudo docker stop blog; 
sudo docker rm blog; 
JEKYLL_ENV=production bundle exec jekyll b;
sudo docker build -t blog .; 
sudo docker run -d --name=blog -p 2001:80  blog:latest
```