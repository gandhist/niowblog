---
title: "Let's we talk about Express"
tags: ["nodejs", "express"]
published: true
date: "2018-12-29"
---

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Mauris sapien nisi, consequat nec dolor ut, lobortis vestibulum nunc. Nulla facilisi. Suspendisse leo urna, pulvinar ut pretium sit amet, consequat eget sapien. Nam ultricies in nulla finibus feugiat. Maecenas lacinia, lorem quis egestas convallis, tortor nunc consectetur est, vel finibus odio dui et nunc. Proin quis ante ut felis lacinia dignissim quis ac risus. Vestibulum a maximus est. Pellentesque malesuada eros ac diam aliquam, non pulvinar magna sodales. Fusce hendrerit malesuada quam, ut accumsan massa efficitur et. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Nullam vitae ornare sem, eget volutpat mauris. Praesent aliquet condimentum dui non bibendum. Nam dapibus rutrum mi sit amet luctus. Proin id vehicula risus. Nullam dictum, elit sit amet molestie eleifend, felis dolor scelerisque risus, sed dictum odio dolor id justo. Integer consectetur dui non tortor scelerisque, non vulputate sem laoreet:

```javascript
const express = require("express")
const app = express()
const bodyParser = require("body-parser")

const cors = require("cors")

const mongoose = require("mongoose")
mongoose.connect(process.env.DB_URI || "mongodb://localhost/dbname")

app.use(cors())

app.use(bodyParser.urlencoded({ extended: false }))
app.use(bodyParser.json())

app.use(express.static("public"))
app.get("/", (req, res) => {
  res.sendFile(__dirname + "/views/index.html")
})

// Not found middleware
app.use((req, res, next) => {
  return next({ status: 404, message: "not found" })
})

const listener = app.listen(process.env.PORT || 3000, () => {
  console.log("Your app is listening on port " + listener.address().port)
})
```

<br>

Donec at quam sapien. Nulla quis egestas metus, ut tempus elit. Vivamus placerat diam ac ultrices finibus. Aenean vitae molestie eros. Curabitur pulvinar ornare est volutpat consequat. Vivamus ullamcorper pharetra leo ac volutpat. Curabitur efficitur egestas posuere.

<br>

consectetur elementum.
