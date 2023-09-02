# GOOGLE take out 

https://takeout.google.com/settings/takeout

- select google drive
- select homepage only and export

# modify the files 
- replace files in the homepage folder
- add map image and delete `noindex`

```bash
sed -i '' 's/EDITTHISPLACE/<a href="https:\/\/clustrmaps.com\/site\/1bwc8"  title="Visit tracker"><img src="https:\/\/www.clustrmaps.com\/map_v2.png?d=KsmYlrZjZoOFkZQbaRUASTztAvL9_2OmjD38hI8orEI&cl=ffffff"\/><\/a>/g' index.html

sed -i '' 's/<meta name="robots" content="noindex">//g' index.html
```

# deploy on clic.cs.columbia.edu

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
