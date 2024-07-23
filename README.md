# Homepage

This repo builds the https://oglimmer.github.io/homepage-k8s/ web page.

It's technicaly based on Boostrap 5 and Nuxt 3 using a static build.

## Development Server

```bash
npm i
npm run dev
```

Access at `http://localhost:3000`:

## Build for prod

```bash
npm run static
```

### Test prod

```bash
cd .output/public/
docker run -v $PWD:/usr/share/nginx/html -p 8080:80 nginx
```

# Create picture

* find a picture
* resize to 382x287
* for FILE in *.jpeg; do ffmpeg -i "$FILE" -vf "scale='min(414,iw)':'-1'" -q:v 5 "${FILE%.jpg}_resized.jpg"; done

