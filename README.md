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

## midjourney

prompts

```
a stylized octopus with large eyes sitting on a data server

a stylized traffic policeman in the middle of a multi lane street managing car traffic

a stylized worker using a shovel in front of a large cloud and computers

a stylized worker using a shovel to move gold int the cloud

Draw a stylized representation of servers, with haproxy as the central hub. Use geometric shapes, lines, and colors to convey the idea of a complex network infrastructure. Envision haproxy as a futuristic building or skyscraper, with incoming requests (in the form of arrows or rays) converging on it from various directions  Depict haproxy as a mechanical, cybernetic creature, with gears, wires, and circuits forming its body.  Create a stylized diagram illustrating the flow of traffic through haproxy. Use arrows, curves, and shapes to visualize the proxy's role in routing requests, managing load balancing, and optimizing performance.  Draw a fractal representation of data streams flowing through haproxy. This could capture the idea of complex, self-similar patterns emerging from the interactions between clients, servers, and the proxy itself.

a stylized conductor directing a orchestra with perspective from behind the conductor and the orchestra in the back

in a desert scene, people investigating boxes with magnifying glasses

a very long conveyor belt moving boxes into clouds

a stylized super large monitoring dashboard in the middle of a living room

a stylized container ship, fully loaded departing from a harbor

a stylized rancher set against a desert scene

a stylized longhorn eating grass on the great plains, mountains in the background
```
