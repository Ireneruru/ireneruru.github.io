# deploy on clic.cs.columbia.edu
- Modify the website 
```bash
mv /Users/yiru/Project/homepage-repo/Home.html /Users/yiru/Project/homepage-repo/index.html
```
- change the Home.html in the file to be index.html.
  
- sync on github
```bash
git add -A; git commit -m 'update website';  git push
```
- sync on the server.
```bash
ssh chen1ru@clic.cs.columbia.edu
```
```bash
cd homepage; git pull; cd ..
rm -rf  secure_html/*
cp -r homepage/* secure_html/
chmod --recursive 777 secure_html/
chmod --recursive 777  html/
```
