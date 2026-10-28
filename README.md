# Cinetag API

The mock data behind [Cinetag](https://github.com/victorhubarb/cinetag), my React movie-catalog app. It is a single `db.json` file with a `videos` list, and it is served as a REST API by [My JSON Server](https://my-json-server.typicode.com), which turns a public GitHub repo with a `db.json` file into a live endpoint.

## Endpoint

```
https://my-json-server.typicode.com/victorhubarb/cinetag-api/videos
```

| Request | Returns |
|---|---|
| `GET /videos` | All videos |
| `GET /videos/1` | One video by id |
| `GET /videos?id=1` | The same video, as a one-item list (the form the Player page uses) |

Each video has this shape:

```json
{
  "id": 1,
  "titulo": "O labirinto do Logcat",
  "capa": "https://.../img2.png",
  "link": "https://www.youtube.com/embed/ypvGqZGJBls"
}
```

`titulo` is the title, `capa` is the cover image and `link` is the YouTube embed address that the player loads.

## Run it locally

To work against a local copy, use [json-server](https://github.com/typicode/json-server):

```bash
git clone https://github.com/victorhubarb/cinetag-api.git
cd cinetag-api
npx json-server --watch db.json --port 3001
```

Then open `http://localhost:3001/videos`.

## Notes

- The endpoint is read-only. My JSON Server accepts write requests but does not save them.
- The cover images are hosted on a third-party server, so they depend on that host staying online.

---

Victor Hugo Barbosa · [GitHub](https://github.com/victorhubarb) · [LinkedIn](https://www.linkedin.com/in/victorhbarbosa/)
