Below is the contents of this project/repo.

Generate a beautiful readme.md file from this.

```public/readme.scroll
title ScrollHub: The fastest way to publish

linkTitle Readme
pageHeader.scroll

container 560px

ScrollHub is a super server for publishing websites, scientific articles, blog posts, books, and more.

It is the fastest way to publish. Don't take my word for it, try for yourself here: https://hub.scroll.pub

# Run your own ScrollHub in 60 seconds
Follow the steps below to run your own ScrollHub server in 60 seconds!

serverSetup.scroll

Optional steps:
- Create a DNS A Record pointing from your domain or subdomain to your new server.

# Helpful Dev Environment Aliases
codeFromFile .bash_aliases.sh

# Wildcard SSL certs
code
 sudo certbot certonly --manual --preferred-challenges dns -d example.com -d "*.example.com"
 dig _acme-challenge.example.com TXT

tor.scroll

# Git Troubleshooting

ScrollHub uses git for versioning files.

If developing locally, occasionally you may run into merge conflicts.

To see the "git status" for a folder visit: https://hub.scroll.pub/status/[folderName]

It is recommended to prevent force pushes on your server with `git config --system receive.denyNonFastForwards true`.

****

ScrollHub is public domain.

footer.scroll

```
```public/releaseNotes.scroll
buildConcepts releaseNotes.csv releaseNotes.json releaseNotes.tsv
buildMeasures releaseNotesMeasures.tsv
title ScrollHub Release Notes
linkTitle Release Notes

pageHeader.scroll
## A list of what has changed in ScrollHub releases.

thinColumn
Download as CSV | TSV | JSON
 link releaseNotes.csv CSV
 link releaseNotes.tsv TSV
 link releaseNotes.json JSON

br

node_modules/scroll-cli/microlangs/changes.parsers

thinColumns 1

📦 0.81.0 1/14/2025
🎉 support for unlimited wildcard SSLs
🎉 refactor of AI prompts
🎉 AI prompt template set via query string
🎉 AI prompt settings - adjust model and tld and save to local storage
🎉 upgraded Scroll
🎉 welcome message improvements

📦 0.80.0 1/13/2025
🎉 show hidden files toggle

📦 0.79.0 1/13/2025
🎉 wildcard cert support
🎉 new /stamp route and command in editor
🏥 various fixes

📦 0.78.0 1/12/2025
🎉 better new site landing experience
🎉 upgrade scroll

📦 0.77.0 1/12/2025
🎉 eliminated certs folder. Now store certs in their respective folders.
⚠️ BREAKING: .hub/keys.txt is now .hub/config.scroll
⚠️ BREAKING: put your root crt/key pair in the .hub folder for root SSL
⚠️ BREAKING: use the migration script below, otherwise all certs will be regenerated.
codeWithHeader migrateCerts.sh
 #!/bin/bash
 cd /root/.hub/certs
 # Iterate over all .crt files (we could use .key too, pattern will match pairs)
 for cert in *.crt; do
     # Skip if no matches found
     [[ -f "$cert" ]] || continue
     # Get the base name without extension (e.g., xiuzhen1.scroll.pub)
     base="${cert%.crt}"
     # Copy both cert and key with leading dot
     cp "$cert" "/root/$base/.$cert"
     cp "$base.key" "/root/$base/.$base.key"
 done

📦 0.76.0 1/12/2025
🎉 add list and kill commands for easier sysadmin
🎉 various improvements, new prompts, and fixes
🏥 various fixes

📦 0.75.0 1/7/2025
🎉 show file history command
🏥 fix rehighlighting bug with remote imports

📦 0.74.0 1/7/2025
🎉 various improvements and fixes
🏥 continue gracefully if errors in loading a scroll doc

📦 0.73.0 1/5/2025
🎉 various improvements and fixes
🏥 mobile layout fixes

📦 0.72.0 1/2/2025
🎉 added writing metrics
🎉 added file keyboard nav
🎉 added keyboard shortcut headers

📦 0.71.0 1/2/2025
🎉 update Scroll
🎉 ls.csv route
🎉 ls.json now includes mtimes and filesizes

📦 0.70.0 1/1/2025
🎉 added dark mode to editor

📦 0.69.0 12/30/2024
🎉 added welcome message
🏥 mode fix

📦 0.68.0 12/30/2024
🎉 added keyboard shortcuts help

📦 0.67.0 12/28/2024
🎉 added focus mode

📦 0.66.0 12/26/2024
🎉 Generalized Agent code and added support for deepseek

📦 0.65.0 12/25/2024
🎉 Stop serving all folders from all custom domains
🎉 Stop serving non-existant domains

📦 0.64.0 12/25/2024
🎉 Better AI prompt

📦 0.63.0 12/24/2024
🎉 Add cron.js support

📦 0.62.0 12/24/2024
🎉 Moved analytics logging to after response finishes and added response time and status code

📦 0.61.0 12/23/2024
🎉 Added create via AI. Requires adding your Claude API key to server.

📦 0.60.0 12/20/2024
🎉 You can now run unlimited ScrollHub processes on one machine-each independently serving their own root folder on their own port.

📦 0.59.0 12/19/2024
🎉 update scroll for better perf
🏥 other fixes

📦 0.58.0 12/17/2024
🎉 update scroll
🏥 format fixes

📦 0.57.0 12/17/2024
🎉 format file command
🎉 many color and style improvements
🎉 upgrade Scroll and ScrollSDK

📦 0.56.0 12/15/2024
🎉 many improvements
🏥 various bug fixes

📦 0.55.0 12/12/2024
🎉 faster startup via caching folder contents to .stats.json
🎉 refresh parsers on save
🏥 various bug fixes

📦 0.54.0 12/06/2024
🎉 hide external dependencies!
🎉 hide .log.txt file
🎉 upgrade Scroll

📦 0.53.1 12/04/2024
🏥 turn off auto-rehighlighting til we figure it out

📦 0.53.0 12/04/2024
🎉 upgrade ScrollSDK and Scroll
🎉 turn Fusion refreshParsers on

📦 0.52.0 12/02/2024
🏥 nested delete file fix

📦 0.51.0 12/02/2024
🏥 git fix

📦 0.50.0 12/02/2024
🎉 cron support: `cron.scroll` files are now run automatically every minute.

📦 0.49.0 11/30/2024
🎉 updated Scroll and ScrollSDK for Fusion

📦 0.48.0 11/29/2024
🎉 Fusion http import support
🎉 updated Scroll and ScrollSDK

📦 0.47.0 11/29/2024
🎉 updated ScrollSDK and Scroll to get Fusion

📦 0.46.0 11/27/2024
🎉 added fileList filter
🏥 various bug fixes

📦 0.45.0 11/23/2024
🎉 added `set` route
🎉 upgraded Scroll
🎉 fixed nested file editing

📦 0.44.0 11/22/2024
🎉 support mjs script running

📦 0.43.0 11/22/2024
🎉 update Scroll to get better forms and notices parsers
🎉 New File API now supports passing params in via query string

📦 0.42.0 11/21/2024
🎉 update Scroll to get new table date transforms

📦 0.41.0 11/20/2024
🎉 added New File API

📦 0.40.0 11/20/2024
🎉 cleanup route names

📦 0.39.0 11/19/2024
🎉 custom parser support in editor

📦 0.38.0 11/18/2024
🎉 file list now shows subdirectories

📦 0.37.0 11/18/2024
🎉 significant write time perf improvements

📦 0.36.0 11/17/2024
🎉 hub can now serve any/all folders on a machine. will serve whatever cwd is.
🎉 moved all hub data storage (logs, certs, etc) under new `.hub` folder in `folders` dir.
🎉 whatever cwd is when you launch hub, that will be the folders dir now.
⚠️ BREAKING: by default ScrollHub server now serves `~` folder, not `~/folders`. You can update your pm2 job to launch ScrollHub from `~/folders` or move folders from `~/folders` to `~`

📦 0.35.0 11/14/2024
🎉 updated Scroll

📦 0.34.0 11/13/2024
🎉 updated Scroll

📦 0.33.0 11/12/2024
🎉 updated Scroll

📦 0.32.0 11/11/2024
🎉 updated to Scroll 148
⚠️ BREAKING: see Scroll release notes for breaks in 148
 https://scroll.pub/releaseNotes.html Scroll release notes

📦 0.31.0 11/11/2024
🏥 more open cors

📦 0.30.0 11/11/2024
🏥 fix script runner by enabling json form parsing

📦 0.29.0 11/11/2024
🎉 updated scroll
🎉 pass request body to script runner

📦 0.28.0 11/10/2024
🏥 temporary cleanup of git issues with templates

📦 0.27.0 11/10/2024
🎉 new /status/:folderName route to help debugging git sync issues

📦 0.26.0 11/09/2024
🏥 git fix

📦 0.25.0 11/09/2024
🎉 add support for php, python, ruby and perl

📦 0.24.0 11/08/2024
🎉 add syntax highlight support for html, css, and js files
🏥 dont use scroll mode for non scroll files
🏥 dont show folders in sidebar for now

📦 0.23.0 11/08/2024
🎉 show version tracking status of files in sidebar
🎉 allow all file types
🎉 add download button
🎉 folder stats should show # of versioned files, not # of files
🎉 a scrollhub folder is one not starting with . that contains a git repo

📦 0.22.0 11/07/2024
🎉 perf for big sites: build saved file immediately, then kick off bigger build jobs
🎉 perf for big sites: only have at most 1 build job in queue per folder

📦 0.21.0 11/07/2024
🎉 added new way to create a folder by dropping a zip onto index page

📦 0.20.0 11/07/2024
🎉 run prettier on save of js, css, and html files if hand edited
🎉 cleanup of write files
🏥 fix bugs with trying to git commit an unchanged file after format

📦 0.19.0 11/06/2024
🎉 shift+click to rename a file
🏥 restore normal browser behavior on command click or right click

📦 0.18.0 11/05/2024
🎉 easier/faster renames and file opens

📦 0.17.0 11/05/2024
🎉 add ScrollHub version number to folders.html page and log to console on start
🏥 error message improvements

📦 0.16.0 11/04/2024
🏥 bug fixes

📦 0.15.0 11/03/2024
🎉 introduced "buffer" param to editor to allow for creating new files from templates
🎉 refactored editor

📦 0.14.0 11/03/2024
🎉 many fixes and improvements

📦 0.13.0 10/25/2024
🎉 the template release

📦 0.12.0 10/24/2024
🎉 one click clones

📦 0.11.0 10/24/2024
🎉 added folder renaming
🎉 various improvements

📦 0.10.0 10/23/2024
🎉 significant bug fixes and improvements

📦 0.8.0 10/18/2024
🎉 refactored code into ScrollHub class and started automated tests
🎉 refactored templates and creation

endColumns

footer.scroll

```
```public/serverSetup.scroll
1. Launch a new Ubuntu Droplet on Digital Ocean (or your cloud provider of choice)
 https://www.digitalocean.com Digital Ocean
2. SSH into your new server and run this oneliner:
code
 apt install -y make zip && git clone https://github.com/tj/n && cd n && make install && n latest && cd && git config --global user.name "ScrollHub" && git config --global user.email "scrollhub@scroll.pub" && git clone https://github.com/breck7/ScrollHub && cd ScrollHub && npm install . && npm install scroll-cli pm2 prettier -g && npm install -g . && git config --global receive.denyCurrentBranch updateInstead && cd && pm2 start ~/ScrollHub/server.js --node-args="--max-old-space-size=4096" --log ~/ScrollHub/pm2.log && pm2 startup && pm2 save

```
```ScrollHub.js
// STDLib
const { exec, execSync, spawn } = require("child_process")
const fs = require("fs")
const v8 = require("v8")
const fsp = require("fs").promises
const os = require("os")
const path = require("path")
const util = require("util")
const crypto = require("crypto")
const execAsync = util.promisify(exec)

// Web server
const express = require("express")
const compression = require("compression")
const https = require("https")
const http = require("http")
const fileUpload = require("express-fileupload")

// Git server
const httpBackend = require("git-http-backend")

// PPS
const { Particle } = require("scrollsdk/products/Particle.js")
const { ScrollFile, ScrollFileSystem } = require("scroll-cli/scroll.js")
const { CloneCli } = require("scroll-cli/clone.js")
const { ScriptRunner } = require("./ScriptRunner.js")
const packageJson = require("./package.json")
const scrollFs = new ScrollFileSystem()

// This
const { TrafficMonitor } = require("./TrafficMonitor.js")
const { CronRunner } = require("./CronRunner.js")
const { FolderIndex } = require("./FolderIndex.js")
const { Agents } = require("./Agents.js")

const exists = async filePath => {
  const fileExists = await fsp
    .access(filePath)
    .then(() => true)
    .catch(() => false)
  return fileExists
}

const ScrollToHtml = async scrollCode => {
  const page = new ScrollFile(scrollCode)
  await page.fuse()
  return page.scrollProgram.asHtml
}

const generateFileName = async (basePath, strategy, content) => {
  let name = "untitled.scroll"
  switch (strategy) {
    case "timestamp":
      name = Date.now() + ".scroll"
      break
    case "autoincrement":
      // Find the highest numbered file and increment
      if (!(await exists(basePath))) {
        name = `1.scroll`
        break
      }
      const files = await fsp.readdir(basePath)
      const scrollFiles = files.filter(file => file.endsWith(".scroll"))
      const numbers = scrollFiles
        .map(file => {
          const match = file.match(/^(\d+)\.scroll$/)
          return match ? parseInt(match[1], 10) : 0
        })
        .filter(num => num > 0)

      const nextNumber = numbers.length > 0 ? Math.max(...numbers) + 1 : 1

      name = `${nextNumber}.scroll`
      break
    case "hash":
      // Generate a hash from the content or a random string
      const hash = crypto
        .createHash("md5")
        .update(content || crypto.randomBytes(16))
        .digest("hex")
        .slice(0, 10)

      name = `${hash}.scroll`
      break
    case "random":
      // Generate a random string
      const randomStr = crypto.randomBytes(8).toString("hex")
      name = `${randomStr}.scroll`
      break
    case "datetime":
      // Use formatted date and time
      const now = new Date()
      const formattedDateTime = now.toISOString().replace(/[:\.]/g, "-").slice(0, 19)

      name = `${formattedDateTime}.scroll`
      break
  }

  const fullPath = path.join(basePath, name)
  const fileExists = await exists(fullPath)

  // Recursive check to ensure unique filename
  if (fileExists) throw new Error(`File ${fullPath} exists`)

  return fullPath
}

const requestsFile = folderName => `title Traffic Data
metaTags
homeButton
buildHtml
theme gazette

printTitle

container

Real time view
 /globe.html?folderName=${folderName}

scrollButton Refresh
 link /summarizeRequests.htm?folderName=${folderName}
 post
  // Anything

.requests.csv
 ReadersWriters
 sparkline
  y Readers
  color blue
  width 200
  height 200
 sparkline
  y Writers
  color green
  width 200
  height 200
 printTable

tableSearch
scrollVersionLink
`

express.static.mime.define({ "text/plain": ["scroll", "parsers"] })
express.static.mime.define({ "text/plain": ["ssv", "psv", "tsv", "csv"] })

const parseUserAgent = userAgent => {
  if (!userAgent) return "Unknown"

  // Extract browser and OS
  const browser = userAgent.match(/(Chrome|Safari|Firefox|Edge|Opera|MSIE|Trident)[\/\s](\d+)/i)
  const os = userAgent.match(/(Mac OS X|Windows NT|Linux|Android|iOS)[\/\s]?(\d+[\._\d]*)?/i)

  let result = []
  if (browser) result.push(browser[1] + (browser[2] ? "." + browser[2] : ""))
  if (os) result.push(os[1].replace(/ /g, "") + (os[2] ? "." + os[2].replace(/_/g, ".") : ""))

  return result.join(" ") || "Other"
}

const isUrl = str => str.startsWith("http://") || str.startsWith("https://")

// todo: clean this up. add all test cases
const sanitizeFolderName = name => {
  name = name.replace(/\.git$/, "")
  // if given a url, return the last part
  // given http://hub.com/foo returns foo
  // given http://hub.com/foo.git returns foo
  if (isUrl(name)) {
    try {
      const url = new URL(name)
      const { hostname, pathname } = url
      // given http://hub.com/ return hub.com
      name = pathname.split("/").pop()
      if (!name) return hostname
      return name.toLowerCase().replace(/[^a-z0-9._]/g, "")
    } catch (err) {
      console.error(err)
    }
  }
  name = name.split("/").pop()
  return name.toLowerCase().replace(/[^a-z0-9._]/g, "")
}

const sanitizeFileName = name => name.replace(/[^a-zA-Z0-9._\-]/g, "")

class ScrollHub {
  constructor(dir = path.join(os.homedir(), "folders")) {
    this.app = express()
    const app = this.app
    this.port = 80
    this.maxUploadSize = 100 * 1000 * 1024
    this.hostname = os.hostname()
    this.wildCardCerts = []
    this.rootFolder = dir
    const hubFolder = path.join(dir, ".hub")
    this.hubFolder = hubFolder
    this.publicFolder = path.join(hubFolder, "public")
    this.trashFolder = path.join(hubFolder, "trash")
    this.globalLogFile = path.join(hubFolder, ".log.txt")
    this.slowLogFile = path.join(hubFolder, ".slow.txt")
    this.storyLogFile = path.join(hubFolder, ".writes.txt")
    this.folderCache = {}
    this.sseClients = new Set()
    this.folderIndex = new FolderIndex(this)
    this.trafficMonitor = new TrafficMonitor(this.globalLogFile, this.hubFolder)
    this.version = packageJson.version
    const configPath = path.join(hubFolder, `config.scroll`)
    this.config = fs.existsSync(configPath) ? Particle.fromDisk(configPath) : new Particle()
  }

  startAll() {
    const { rootFolder } = this
    const lastFolder = rootFolder.split("/").pop()
    process.title = process.title + ` ScrollHub ${lastFolder}`
    this.startTime = Date.now()
    this.ensureInstalled()
    this.ensureTemplatesInstalled()
    this.warmFolderCache()
    this.initVandalProtection()
    this.enableCompression()
    this.enableCors()
    this.enableFormParsing()
    this.enableFileUploads()

    this.initAnalytics()
    this.addStory({ ip: "admin" }, `started ScrollHub v${this.version}`)
    console.log(`ScrollHub version: ${this.version}`)
    console.log(`Serving all folders in: ${this.rootFolder}`)
    console.log(`Saving runtime data in: ${this.hubFolder}`)
    console.log(`Max memory: ${v8.getHeapStatistics().heap_size_limit / 1024 / 1024} MB`)

    this.initFileRoutes()
    this.initAIRoutes()
    this.initGitRoutes()
    this.initHistoryRoutes()
    this.initZipRoutes()
    this.initCommandRoutes()
    this.initSSERoute()
    this.initCloneRoute()
    this.initScriptRunner()

    this.enableStaticFileServing()

    this.servers = []
    if (!this.isLocalHost) this.servers.push(this.startHttpsServer())

    this.servers.push(this.startHttpServer())
    this.init404Routes()
    this.cronRunner = new CronRunner(this).start()
    return this
  }

  initCloneRoute() {
    const { folderCache, app } = this
    app.get("/clone", (req, res) => {
      const folderName = this.getFolderName(req)
      if (!folderCache[folderName]) return res.status(404).send("Folder not found")

      const html = `

 Clone ${folderName}
 
   body { margin: 0; }
   iframe { width: 100%; height: 100vh; border: none; }
   .clone-btn { 
     position: fixed; 
     top: 50%; 
     left: 50%;
     transform: translate(-50%, -50%);
     z-index: 100; 
     padding: 30px 60px;
     background: #0066cc; 
     color: white;
     border: none; 
     border-radius: 8px;
     cursor: pointer;
     font-size: 24px;
     font-weight: bold;
     box-shadow: 0 4px 12px rgba(0,0,0,0.2);
     transition: all 0.2s;
   }
   .clone-btn:hover { 
     background: #0052a3;
     transform: translate(-50%, -50%) scale(1.05);
   }
 

 Clone this site
 
 
 function cloneSite() {
   fetch('/cloneFolder.htm', {
     method: 'POST',
     headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
     body: 'folderName=${folderName}&redirect=false'
   })
   .then(res => res.text())
   .then(name => window.location.href = '/edit.html?folderName=' + name);
 }
 

`
      res.send(html)
    })
  }

  initScriptRunner() {
    this.scriptRunner = new ScriptRunner(this)
    this.scriptRunner.init()
  }

  initSSERoute() {
    const { app, globalLogFile } = this
    app.get("/.requests.htm", (req, res) => {
      const folderName = req.query?.folderName
      req.headers["accept-encoding"] = "identity"
      res.writeHead(200, {
        "Content-Type": "text/event-stream",
        "Cache-Control": "no-cache",
        Connection: "keep-alive"
      })

      // Send initial ping
      res.write(": ping\n\n")

      const id = Date.now()

      const client = {
        id,
        res,
        folderName
      }

      this.sseClients.add(client)

      req.on("close", () => this.sseClients.delete(client))
    })
  }

  async broadCastMessage(folderName, log, ip) {
    if (!this.sseClients.size) return
    const geo = await this.trafficMonitor.ipToGeo(ip === "::1" ? "98.150.188.43" : ip)
    const name = (geo.regionName + "/" + geo.country).replace(/ /g, "")
    log = [log.trim(), name, geo.lat, geo.lon].join(" ")
    this.sseClients.forEach(client => {
      if (!client.folderName || client.folderName === folderName) client.res.write(`data: ${JSON.stringify({ log })}\n\n`)
    })
  }

  enableCompression() {
    this.app.use(compression())
  }

  getBaseUrlForFolder(folderName, hostname, protocol, isLocalHost) {
    // if localhost, no custom domains
    if (isLocalHost) return `/${folderName}`

    if (!folderName.includes(".")) return protocol + "//" + hostname + "/" + folderName

    // now it might be a custom domain, serve it as if it is
    // of course, sometimes it would not be
    return protocol + "//" + folderName
  }

  enableCors() {
    this.app.use((req, res, next) => {
      res.setHeader("Access-Control-Allow-Origin", "*")
      res.setHeader("Access-Control-Allow-Methods", "GET, POST, OPTIONS")
      res.setHeader("Access-Control-Allow-Headers", "Content-Type, Authorization")

      // Handle preflight requests
      if (req.method === "OPTIONS") {
        return res.status(200).end()
      }

      next()
    })
  }

  enableFormParsing() {
    this.app.use(express.json())
    this.app.use(express.urlencoded({ extended: true }))
  }

  enableFileUploads() {
    this.app.use(fileUpload({ limits: { fileSize: this.maxUploadSize } }))
  }

  async sendFolderNotFound(res, hostname) {
    const message = `title Folder Not Found

css
 body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
  max-width: 600px;
  margin: 40px auto;
  padding: 20px;
  line-height: 1.6;
 }
 h1 { color: #333; }
 .message { color: #666; }
 .suggestion { margin-top: 20px; color: #0066cc; }

# Folder Not Found

The folder "${hostname}" does not exist on this ScrollHub instance.
 link https://github.com/breck7/ScrollHub ScrollHub
 class message

If you'd like to create this folder, visit our main site to get started.
 link https://${this.hostname} our main site
 class suggestion`
    // Use 400 (Bad Request) for unknown hostname
    const html = await ScrollToHtml(message)
    res.status(400).send(html)
    return
  }

  enableStaticFileServing() {
    const { app, folderCache, rootFolder } = this

    const isRootHost = req => {
      const hostname = req.hostname?.toLowerCase()
      // If its the main hostname, serve the folders directly
      if (hostname === this.hostname || hostname === "localhost") return true
      const ipv4Regex = /^(\d{1,3}\.){3}\d{1,3}$/
      if (ipv4Regex.test(hostname))
        // treat direct IP requests as host requests
        return true
      return false
    }

    app.use((req, res, next) => {
      const hostname = req.hostname?.toLowerCase()

      // If no hostname, continue to next middleware
      if (!hostname) return next()

      // If hostname is the main server hostname, continue to next middleware
      if (isRootHost(req)) return next()

      // If the hostname requested isnt root host and doesn't exist in folderCache, return 400
      if (!folderCache[hostname]) return this.sendFolderNotFound(res, hostname)

      // If domain exists, serve from its folder
      const folderPath = path.join(rootFolder, hostname)
      express.static(folderPath, { dotfiles: "allow" })(req, res, next)
    })

    app.use((req, res, next) => {
      // On the root host, all folders are served like: rootDomain/folder/
      if (isRootHost(req)) return express.static(rootFolder, { dotfiles: "allow" })(req, res, next)
      next()
    })

    // Serve the process's public folder
    app.use(express.static(this.publicFolder, { dotfiles: "allow" }))
  }

  init404Routes() {
    const { app, rootFolder, publicFolder } = this
    //The 404 Route (ALWAYS Keep this as the last route)
    app.get("*", async (req, res) => {
      const folderName = this.getFolderName(req)
      const folderPath = path.join(rootFolder, folderName)

      const notFoundPage = path.join(folderPath, "404.html")
      await fsp
        .access(notFoundPage)
        .then(() => {
          res.status(404).sendFile(notFoundPage)
        })
        .catch(() => {
          res.status(404).sendFile(path.join(publicFolder, "404.html"))
        })
    })
  }

  isSummarizing = {}
  async buildRequestsSummary(folder = "") {
    const { rootFolder, folderCache, hubFolder } = this
    if (this.isSummarizing[folder]) return
    this.isSummarizing[folder] = true
    if (folder && !folderCache[folder]) return
    const logFile = folder ? this.getFolderLogFile(folder) : this.globalLogFile
    const outputPath = folder ? path.join(rootFolder, folder) : path.join(this.publicFolder)
    const trafficMonitor = new TrafficMonitor(logFile, hubFolder)
    await trafficMonitor.processLogFile()
    const content = folder ? trafficMonitor.csv : trafficMonitor.csvTotal
    await fsp.writeFile(path.join(outputPath, ".requests.csv"), content, "utf8")
    if (folder) {
      const reqFile = path.join(outputPath, ".requests.scroll")
      await fsp.writeFile(reqFile, requestsFile(folder), "utf8")
      const file = new ScrollFile(undefined, reqFile, new ScrollFileSystem())
      await file.fuse()
      await file.scrollProgram.buildAll()
    } else await this.buildPublicFolder()
    this.isSummarizing[folder] = false
  }

  initAnalytics() {
    const checkWritePermissions = this.checkWritePermissions.bind(this)
    if (!fs.existsSync(this.storyLogFile)) fs.writeFileSync(this.storyLogFile, "", "utf8")
    const { app, folderCache } = this

    app.use((req, res, next) => {
      req.startTime = performance.now()

      res.on("finish", () => {
        this.logRequest(req, res)
      })
      next()
    })

    app.use("/summarizeRequests.htm", checkWritePermissions, async (req, res) => {
      const folderName = this.getFolderName(req)
      if (folderName) {
        await this.buildRequestsSummary(folderName)
        if (req.body.particle) return res.send("Done.")
        const base = this.getBaseUrlForFolder(folderName, req.hostname, req.protocol + ":", this.isLocalHost)
        return res.redirect(base + "/.requests.html")
      }
      await this.buildRequestsSummary()
      res.send(`Done.`)
    })

    app.get("/hostname.htm", (req, res) => res.send(req.hostname))
  }

  reqToLog(req, res) {
    const { hostname, method, url, protocol } = req
    const ip = req.ip || req.connection.remoteAddress
    const userAgent = parseUserAgent(req.get("User-Agent") || "Unknown")
    const folderName = this.getFolderName(req)
    const responseTime = ((performance.now() - req.startTime) / 1000).toFixed(1)
    return `${method === "GET" ? "read" : "write"} ${folderName || hostname} ${protocol}://${hostname}${url} ${Date.now()} ${ip} ${responseTime} ${res.statusCode} ${userAgent}\n`
  }

  async logRequest(req, res) {
    const { folderCache, globalLogFile, slowLogFile } = this
    const ip = req.ip || req.connection.remoteAddress
    const folderName = this.getFolderName(req)

    const logEntry = this.reqToLog(req, res)
    fs.appendFile(globalLogFile, logEntry, err => {
      if (err) console.error("Failed to log request:", err)
    })

    if (performance.now() - req.startTime > 1000) {
      fs.appendFile(slowLogFile, logEntry, err => {
        if (err) console.error("Failed to log slow request:", err)
      })
    }

    this.broadCastMessage(folderName, logEntry, ip)

    if (folderName && folderCache[folderName]) {
      const folderLogFile = this.getFolderLogFile(folderName)
      try {
        await fsp.appendFile(folderLogFile, logEntry)
      } catch (err) {
        console.error(`Failed to log request to folder log (${folderLogFile}):`, err)
      }
    }
  }

  getFolderLogFile(folderName) {
    const { rootFolder } = this
    const folderPath = path.join(rootFolder, folderName)
    return path.join(folderPath, ".log.txt")
  }

  initGitRoutes() {
    const { app, rootFolder } = this
    const checkWritePermissions = this.checkWritePermissions.bind(this)
    app.get("/:repo.git/*", (req, res) => {
      const repo = req.params.repo
      const repoPath = path.join(rootFolder, repo)
      req.url = "/" + req.url.split("/").slice(2).join("/")
      const handlers = httpBackend(req.url, (err, service) => {
        if (err) return res.end(err + "\n")
        res.setHeader("content-type", service.type)
        const ps = spawn(service.cmd, service.args.concat(repoPath))
        ps.stdout.pipe(service.createStream()).pipe(ps.stdin)
      })
      req.pipe(handlers).pipe(res)
    })

    app.post("/:repo.git/*", checkWritePermissions, async (req, res) => {
      const repo = req.params.repo
      const repoPath = path.join(rootFolder, repo)
      req.url = "/" + req.url.split("/").slice(2).join("/")
      const handlers = httpBackend(req.url, (err, service) => {
        if (err) return res.end(err + "\n")
        res.setHeader("content-type", service.type)
        const ps = spawn(service.cmd, service.args.concat(repoPath))
        ps.stdout.pipe(service.createStream()).pipe(ps.stdin)
        // Handle Git pushes asynchronously and build the scroll
        ps.on("close", async code => {
          if (code === 0 && service.action === "push") {
            const folderName = repoPath.split("/").pop()
            await this.buildFolder(folderName)
            this.addStory(req, `pushed ${repo}`)
            this.updateFolderAndBuildList(repo)
          }
        })
      })
      req.pipe(handlers).pipe(res)
    })
  }

  initHistoryRoutes() {
    const { app, rootFolder, folderCache, folderIndex } = this
    const checkWritePermissions = this.checkWritePermissions.bind(this)
    app.get("/revisions.htm/:folderName", async (req, res) => {
      const folderName = req.params.folderName
      const folderPath = path.join(rootFolder, folderName)
      if (!folderCache[folderName]) return res.status(404).send("Folder not found")
      try {
        // Get the git log asynchronously and format it as CSV
        const { stdout: gitLog } = await execAsync(`git log --pretty=format:"%h,%an,%ad,%at,%s" --date=short`, { cwd: folderPath })

        res.setHeader("Content-Type", "text/plain; charset=utf-8")
        const header = "commit,author,date,timestamp,message\n"
        res.send(header + gitLog)
      } catch (error) {
        console.error(error)
        res.status(500).send("An error occurred while fetching the git log")
      }
    })
    app.get("/commits.htm", async (req, res) => {
      const folderName = this.getFolderName(req)
      if (!folderCache[folderName]) return res.status(404).send("Folder not found")
      await folderIndex.sendCommits(folderName, req.query.count || 10, res)
    })
    app.get("/commits.json", async (req, res) => {
      const folderName = this.getFolderName(req)
      if (!folderCache[folderName]) return res.status(404).send("Folder not found")
      const commits = await folderIndex.getCommits(folderName, req.query.count || 10)
    })

    app.post("/revert.htm/:folderName", checkWritePermissions, async (req, res) => {
      const folderName = req.params.folderName
      const targetHash = req.body.hash
      const folderPath = path.join(rootFolder, folderName)

      if (!folderCache[folderName]) return res.status(404).send("Folder not found")

      if (!targetHash || !/^[0-9a-f]{40}$/i.test(targetHash)) return res.status(400).send("Invalid target hash provided")

      try {
        // Perform the revert
        const clientIp = req.ip || req.connection.remoteAddress
        const hostname = req.hostname?.toLowerCase()
        await execAsync(`git checkout ${targetHash} . && git add . && git commit --author="${clientIp} " -m "Reverted to ${targetHash}" --allow-empty`, { cwd: folderPath })

        this.addStory(req, `reverted ${folderName}`)

        await this.buildFolder(folderName)

        res.redirect("/commits.htm?folderName=" + folderName)
        this.updateFolderAndBuildList(folderName)
      } catch (error) {
        console.error(error)
        res.status(500).send(`An error occurred while reverting the repository:\n ${error.toString().replace(/ directoriesSet.add(path.join(folderPath, path.dirname(file))))

    const files = cachedEntry.files
    for (let dir of directoriesSet) {
      const fileNames = (await fsp.readdir(dir, { withFileTypes: true })).filter(dirent => dirent.isFile() && dirent.name !== ".git" && dirent.name !== ".DS_Store").map(dirent => dirent.name)
      fileNames.forEach(file => {
        const relativePath = path.join(dir, file).replace(folderPath, "").substr(1)
        if (!files[relativePath])
          files[relativePath] = {
            versioned: false
          }
      })
    }
    return files
  }

  async handleCreateFolder(newFolderName, req, res) {
    try {
      const result = await this.createFolder(newFolderName)
      if (result.errorMessage) return this.handleCreateError(res, result)
      const { folderName } = result
      this.addStory(req, `created ${folderName}`)
      res.redirect(`/edit.html?folderName=${folderName}&command=showWelcomeMessageCommand`)
    } catch (error) {
      console.error(error)
      res.status(500).send("Sorry, an error occurred while creating the folder:", error)
    }
  }

  initAIRoutes() {
    const { app, folderCache } = this
    const checkWritePermissions = this.checkWritePermissions.bind(this)
    const agents = new Agents(this)
    app.post("/createFromPrompt.htm", checkWritePermissions, async (req, res) => {
      try {
        const prompt = req.body.prompt
        const agent = (req.body.agent || "claude").toLowerCase()
        const template = req.body.template
        const welcomeMessage = req.body.welcomeMessage || "scrollhub"
        const domainSuffix = req.body.tld || "scroll.pub"
        if (!prompt) return res.status(400).send("Prompt is required")

        // Get existing names for domain uniqueness check
        const existingNames = Object.keys(this.folderCache)

        // Generate website content from prompt
        const response = await agents.createFolderNameAndFilesFromPrompt(prompt, existingNames, agent, template, domainSuffix)
        const { folderName, files } = response.parsedResponse
        files["prompt.json"] = JSON.stringify(response.completion, null, 2)

        // Create the folder with generated files
        await this.createFolderFromFiles(folderName, files)

        try {
          await this.buildFolder(folderName)
        } catch (err) {
          console.error(err)
        }

        // Add to story and redirect
        this.addStory(req, `created ${folderName} from prompt using ${agent}`)
        res.redirect(`/edit.html?folderName=${folderName}&command=showWelcomeMessageCommand&welcomeMessage=${welcomeMessage}`)
      } catch (error) {
        console.error("Error creating from prompt:", error)
        res.status(500).send("Failed to create website from prompt: " + error.message)
      }
    })
  }

  async doesHaveSslCert(folderName) {
    // by default assume root server has ssl certs
    if (!folderName.includes(".")) return true
    // Now we see if the custom domain has one
    const certPath = this.makeCertPath(folderName)
    const hasSslCert = await exists(certPath)
    return hasSslCert ? hasSslCert : this.getMatchingWildcardCert(folderName)
  }

  makeCertPath(folderName) {
    return path.join(this.rootFolder, folderName, `.${folderName}.crt`)
  }

  initStampRoute() {
    const { app, rootFolder, folderCache } = this

    // Text file extensions - only include actual text formats
    const textExtensions = new Set("scroll parsers txt html htm rb php md perl py mjs css json csv tsv psv ssv js".split(" "))

    const isTextFile = filepath => {
      const ext = path.extname(filepath).toLowerCase().slice(1)
      return textExtensions.has(ext)
    }

    async function makeStamp(dir) {
      let stamp = "stamp\n"

      const handleFile = async (indentation, relativePath, itemPath) => {
        if (!isTextFile(itemPath)) return
        stamp += `${indentation}${relativePath}\n`
        const content = await fsp.readFile(itemPath, "utf8")
        stamp += `${indentation} ${content.replace(/\n/g, `\n${indentation} `)}\n`
      }

      let gitTrackedFiles

      async function processDirectory(currentPath, depth) {
        const items = await fsp.readdir(currentPath)

        for (const item of items) {
          const itemPath = path.join(currentPath, item)
          const relativePath = path.relative(dir, itemPath)

          if (!gitTrackedFiles.has(relativePath)) continue

          const stats = await fsp.stat(itemPath)
          const indentation = " ".repeat(depth)

          if (stats.isDirectory()) {
            stamp += `${indentation}${relativePath}/\n`
            await processDirectory(itemPath, depth + 1)
          } else if (stats.isFile()) {
            await handleFile(indentation, relativePath, itemPath)
          }
        }
      }

      const stats = await fsp.stat(dir)
      if (stats.isDirectory()) {
        // Get list of git-tracked files
        const { stdout } = await execAsync("git ls-files", { cwd: dir })
        gitTrackedFiles = new Set(stdout.split("\n").filter(Boolean))
        await processDirectory(dir, 1)
      } else {
        await handleFile(" ", dir, dir)
      }

      return stamp.trim()
    }

    app.get("/stamp", async (req, res) => {
      const folderName = this.getFolderName(req)
      const { rootFolder, folderCache } = this

      // Check if folder exists
      if (!folderCache[folderName]) return res.status(404).send("Folder not found")

      const folderPath = path.join(rootFolder, folderName)

      try {
        // Generate the stamp
        const stamp = await makeStamp(folderPath)

        // Set content type and send response
        res.setHeader("Content-Type", "text/plain; charset=utf-8")
        res.send(stamp)
      } catch (error) {
        console.error("Error generating stamp:", error)
        res.status(500).send(`Error generating stamp: ${error.toString().replace(/ this.handleCreateFolder(req.body.folderName, req, res))

    app.post("/cloneFolder.htm", checkWritePermissions, async (req, res) => {
      try {
        const sourceFolderName = req.body.folderName || (req.body.particle ? new Particle(req.body.particle).get("folderName") : "")
        if (!sourceFolderName) return res.status(500).send("No folder name provided")
        const cloneName = this.getCloneName(sourceFolderName)
        const result = await this.createFolder(sourceFolderName + " " + cloneName)
        if (result.errorMessage) return this.handleCreateError(res, result)
        const { folderName } = result
        this.addStory(req, `cloned ${sourceFolderName} to ${cloneName}`)
        if (req.body.redirect === "false") return res.send(cloneName)
        res.redirect(`/edit.html?folderName=${cloneName}&command=showWelcomeMessageCommand`)
      } catch (error) {
        console.error(error)
        res.status(500).send("Sorry, an error occurred while cloning the folder:", error)
      }
    })

    app.get("/ls.json", async (req, res) => {
      const folderName = this.getFolderName(req)
      const folderEntry = folderCache[folderName]
      if (!folderEntry) return res.status(404).send(`Folder '${folderName}' not found`)
      res.setHeader("Content-Type", "text/json")
      const files = await this.getFileList(folderName)
      if (folderEntry.hasSslCert === undefined) folderEntry.hasSslCert = await this.doesHaveSslCert(folderName)

      res.send(JSON.stringify({ files, hasSslCert: folderEntry.hasSslCert }, undefined, 2))
    })

    app.get("/ls.csv", async (req, res) => {
      const folderName = this.getFolderName(req)
      const folderEntry = folderCache[folderName]
      if (!folderEntry) return res.status(404).send(`Folder '${folderName}' not found`)
      res.setHeader("Content-Type", "text/plain")
      const files = await this.getFileList(folderName)
      res.send(new Particle(files).asCsv)
    })

    this.initStampRoute()

    app.get("/readFile.htm", async (req, res) => {
      const filePath = path.join(rootFolder, decodeURIComponent(req.query.filePath))
      try {
        const fileExists = await exists(filePath)
        if (!fileExists) return res.status(404).send(`File '${filePath}' not found`)

        const content = await fsp.readFile(filePath, "utf8")
        res.setHeader("Content-Type", "text/plain")
        res.send(content)
      } catch (error) {
        console.error(error)
        res.status(500).send(`An error occurred while reading '${filepath}'.`)
      }
    })

    app.post("/writeFile.htm", checkWritePermissions, (req, res) => this.writeAndCommitTextFile(req, res, req.body.filePath, req.body.content))

    app.post("/set", checkWritePermissions, async (req, res) => {
      const { rootFolder, folderCache } = this
      const folderName = this.getFolderName(req)
      if (!folderCache[folderName]) return res.status(404).send("Folder not found")

      const { file, line } = req.query
      if (!file) return res.status(400).send("No filename provided")

      const filePath = path.join(rootFolder, folderName, file)

      try {
        // Check if file exists
        const fileExists = await exists(filePath)
        if (!fileExists) return res.status(404).send("File not found")

        // Read the current content
        const content = await fsp.readFile(filePath, "utf8")

        // Parse into Particle
        const particle = new Particle(content)

        // Set the new content at the specified line
        const parts = line.split(" ")
        particle.set(parts[0], parts.slice(1).join(" "))

        const relativePath = filePath.replace(rootFolder, "")

        this.writeAndCommitTextFile(req, res, relativePath, particle.toString(), folderName)
      } catch (error) {
        console.error(`Error in /set route:`, error)
        res.status(500).send(`An error occurred while setting particle content: ${error.toString().replace(/ {
      const stripped = req.body.content.replace(/\r/g, "")
      let content = stripped
      let filenameStrategy
      let folderName
      let subfolders
      let redirect
      if (req.query.folderName) {
        // Query string
        folderName = this.getFolderName(req)
        filenameStrategy = req.query.filenameStrategy
        subfolders = req.query.subfolders?.split("/") || []
        redirect = req.query.redirect
      } else {
        // Top matter
        const parts = stripped.split("\n\n")
        const topMatter = new Particle(parts.shift())
        content = parts.join("\n\n")
        folderName = topMatter.get("folderName") || this.getFolderName(req)
        filenameStrategy = topMatter.get("filenameStrategy")
        redirect = topMatter.get("redirect")
        subfolders = topMatter.get("subfolder")?.split("/") || []
      }
      if (!folderCache[folderName]) return res.status(404).send("Folder not found")
      const basePath = path.join(folderName, ...subfolders)
      try {
        const filePath = await generateFileName(basePath, filenameStrategy, content)
        this.writeAndCommitTextFile(req, res, filePath, content, folderName, redirect)
      } catch (err) {
        return res.status(400).send(err.message)
      }
    })

    // Add a route for file uploads
    app.post("/uploadFile.htm", checkWritePermissions, async (req, res) => {
      if (!req.files || Object.keys(req.files).length === 0) return res.status(400).send("No files were uploaded.")

      const file = req.files.file
      const folderName = req.body.folderName
      const folderPath = path.join(rootFolder, folderName)

      if (!folderCache[folderName]) return res.status(404).send("Folder not found")

      // Check file extension
      const fileExtension = path.extname(file.name).toLowerCase().slice(1)

      if (file.size > this.maxUploadSize) return res.status(400).send("File size exceeds the maximum limit of 1MB.")

      // Save file to disk
      const fileName = sanitizeFileName(path.basename(file.name, path.extname(file.name))) + "." + fileExtension
      const filePath = path.join(folderPath, fileName)

      try {
        // Use async `mv` with `await`
        await file.mv(filePath)

        // Run git and scroll commands asynchronously
        await execAsync(`git add -f ${fileName}; git commit -m 'Added ${fileName}'`, { cwd: folderPath })
        this.addStory(req, `uploaded ${fileName} to ${folderName}`)
        res.send("File uploaded successfully")
        this.updateFolderAndBuildList(folderName)
      } catch (err) {
        console.error(err)
        res.status(500).send("An error occurred while uploading or processing the file: " + err.message)
      }
    })

    app.post("/createFolderFromFiles.htm", checkWritePermissions, async (req, res) => {
      if (!req.files || !req.files["files[]"]) return res.status(400).send("No files were uploaded.")

      try {
        // Generate a unique folder name
        const folderName = await this.findAvailableFolderName()
        const folderPath = path.join(this.rootFolder, folderName)

        // Create the folder
        await fsp.mkdir(folderPath, { recursive: true })

        // Handle multiple files
        const uploadedFiles = Array.isArray(req.files["files[]"]) ? req.files["files[]"] : [req.files["files[]"]]

        // Process each file
        for (const file of uploadedFiles) {
          const filePath = path.join(folderPath, file.name)

          // Create necessary subdirectories
          await fsp.mkdir(path.dirname(filePath), { recursive: true })

          // Move the file to its destination
          await file.mv(filePath)
        }

        // Initialize git repository
        await execAsync("git init", { cwd: folderPath })
        await execAsync("git add .", { cwd: folderPath })
        await execAsync('git commit -m "Initial commit from uploaded files"', { cwd: folderPath })

        // Add to story and update caches
        this.addStory(req, `created ${folderName} from uploaded files`)
        await this.updateFolderAndBuildList(folderName)

        // Build the folder
        await this.buildFolder(folderName)

        // Send the folder name back
        res.send(folderName)
      } catch (error) {
        console.error(`Error creating folder from files:`, error)
        res.status(500).send(`An error occurred while creating folder from files: ${error.toString().replace(/ {
      if (!req.files || !req.files.zipFile) return res.status(400).send("No zip file was uploaded.")

      const zipFile = req.files.zipFile
      const suggestedName = req.body.folderName || path.basename(zipFile.name, ".zip").toLowerCase()
      const folderName = sanitizeFolderName(suggestedName)

      // Validate folder name
      if (!this.isValidFolderName(folderName)) return res.status(400).send(`Invalid folder name "${folderName}". Folder names must start with a letter a-z, ` + `be more than 1 character, and not end in a common file extension.`)

      // Check if folder already exists
      if (this.folderCache[folderName]) return res.status(409).send(`A folder named "${folderName}" already exists`)

      const folderPath = path.join(this.rootFolder, folderName)
      const tempPath = path.join(os.tmpdir(), `scroll-${Date.now()}`)

      try {
        // Create temp directory
        await fsp.mkdir(tempPath, { recursive: true })

        // Write zip file to temp location
        const tempZipPath = path.join(tempPath, "upload.zip")
        await zipFile.mv(tempZipPath)

        // Create the target folder
        await fsp.mkdir(folderPath, { recursive: true })

        // Unzip the file
        await execAsync(`unzip "${tempZipPath}"`, { cwd: folderPath })

        // Initialize git repository
        if (!fs.existsSync(path.join(folderPath, ".git"))) await execAsync(`git init; git add .; git commit -m "Initial import from zip file"`, { cwd: folderPath })

        // Add to story and update caches
        this.addStory(req, `created ${folderName} from zip file`)
        this.updateFolderAndBuildList(folderName)

        // Build the folder
        await this.buildFolder(folderName)

        // Redirect to editor
        res.send(folderName)
      } catch (error) {
        console.error(`Error creating folder from zip:`, error)
        res.status(500).send(`An error occurred while creating folder from zip: ${error.toString().replace(/ {
      res.setHeader("Content-Type", "text/plain")
      res.send(req.body)
    })

    app.post("/insert.htm", checkWritePermissions, async (req, res) => {
      const folderName = this.getFolderName(req)

      if (!folderCache[folderName]) return res.status(404).send("Folder not found")

      // Which file to insert data to
      const fileName = sanitizeFileName(req.query.fileName)

      // Where to redirect after success
      const redirectUrl = sanitizeFileName(req.query.redirect)
      const line = parseInt(req.query.line)
      let particles = req.body.particles

      if (!particles) return res.status(400).send("No particles provided")

      if (!fileName) return res.status(400).send("No filename provided")

      const folderPath = path.join(rootFolder, folderName)
      const filePath = path.join(folderPath, fileName)

      particles = "\n" + particles // add a new line before new particles
      try {
        // Default is append
        if (req.query.line === undefined) {
          await fsp.appendFile(filePath, particles)
        } else {
          await fsp.access(filePath)
          let content = await fsp.readFile(filePath, "utf8")
          let lines = content.split("\n")
          lines.splice(line - 1, 0, particles)
          content = lines.join("\n")
          await fsp.writeFile(filePath, content, "utf8")
        }

        // Run git commands
        const clientIp = req.ip || req.connection.remoteAddress
        const hostname = req.hostname?.toLowerCase()
        await execAsync(`git add "${fileName}"; git commit --author="${clientIp} " -m 'Inserted particles into ${fileName}'`, { cwd: folderPath })

        this.addStory(req, `inserted particles into ${folderPath}/${fileName}`)
        this.buildFolder(folderName)
        res.redirect(redirectUrl)
        this.updateFolderAndBuildList(folderName)
      } catch (error) {
        if (error.code === "ENOENT") {
          res.status(404).send("File not found")
        } else {
          console.error(error)
          res.status(500).send(`An error occurred while inserting the particles:\n ${error.toString().replace(/ {
      const folderName = this.getFolderName(req)
      const filePath = path.join(rootFolder, folderName, decodeURIComponent(req.query.filePath))

      if (!folderCache[folderName]) return res.status(404).send("Folder not found")

      try {
        const fileExists = await exists(filePath)
        if (!fileExists) return res.status(404).send(`File '${filePath}' not found`)

        const fileName = path.basename(filePath)
        const folderPath = path.dirname(filePath)

        await fsp.unlink(filePath)
        await execAsync(`git rm ${fileName}; git commit -m 'Deleted ${fileName}'`, { cwd: folderPath })

        res.send("File deleted successfully")
        this.addStory(req, `deleted ${fileName} in ${folderName}`)
        this.updateFolderAndBuildList(folderName)
      } catch (error) {
        console.error(error)
        res.status(500).send(`An error occurred while deleting the file:\n ${error.toString().replace(/ {
      const { trashFolder } = this
      const folderName = req.body.folderName
      if (!folderCache[folderName]) return res.status(404).send("Folder not found")

      const sourcePath = path.join(rootFolder, folderName)
      const timestamp = Date.now()
      const destinationPath = path.join(trashFolder, `${folderName}-${timestamp}`)

      try {
        // Move the folder to trash
        await fsp.rename(sourcePath, destinationPath)

        // Remove the folder from the cache
        delete folderCache[folderName]

        // Rebuild the list file
        this.buildListFile()

        this.addStory(req, `trashed ${folderName}`)

        res.send("Folder moved to trash successfully")
      } catch (error) {
        console.error(error)
        res.status(500).send(`An error occurred while moving the folder to trash:\n ${error.toString().replace(/ {
      const folderName = req.body.folderName
      if (!folderCache[folderName]) return res.status(404).send("Folder not found")

      const oldFileName = req.body.oldFileName
      const newFileName = sanitizeFileName(req.body.newFileName)

      const folderPath = path.join(rootFolder, folderName)
      const oldFilePath = path.join(folderPath, oldFileName)
      const newFilePath = path.join(folderPath, newFileName)

      try {
        // Check if the old file exists
        await fsp.access(oldFilePath)

        // Run git commands
        const clientIp = req.ip || req.connection.remoteAddress
        const hostname = req.hostname?.toLowerCase()
        await execAsync(`git mv ${oldFileName} ${newFileName}; git commit --author="${clientIp} " -m 'Renamed ${oldFileName} to ${newFileName}'`, { cwd: folderPath })
        this.addStory(req, `renamed ${oldFileName} to ${newFileName} in ${folderName}`)
        res.send("File renamed successfully")
        this.updateFolderAndBuildList(folderName)
      } catch (error) {
        console.error(error)
        res.status(500).send(`An error occurred while renaming the file:\n ${error.toString().replace(/ {
      const oldFolderName = req.body.oldFolderName
      const newFolderName = req.body.newFolderName

      // Validate old folder exists
      if (!folderCache[oldFolderName]) return res.status(404).send("Source folder not found")

      // Validate new folder name
      if (!this.isValidFolderName(newFolderName)) return res.status(400).send(`Invalid folder name "${newFolderName}". Folder names must start with a letter a-z, be more than 1 character, and not end in a common file extension.`)

      // Check if new folder name already exists
      if (folderCache[newFolderName]) return res.status(409).send(`A folder named "${newFolderName}" already exists`)

      const oldPath = path.join(rootFolder, oldFolderName)
      const newPath = path.join(rootFolder, newFolderName)

      try {
        // Rename the folder
        await fsp.rename(oldPath, newPath)

        // Remove from cache
        delete folderCache[oldFolderName]

        // Update folder cache with new name
        await this.folderIndex.updateFolder(newFolderName)

        // Rebuild the list file
        this.buildListFile()

        this.addStory(req, `renamed folder ${oldFolderName} to ${newFolderName}`)

        res.send("Folder renamed successfully")
      } catch (error) {
        console.error(error)
        res.status(500).send(`An error occurred while renaming the folder:\n ${error.toString().replace(/ true)
              .catch(() => false)
          ) {
            await fsp.rename(newPath, oldPath)
          }
        } catch (revertError) {
          console.error("Error reverting failed rename:", revertError)
        }
      }
    })
  }

  async findAvailableFolderName(prefix = "files") {
    const { folderCache } = this
    let counter = 1
    let folderName
    do {
      folderName = `${prefix}${counter}`
      counter++
    } while (folderCache[folderName])
    return folderName
  }

  initCommandRoutes() {
    const { app } = this
    const checkWritePermissions = this.checkWritePermissions.bind(this)

    app.get("/edit/:folderName", async (req, res) => {
      res.redirect("/edit.html?folderName=" + req.params.folderName)
    })

    app.get("/edit", async (req, res) => {
      res.redirect("/edit.html")
    })

    app.get("/test/:folderName", checkWritePermissions, async (req, res) => {
      await this.runScrollCommand(req, res, "test")
    })

    app.get("/build/:folderName", checkWritePermissions, async (req, res) => {
      await this.runScrollCommand(req, res, "build")
      this.updateFolderAndBuildList(this.getFolderName(req))
    })

    app.post("/build.htm", checkWritePermissions, async (req, res) => {
      await this.runScrollCommand(req, res, "build")
      this.updateFolderAndBuildList(this.getFolderName(req))
    })

    app.get("/format/:folderName", checkWritePermissions, async (req, res) => {
      await this.runScrollCommand(req, res, "format")
      this.updateFolderAndBuildList(this.getFolderName(req))
    })

    app.get("/status/:folderName", checkWritePermissions, async (req, res) => {
      await this.runCommand(req, res, "git status")
    })

    app.get("/blame.htm", checkWritePermissions, async (req, res) => {
      const fileName = req.query.fileName.replace(/[^a-zA-Z0-9\/_.-]/g, "")
      await this.runCommand(req, res, "git blame " + fileName)
    })
  }

  async runScrollCommand(req, res, command) {
    await this.runCommand(req, res, `scroll list | scroll ${command}`)
  }

  async runCommand(req, res, command) {
    const folderName = this.getFolderName(req)
    const { rootFolder, folderCache } = this

    if (!folderCache[folderName]) return res.status(404).send("Folder not found")

    try {
      const folderPath = path.join(rootFolder, folderName)
      const { stdout } = await execAsync(command, { cwd: folderPath })
      res.setHeader("Content-Type", "text/plain")
      res.send(stdout.toString())
    } catch (error) {
      console.error(`Error running '${command}' in '${folderName}':`, error)
      res.status(500).send(`An error occurred while running '${command}' in '${folderName}': ` + error.message)
    }
  }

  initZipRoutes() {
    const { app, folderCache } = this
    app.get("/:folderName.zip", async (req, res) => {
      const folderName = req.params.folderName
      const cacheEntry = folderCache[folderName]
      if (!cacheEntry) return res.status(404).send("Folder not found")

      // Check if the zip is in memory cache
      let zipBuffer = cacheEntry.zip

      if (!zipBuffer) {
        try {
          zipBuffer = await this.zipFolder(folderName)
          if (!zipBuffer) return res.status(404).send("Folder not found or failed to zip")
        } catch (err) {
          console.error("Error zipping folder:", err)
          return res.status(500).send("Error zipping folder")
        }
      }

      // Set headers for zip file
      res.setHeader("Content-Type", "application/zip")
      res.setHeader("Content-Disposition", `attachment; filename=${folderName}.zip`)
      res.send(zipBuffer)
    })
  }

  async zipFolder(folderName) {
    const { rootFolder, folderCache } = this
    const folderPath = path.join(rootFolder, folderName)
    console.log(`Starting zip for folder: '${folderName}'`)

    const zipBuffer = await new Promise((resolve, reject) => {
      const output = []
      let totalSize = 0

      const zip = spawn(
        "zip",
        [
          "-r", // Recursive
          "-q", // Quiet mode (less verbose)
          "-", // Output to stdout
          "." // Current directory
        ],
        {
          cwd: folderPath,
          stdio: ["ignore", "pipe", "pipe"] // Properly configure stdio
        }
      )

      // Handle stdout data
      zip.stdout.on("data", data => {
        output.push(data)
        totalSize += data.length
        // console.log(`Zip progress for ${folderName}: ${totalSize} bytes`)
      })

      // Handle potential stderr messages
      zip.stderr.on("data", data => {
        console.warn(`Zip stderr for ${folderName}:`, data.toString())
      })

      // Handle errors on the process itself
      zip.on("error", err => {
        console.error(`Zip process error for ${folderName}:`, err)
        reject(err)
      })

      // Handle completion
      zip.on("close", code => {
        if (code === 0) {
          console.log(`Successfully zipped ${folderName}: ${totalSize} bytes`)
          resolve(Buffer.concat(output))
        } else {
          const error = new Error(`Zip process failed with code ${code}`)
          console.error(`Failed to zip ${folderName}:`, error)
          reject(error)
        }
      })
    })

    // Only cache if zip was successful
    folderCache[folderName].zip = zipBuffer
    return zipBuffer
  }

  async isScrollFolder(folderName) {
    // We define a Scroll folder as one with at least 1 git commit.
    if (folderName.startsWith(".")) return false
    const folderPath = path.join(this.rootFolder, folderName)
    try {
      if (await exists(this.getStatsPath(folderName))) return true
      // Check if folder contains a .git directory
      const gitPath = path.join(folderPath, ".git")
      const stats = await fsp.stat(gitPath)
      if (!stats.isDirectory()) return false

      // Check if there's at least one commit
      const { stdout } = await execAsync("git rev-list --count HEAD", { cwd: folderPath })
      return parseInt(stdout.trim(), 10) > 0
    } catch (err) {}
    return false
  }

  getStatsPath(folderName) {
    return path.join(this.rootFolder, folderName, ".stats.json")
  }

  async warmFolderCache() {
    const folders = await fsp.readdir(this.rootFolder)
    const scrollFolders = []
    for (const folder of folders) {
      if (await this.isScrollFolder(folder)) scrollFolders.push(folder)
    }
    console.log(`Loading ${scrollFolders.length} folders.`)
    await Promise.all(scrollFolders.map(this.getFolderStats.bind(this)))
    await this.buildListFile()
    console.log(`Folder cache warmed. Time: ${(Date.now() - this.startTime) / 1000}s`)
  }

  async getFolderStats(folderName) {
    const statsPath = this.getStatsPath(folderName)
    if (await exists(statsPath)) {
      const entry = await fsp.readFile(statsPath, "utf8")
      const parsed = JSON.parse(entry)
      this.folderCache[folderName] = parsed
      const cacheOkay = parsed.scrollHubVersion // if we change cache format in future, just check scrollHubVersion here
      if (cacheOkay) return
    }
    this.folderIndex.updateFolder(folderName)
  }

  initVandalProtection() {
    const allowedIpsPath = path.join(this.hubFolder, ".allowedIps.txt")
    const readAllowedIPs = () => {
      if (!fs.existsSync(allowedIpsPath)) return null

      const data = fs.readFileSync(allowedIpsPath, "utf8")
      return new Set(
        data
          .split("\n")
          .map(ip => ip.trim())
          .filter(ip => ip)
      )
    }

    this.allowedIPs = readAllowedIPs()
    this.annoyingIps = new Set(["24.199.111.182", "198.54.134.120"])
    this.writeLimit = 50 // Maximum number of writes per minute
    this.writeWindow = 60 * 1000 // 1 minute in milliseconds
    this.ipWriteOperations = new Map()
    const ipWriteOperations = this.ipWriteOperations

    // Cleanup function to remove old entries from ipWriteOperations
    const cleanupWriteOperations = () => {
      const now = Date.now()
      for (const [ip, times] of ipWriteOperations.entries()) {
        const recentWrites = times.filter(time => now - time  now - time = this.writeLimit) {
      console.log(`Write limit exceeded for IP: ${clientIp}`)
      this.annoyingIps.add(clientIp)
      return res.status(429).send(msg)
    }

    recentWrites.push(now)
    this.ipWriteOperations.set(clientIp, recentWrites)

    if (this.allowedIPs === null || this.allowedIPs.has(clientIp)) return next()

    res.status(403).send(msg)
  }

  async formatFile(filePath, content) {
    if (!this.shouldFormat(filePath)) return content

    if (filePath.endsWith(".scroll") || filePath.endsWith(".parsers")) {
      try {
        const scrollFs = new ScrollFileSystem()
        const file = await new ScrollFile(undefined, filePath, scrollFs).fuse()
        const formatted = file.formatted
        await fsp.writeFile(filePath, formatted, "utf8")
        return formatted
      } catch (err) {
        console.error(`Error formatting ${filePath}. Continuing on. Error:`, err)
        return content
      }
    }

    // Handle Prettier-supported files
    return new Promise((resolve, reject) => {
      const process = spawn("prettier", ["--write", filePath, "--ignore-path", "/dev/null"])
      // set ignore path to dev/null to tell prettier to ignore .gitignore. todo: better ignore strategy in scroll?
      process.on("close", async code => {
        if (code === 0) {
          const result = await fsp.readFile(filePath, "utf8")
          resolve(result)
        } else {
          console.log(`Error formatting ${filePath}. Continuing on. Error:`, err)
          reject(content)
        }
      })
      process.on("error", reject)
    })
  }

  shouldFormat(filePath) {
    const prettierExtensions = [".js", ".html", ".css", ".json", ".htm", ".mjs"]
    const scrollExtensions = [".scroll", ".parsers"]
    return prettierExtensions.some(ext => filePath.endsWith(ext)) || scrollExtensions.some(ext => filePath.endsWith(ext))
  }

  async writeAndCommitTextFile(req, res, filePath, content, folderName, redirect) {
    // todo: refactor into multiple methods and unit test heavily
    content = content.replace(/\r/g, "")
    const { rootFolder, folderCache } = this
    filePath = path.join(rootFolder, filePath)

    folderName = folderName || this.getFolderName(req)
    const fileName = path.basename(filePath)
    if (!folderCache[folderName]) return res.status(404).send(`Folder '${folderName}' not found`)

    const fileExists = await exists(filePath)
    const action = fileExists ? "updated" : "created"
    const previousVersion = fileExists ? await fsp.readFile(filePath, "utf8") : null

    // Always write to disk.
    try {
      await fsp.mkdir(path.dirname(filePath), { recursive: true })
      await fsp.writeFile(filePath, content, "utf8")
      this.addStory(req, `${action} ${filePath}`)
    } catch (err) {
      return res.status(500).send("Failed to save file. Error: " + err.toString().replace(/`
      const folderPath = path.join(rootFolder, folderName)
      const relativePath = filePath.replace(folderPath, "").substr(1)
      await this.gitCommitFile(folderPath, relativePath, author, action)
    } catch (err) {
      return res.status(500).send("Save ok but git step failed, building aborted. Error: " + err.toString().replace(/ (err ? console.error(err) : ""))
  }

  ensureInstalled() {
    const { hubFolder, rootFolder, trashFolder, publicFolder } = this
    if (!fs.existsSync(hubFolder)) fs.mkdirSync(hubFolder)
    if (!fs.existsSync(rootFolder)) fs.mkdirSync(rootFolder)
    if (!fs.existsSync(trashFolder)) fs.mkdirSync(trashFolder)
    if (!fs.existsSync(publicFolder)) fs.mkdirSync(publicFolder)
    // copy public folder
    execSync(`cp -R ${path.join(__dirname, "public")} ${this.hubFolder}`)
  }

  ensureTemplatesInstalled() {
    const { rootFolder } = this
    const templatesFolder = path.join(__dirname, "templates")
    const templateDirs = fs.readdirSync(templatesFolder)
    const standardGitIgnore = fs.readFileSync(path.join(templatesFolder, "blank_template", ".gitignore"), "utf8")

    for (const dir of templateDirs) {
      const sourcePath = path.join(templatesFolder, dir)
      const destPath = path.join(rootFolder, dir)

      // Check if it's a directory
      const stats = fs.statSync(sourcePath)
      if (!stats.isDirectory()) continue

      if (fs.existsSync(destPath)) return

      // Copy the template folder to the root folder
      execSync(`cp -R ${sourcePath} ${destPath};`, { cwd: rootFolder })

      fs.writeFileSync(path.join(destPath, ".gitignore"), standardGitIgnore, "utf8")

      // Initialize Git repository
      execSync(`git init; git add .; git commit -m 'initial ${dir} template'`, { cwd: destPath })
      this.buildFolderSync(dir)
    }
  }

  async updateFolderAndBuildList(folderName) {
    await this.folderIndex.updateFolder(folderName)
    this.buildListFile()
  }

  async buildFile(filePath) {
    const file = new ScrollFile(undefined, filePath, new ScrollFileSystem())
    await file.fuse()
    await file.scrollProgram.buildAll()
  }

  buildRequests = {}
  async buildFolder(folderName) {
    if (!this.buildRequests[folderName]) this.buildRequests[folderName] = 1
    else {
      this.buildRequests[folderName]++
      return
    }
    await execAsync(`scroll list | scroll build`, { cwd: path.join(this.rootFolder, folderName) })
    const buildAgain = this.buildRequests[folderName] > 1
    this.buildRequests[folderName] = 0
    if (buildAgain) return this.buildFolder(folderName)
  }

  buildFolderSync(folderName) {
    execSync(`scroll list | scroll build`, { cwd: path.join(this.rootFolder, folderName) })
  }

  getFolderName(req) {
    const folderName = req.body?.folderName || req.query?.folderName || req.params?.folderName
    if (folderName && this.folderCache[folderName]) return folderName

    if (req.hostname && this.folderCache[req.hostname]) return req.hostname

    const folderPart = req.url.split("/")[1]
    if (folderPart && this.folderCache[folderPart]) return folderPart
    return ""
  }

  async buildListFile() {
    const folders = Object.values(this.folderCache).map(folder => folder.stats)
    const particles = new Particle(folders)
    const { publicFolder } = this
    await fsp.writeFile(path.join(publicFolder, "folders.csv"), particles.asCsv, "utf8")
    await fsp.writeFile(path.join(publicFolder, "folders.tsv"), particles.asTsv, "utf8")
    await fsp.writeFile(path.join(publicFolder, "folders.json"), JSON.stringify(folders, null, 2), "utf8")
    const processName = this.hostname + (this.port === 80 ? "" : ":" + this.port)
    const scroll = `settings.scroll
homeButton
buildHtml
metaTags
theme gazette
title Folders

scrollHubStyle.css

container 1000px
# ${processName} is serving ${folders.length} folders in ${this.rootFolder}
 index.html ${processName}
 style font-size: 150%;

center
Traffic Data | ScrollHub Version ${packageJson.version}
 .requests.html Traffic Data
Download folders as JSON | CSV | TSV
 link folders.json JSON
 link folders.csv CSV
 link folders.tsv TSV

table folders.csv
 compose links edit · zip
  select folder folderLink links revised hash files mb revisions
   compose hashLink commits.htm?folderName={folder}
    orderBy -revised
     rename revised lastRevised
      printTable

endColumns
tableSearch
scrollVersionLink`
    // todo: move these to .hub folder. 1 per process.
    await fsp.writeFile(path.join(publicFolder, "folders.scroll"), scroll, "utf8")
    await fsp.writeFile(path.join(publicFolder, "foldersPublished.html"), `${folders.length} folders`, "utf8")
    await this.buildPublicFolder()
  }

  async buildPublicFolder() {
    await execAsync(`scroll build`, { cwd: this.publicFolder })
  }

  handleCreateError(res, params) {
    res.redirect(`/index.html?${new URLSearchParams(params).toString()}`)
  }

  reservedExtensions = "scroll parsers txt html htm md rb php perl py mjs css json csv tsv psv ssv pdf js jpg jpeg png gif webp svg heic ico mp3 mp4 mov mkv ogg webm ogv woff2 woff ttf otf tiff tif bmp eps git".split(" ")

  isValidFolderName(name) {
    if (name.length  1) {
      template = parts.shift()
      if (folderCache[template]) folderName = parts.join("")
      else if (isUrl(template)) folderName = sanitizeFolderName(parts.join(" "))
      else {
        template = "blank_template"
        folderName = sanitizeFolderName(rawInput)
      }
    } else {
      folderName = sanitizeFolderName(rawInput)
      template = isUrl(rawInput) ? rawInput : "blank_template"
    }
    if (!this.isValidFolderName(folderName))
      return {
        errorMessage: `Sorry, your folder name "${folderName}" did not meet our requirements. It should start with a letter or number, be more than 1 character, and not end in a common file extension.`,
        folderName: rawInput
      }
    return {
      folderName,
      template,
      errorMessage: undefined
    }
  }

  async createFolderFromFiles(folderName, files) {
    const folderPath = path.join(this.rootFolder, folderName)
    await fsp.mkdir(folderPath, { recursive: true })
    for (const [filename, content] of Object.entries(files)) {
      const filePath = path.join(folderPath, filename)
      await fsp.mkdir(path.dirname(filePath), { recursive: true })
      await fsp.writeFile(filePath, content, "utf8")
    }
    await execAsync("git init", { cwd: folderPath })
    await execAsync("git add .", { cwd: folderPath })
    await execAsync('git commit -m "Initial commit"', { cwd: folderPath })
    await this.updateFolderAndBuildList(folderName)
  }

  // We support a lot of different strategies for creating a folder. Yeah, its a bit wierd. Probably should clean this up.
  async createFolder(rawInput) {
    const { folderCache } = this
    const { folderName, template, errorMessage } = this.makeFolderNameAndTemplateFromInput(rawInput, folderCache)
    if (errorMessage) return { errorMessage, folderName }

    if (folderCache[folderName]) return { errorMessage: `Sorry a folder named "${folderName}" already exists on this server.`, folderName: rawInput }

    const { rootFolder } = this
    if (isUrl(template)) {
      try {
        new URL(template)
      } catch (err) {
        return { errorMessage: `Invalid template url.`, folderName: rawInput }
      }
      const cloner = new CloneCli()
      await cloner.clone(rootFolder, template, folderName)
      await this.buildFolder(folderName)
    } else {
      await execAsync(`cp -R ${template} ${folderName};`, { cwd: rootFolder })
    }
    await this.updateFolderAndBuildList(folderName)

    return { folderName }
  }

  loadCert(certPath, hostname) {
    const keyPath = certPath.replace(/\.crt$/, ".key")

    // Check if both cert and key files exist
    if (fs.existsSync(certPath) && fs.existsSync(keyPath)) {
      const sslOptions = {
        cert: fs.readFileSync(certPath, "utf8"),
        key: fs.readFileSync(keyPath, "utf8")
      }
      this.certCache.set(hostname, sslOptions) // Cache the cert and key
      return sslOptions
    }
    return false
  }

  getMatchingWildcardCert(hostname) {
    const { wildCardCerts } = this
    // Check for matching wildcard certificate
    for (const wild of wildCardCerts) {
      if (wild.regex.test(hostname)) return wild.cert
    }
  }

  loadCertAndKey(hostname) {
    const { certCache, pendingCerts } = this
    if (certCache.has(hostname)) return certCache.get(hostname) // Return from cache if available

    const loadedCert = this.loadCert(this.makeCertPath(hostname), hostname)
    if (loadedCert) return loadedCert

    const wild = this.getMatchingWildcardCert(hostname)
    if (wild) return wild

    if (pendingCerts[hostname]) return
    this.makeCert(hostname)
    throw new Error(`SSL certificate or key not found for ${hostname}. Attempting to make cert.`)
  }

  async loadWildCardCerts() {
    const wildcards = this.config.getParticles("wildcard")
    if (!wildcards.length) return
    wildcards.forEach(wildcardConfig => {
      const [_, pattern, certFile, keyFile] = wildcardConfig.atoms
      const sslOptions = {
        cert: fs.readFileSync(certFile, "utf8"),
        key: fs.readFileSync(keyFile, "utf8")
      }
      // Convert wildcard pattern to regex
      // e.g., "*.example.com" becomes "^[^.]+\.example\.com$"
      const regexPattern = pattern
        .replace(/\./g, "\\.") // Escape dots
        .replace(/\*/g, "[^.]+") // Replace * with regex for non-dot chars
      const regex = new RegExp(`^${regexPattern}$`)

      this.wildCardCerts.push({ regex, pattern, cert: sslOptions })
    })
  }

  async startHttpsServer() {
    const { app, hubFolder } = this
    const tls = require("tls")
    const { CertificateMaker } = require("./CertificateMaker.js")
    const certMaker = new CertificateMaker(app).setupChallengeHandler()

    this.certCache = new Map()
    await this.loadWildCardCerts()

    const crtInHubFolder = (await fsp.readdir(hubFolder)).find(f => f.endsWith(".crt"))
    if (crtInHubFolder) {
      const hostname = crtInHubFolder.substr(1).replace(/\.crt$/, "")
      this.loadCert(path.join(hubFolder, crtInHubFolder), hostname)
    }

    const pendingCerts = {}
    this.pendingCerts = pendingCerts
    this.makeCert = async domain => {
      pendingCerts[domain] = true
      const email = domain + "@hub.scroll.pub"
      await certMaker.makeCertificate(domain, email, path.join(this.rootFolder, domain))
    }

    const that = this
    // Dynamic HTTPS server using SNI (Server Name Indication)
    const httpsServer = https.createServer(
      {
        SNICallback: (hostname, cb) => {
          try {
            const sslOptions = that.loadCertAndKey(hostname.toLowerCase())
            cb(null, tls.createSecureContext(sslOptions))
          } catch (err) {
            console.error(`No cert found for ${hostname}: ${err.message}`)
            cb(err)
          }
        }
      },
      app
    )

    httpsServer.listen(443, () => console.log("HTTPS server running on port 443"))
    return httpsServer
  }

  get isLocalHost() {
    const hostname = require("os").hostname().toLowerCase()
    if (/(localhost|macbook)/.test(hostname)) return true
    return false
  }

  async startHttpServer() {
    const { app } = this
    const startPort = this.port
    const maxPort = startPort + 100
    for (let port = startPort; port  {
          httpServer.on("error", err => {
            if (err.code === "EADDRINUSE") {
              console.log(`Port ${port} is busy, trying ${port + 1}...`)
              resolve(false)
            } else reject(err)
          })

          httpServer.listen(port, () => {
            console.log(`HTTP server running at http://localhost:${port}`)
            this.port = port // Store the actual bound port
            resolve(true)
          })
        }).then(success => {
          if (success) return httpServer
        })

        if (httpServer.listening) return httpServer
      } catch (err) {
        console.error(`Error trying port ${port}:`, err)
        if (port === maxPort) throw new Error(`Could not find an available port between ${startPort} and ${maxPort}`)
      }
    }
  }

  async stopServers() {
    if (!this.servers) return

    return Promise.all(
      this.servers.map(server => {
        return new Promise((resolve, reject) => {
          server.close(err => {
            if (err) reject(err)
            else resolve()
          })

          // Force-close connections that don't finish after timeout
          setTimeout(() => {
            server.closeAllConnections?.()
          }, 25000)
        })
      })
    )
  }
}

module.exports = { ScrollHub }

```
```public/scrollHubEditor.js
const getBaseUrlForFolder = (folderName, hostname, protocol) => {
  if (hostname === "localhost" || hostname.startsWith("localhost:")) return `http://${hostname}/${folderName}`

  if (!folderName.includes(".")) return protocol + "//" + hostname + "/" + folderName

  // now it might be a custom domain, serve it as if it is
  // of course, sometimes it would not be
  return protocol + "//" + folderName
}

const getCloneUrlForFolder = (folderName, hostname, protocol) => {
  if (hostname === "localhost" || hostname.startsWith("localhost:")) return `http://${hostname}/${folderName}.git`

  if (!folderName.includes(".")) return protocol + "//" + hostname + "/" + folderName + ".git"

  // now it might be a custom domain, serve it as if it is
  // of course, sometimes it would not be
  return protocol + "//" + folderName + "/" + folderName + ".git"
}

// todo: before unload warn about unsaved changes
class EditorApp {
  constructor() {
    this.folderName = ""
    this.previewIFrame = null
    this.initCodeMirror("custom")
    window.addEventListener("resize", () => this.updateEditorDimensions())

    // Add file filter input handler
    this.fileFilter = document.getElementById("fileFilter")
    this.fileFilter.addEventListener("input", () => {
      this.updateFilteredFileList()
      this.updateUrlWithFilter()
    })
    this.fusionEditor = new FusionEditor(AppConstants.parsers, this)
  }

  get editorHeight() {
    return this.isMobile ? 400 : Math.max(300, window.innerHeight - 200)
  }

  updateEditorDimensions() {
    const { editorHeight, isMobile } = this
    const fileListHeight = isMobile ? "auto" : `${editorHeight - 138}px`
    const fileListWidth = isMobile ? document.body.clientWidth - 40 + "px" : "200px"
    const fileList = document.getElementById("fileList")
    fileList.style.height = fileListHeight
    fileList.style.width = fileListWidth
    this.codeMirrorInstance.setSize(this.width, editorHeight)
    if (this.isFocusMode) {
      console.log("Entering focus mode")
      document.querySelector(".buttonRow").style.display = "none"
      document.querySelector(".editorHolder").classList.add("focusMode")
      const width = Math.min(800, document.body.clientWidth)
      this.codeMirrorInstance.setSize(width, window.innerHeight) // subtract 40 for padding
    }
  }

  get isMobile() {
    return window.innerWidth  {
      if (!document.fullscreenElement) this.exitFocusModeCommand()
    })
    this.disableAutocomplete()
    this.updateEditorDimensions()
    if (!this.codeMirrorInstance.hasFocus()) this.focusOnEnd()
  }

  getEditorMode(fileName) {
    const extension = fileName ? fileName.split(".").pop().toLowerCase() : ""
    const modeMap = {
      html: "htmlmixed",
      htm: "htmlmixed",
      js: "javascript",
      mjs: "javascript",
      json: "javascript",
      css: "css",
      py: "python",
      rb: "ruby",
      php: "php",
      perl: "perl",
      scroll: "custom",
      sh: "shell",
      parsers: "custom"
    }
    return modeMap[extension] || null
  }

  get parser() {
    return this.fusionEditor.customParser
  }

  initCodeMirror(mode) {
    const textarea = document.getElementById("fileEditor")

    if (this.codeMirrorInstance) this.codeMirrorInstance.toTextArea()

    if (mode === "custom") {
      // Use custom scroll parser mode with its autocomplete
      this.codeMirrorInstance = new ParsersCodeMirrorMode(mode, () => this.parser, undefined, CodeMirror).register().fromTextAreaWithAutocomplete(textarea, {
        lineWrapping: true,
        lineNumbers: false,
        mode
      })
    } else {
      // Use standard CodeMirror with appropriate mode and hint addons
      this.codeMirrorInstance = CodeMirror.fromTextArea(textarea, {
        lineWrapping: true,
        lineNumbers: false,
        mode
      })
    }

    this.codeMirrorInstance.on("keyup", () => this._onCodeKeyUp())

    this.updateEditorDimensions()
  }

  _onCodeKeyUp() {
    const code = this.codeMirrorInstance.getValue()
    if (this._code === code) return
    this._code = code
    // no-op at the moment
    // todo: save to local storage? autosave? other?
  }

  rehighlight() {
    if (this._parser === this.parser) return
    console.log("rehighlighting needed - reinitializing CodeMirror")
    this._parser = this.parser

    // Store current state
    const currentContent = this.codeMirrorInstance.getValue()
    const currentCursor = this.codeMirrorInstance.getCursor()
    const currentScrollInfo = this.codeMirrorInstance.getScrollInfo()

    // Completely reinitialize CodeMirror with current mode
    this.initCodeMirror(this.mode)

    // Restore content and cursor position
    this.codeMirrorInstance.setValue(currentContent)
    this.codeMirrorInstance.setCursor(currentCursor)

    // Restore scroll position
    this.codeMirrorInstance.scrollTo(currentScrollInfo.left, currentScrollInfo.top)
  }

  mode = "custom"
  autocomplete = true
  currentParser = null
  updateEditorMode(mode) {
    const modeChanged = mode !== this.mode
    if (!this.autocomplete) this.disableAutocomplete()
    else this.enableAutocomplete()
    if (!modeChanged && mode !== "custom") return
    if (!modeChanged && mode === "custom" && this.currentParser === this.parser) return
    console.log("Setting editor mode: " + mode)
    this.currentParser = this.parser
    const currentContent = this.codeMirrorInstance.getValue()
    this.initCodeMirror(mode)
    this.codeMirrorInstance.setValue(currentContent)
    this.mode = mode
  }

  toggleAutocompleteCommand() {
    this.autocomplete = !this.autocomplete
    if (this.autocomplete) this.enableAutocomplete()
    else this.disableAutocomplete()
  }

  disableAutocomplete() {
    this.autocomplete = false
    this.codeMirrorInstance.setOption("showHint", false)
    if (!this._hintOptions) this._hintOptions = this.codeMirrorInstance.getOption("hintOptions")
    this.codeMirrorInstance.setOption("hintOptions", { completeSingle: false })
  }

  enableAutocomplete() {
    if (this.autocomplete) return
    this.autocomplete = true
    this.codeMirrorInstance.setOption("showHint", true)
    this.codeMirrorInstance.setOption("hintOptions", this._hintOptions)
  }

  get bufferValue() {
    return this.codeMirrorInstance.getValue().replace(/\r/g, "")
  }

  showError(message) {
    console.error(message)
    this.fileListEl.innerHTML = `${message}`
  }

  get filePath() {
    return `${this.folderName}/${this.fileName}`
  }

  async main() {
    this.initTheme()
    this.bindFileListListeners()
    this.bindFileDrop()
    this.bindKeyboardShortcuts()

    const urlParams = new URL(window.location).searchParams
    this.openFolder(urlParams.get("folderName") || window.location.hostname)
    let fileName = urlParams.get("fileName") || ""
    if (fileName.startsWith("/")) {
      fileName = fileName.replace(/^\/+/, "")
      this.setFileNameInUrl(fileName) // strip leading slashes
    }

    // Set initial filter value from URL if present
    const filterValue = urlParams.get("filter") || ""
    this.fileFilter.value = filterValue

    if (!fileName) {
      let buffer = urlParams.get("buffer")
      if (buffer) {
        this.refreshFileListCommand()
        buffer = buffer.replace(/TODAYS_DATE/g, new Date().toLocaleDateString("en-US"))
        this.setFileContent(decodeURIComponent(buffer))
        await this.refreshParserCommand()
      } else {
        await this.refreshFileListCommand()
        await this.autoOpen()
        if (urlParams.get("command") === "showWelcomeMessageCommand") this.showWelcomeMessageCommand()
      }
    } else {
      this.refreshFileListCommand()
      this.openFile(fileName)
    }

    return this
  }

  updateUrlWithFilter() {
    const url = new URL(window.location)
    const filterValue = this.fileFilter.value.trim()

    if (filterValue) {
      url.searchParams.set("filter", filterValue)
    } else {
      url.searchParams.delete("filter")
    }

    window.history.replaceState(null, "", url)
  }

  setFileNameInUrl(fileName) {
    const url = new URL(window.location)
    const urlParams = url.searchParams
    urlParams.set("fileName", fileName)
    window.history.replaceState(null, "", url)
  }

  async autoOpen() {
    const { filenames } = this
    const lowerFilenames = new Set(filenames.map(f => f.toLowerCase()))
    const defaultFiles = ["index.scroll", "readme.scroll", "index.html", "readme.md", "package.json"]
    let file = filenames[0]
    for (let f of defaultFiles) {
      if (lowerFilenames.has(f)) {
        file = filenames.find(n => n.toLowerCase() === f)
        break
      }
    }
    await this.openFile(file)
  }

  async openFolder(folderName) {
    this.folderName = folderName
    this.updateFooterLinks()
  }

  async openFile(fileName) {
    const { folderName } = this
    this.fileName = fileName
    const filePath = `${folderName}/${fileName}`
    const response = await fetch(`/readFile.htm?folderName=${folderName}&filePath=${encodeURIComponent(filePath)}`)
    const content = await response.text()

    this.setFileContent(content)
    this.setFileNameInUrl(fileName)
    await this.refreshParserCommand()
    this.updateEditorMode(this.getEditorMode(fileName))
    this.updatePreviewIFrame()

    if (!this.allFiles) await this.refreshFileListCommand()
    else this.renderFileList()

    if (this.isModalOpen && this._openModal === "metrics") this.openMetricsCommand()
  }

  bindFileDrop() {
    const dropZone = document.getElementById("editForm")
    dropZone.addEventListener("dragover", this.handleDragOver.bind(this))
    dropZone.addEventListener("dragleave", this.handleDragLeave.bind(this))
    dropZone.addEventListener("drop", this.handleDrop.bind(this))
  }

  get permalink() {
    const dir = this.rootUrl.replace(/\/$/, "") + "/"
    const { fileName } = this
    if (!fileName.endsWith(".scroll")) return dir + fileName
    const { outputFileNames } = this.fusionEditor.mainProgram
    const primaryOutputFile = outputFileNames.find(name => name.endsWith(".html")) || outputFileNames[0]
    if (!primaryOutputFile) return dir + fileName
    const path = fileName.split("/")
    if (path.length === 1) return dir + primaryOutputFile
    path.pop()
    return dir + path.join("/") + "/" + primaryOutputFile
  }

  showSpinner(message, style) {
    document.querySelector("#spinner").innerHTML = `${message}`
    document.querySelector("#spinner").style.display = "block"
  }

  showSpinnerWithStopwatch(message, style) {
    this.showSpinner(message, style)
    let count = 1
    this.spinnerInterval = setInterval(() => (document.querySelector("#spinner").innerHTML = `${message} - ${count++}s`), 1000)
    document.querySelector("#spinner").style.display = "block"
  }

  showError(message) {
    clearInterval(this.spinnerInterval)
    this.showSpinner(message, ` style="color:red;"`)
  }

  hideSpinner() {
    document.querySelector("#spinner").style.display = "none"
    clearInterval(this.spinnerInterval)
  }

  async saveFile() {
    if (!this.fileName) {
      const name = new URL(window.location).searchParams.get("bufferName") || "untitled"
      let fileName = this.sanitizeFileName(prompt("Enter a filename", name))
      if (!fileName) return ""
      this.fileName = fileName
    }
    await this.writeFile("Publishing...", this.bufferValue, this.fileName)
    await this.refreshParserCommand()
    this.updatePreviewIFrame()
  }

  async writeFile(spinnerText, content, fileName) {
    const { folderName } = this
    const filePath = `${folderName}/${fileName}`
    this.showSpinner(spinnerText)
    const formData = new FormData()
    formData.append("filePath", filePath)
    formData.append("folderName", folderName)
    formData.append("content", content)
    try {
      const response = await fetch("/writeFile.htm", {
        method: "POST",
        body: formData
      })
      this.hideSpinner()
      await this.refreshFileListCommand()
      if (this.fileName !== fileName) this.openFile(fileName)
      this.buildFolderCommand()
    } catch (error) {
      console.error("Error duplicating file:", error)
      this.showError(error.message)
    }
  }

  async buildFolderCommand() {
    const formData = new FormData()
    const { folderName } = this
    formData.append("folderName", folderName)
    const response = await fetch("/build.htm", {
      method: "POST",
      body: formData
    })
    const message = await response.text()
    if (!response.ok) {
      console.error(message)
      this.showError(message.message?.split(".")[0] || "Error building folder.")
      return false
    } else if (message.includes("SyntaxError")) {
      this.showError("There may have been an error building your site. Please check console logs.")
      console.error(message)
      return false
    }

    console.log(`'${folderName}' built`)
    return true
  }

  async buildFolderAndRefreshCommand() {
    this.showSpinnerWithStopwatch("Building")
    const result = await this.buildFolderCommand()
    if (!result) return false
    await this.refreshFileListCommand()
    this.hideSpinner()
  }

  async saveAndPublishCommand() {
    await this.saveFile()
    await this.refreshFileListCommand()
    await this.buildFolderCommand()
  }

  async refreshParserCommand() {
    await this.fusionEditor.buildMainProgram()
    console.log("Parser refreshed")
    this.rehighlight()
  }

  toggleHelpCommand(event) {
    if (this._openModal === "help") this.closeHelpModalCommand()
    else this.openHelpModalCommand(event)
  }

  closeHelpModalCommand() {
    this.closeModal()
  }

  _modalContent
  openModal(content, modalName, event) {
    document.querySelector("#theModal").classList.remove("scrollModalFit")
    this._openModal = modalName
    if (!this._modalContent) this._modalContent = document.querySelector("#theModal").innerHTML
    document.querySelector("#theModal").innerHTML = this._modalContent + content
    openModal("theModal", event)
  }

  get isModalOpen() {
    return document.querySelector("#theModal").style.display === "block"
  }

  closeModal() {
    if (this.isModalOpen) closeModal(document.querySelector("#theModal"))
    delete this._openModal
  }

  get metrics() {
    // Calculate document metrics
    const content = this.bufferValue
    const words = (content.match(/\S+/g) || []).filter(word => !/[.]\w+[(]|[[\]{}()]|[.]\w+$|[@]|[;\|\#\`,=+\-*/%]/.test(word))
    const chars = content.length
    const sentences = content.split(/[.!?]+\s+/).filter(s => s.trim().length > 0)
    const readingTimeMinutes = Math.max(1, Math.ceil(words.length / 200))

    // Calculate average word length
    const avgWordLength = words.length ? (words.join("").length / words.length).toFixed(1) : 0

    // Count unique words
    const uniqueWords = new Set(words.map(w => w.toLowerCase().replace(/[.,!?]$/, ""))).size

    return `
    
      Document Metrics
      Sentences:${sentences.length}
      Words:${words.length}
      Characters:${chars}
      Average Word Length:${avgWordLength}
      Unique Words:${uniqueWords}
      Reading Time:${readingTimeMinutes} min
      
    `
  }

  openMetricsCommand(event) {
    this.openModal(this.metrics, "metrics", event)
  }

  toggleMetricsCommand(event) {
    if (this._openModal === "metrics") this.closeModal()
    else this.openMetricsCommand(event)
  }

  openHelpModalCommand(event) {
    const { keyboardShortcuts } = this
    // Group shortcuts by category
    const shortcutsByCategory = lodash.groupBy(keyboardShortcuts, "category")

    // Generate HTML for each category
    const categoryElements = Object.entries(shortcutsByCategory)
      .map(([category, shortcuts]) => {
        if (category === "Hidden") return ""
        const shortcutElements = shortcuts
          .map(shortcut => {
            const command = shortcut.command
            const description = lodash.startCase(command.replace("Command", ""))
            const keyStr = shortcut.key.startsWith("nokey") ? "&nbsp;" : shortcut.key.replace("command", "cmd")
            return `
            
              ${keyStr} ${description}
            
          `
          })
          .join("")

        return `
          
            ${category}
              ${shortcutElements}
          
        `
      })
      .join("")

    this.openModal(
      `
      
        Keyboard Shortcuts
        
        ${categoryElements}
        
          
            ScrollHub Community: 
            GitHub · 
            Twitter · 
            YouTube · 
            Reddit
          
      
    `,
      "help",
      event
    )
  }

  nextFileCommand() {
    const { scrollFiles } = this
    const currentIndex = scrollFiles.indexOf(this.fileName)
    const nextIndex = (currentIndex + 1) % scrollFiles.length
    console.log(nextIndex)
    this.openFile(scrollFiles[nextIndex])
  }

  previousFileCommand() {
    const { scrollFiles } = this
    const currentIndex = scrollFiles.indexOf(this.fileName)
    const prevIndex = (currentIndex - 1 + scrollFiles.length) % scrollFiles.length
    this.openFile(scrollFiles[prevIndex])
  }

  keyboardShortcuts = Object.values(
    Particle.fromSsv(
      `key command category
command+s saveAndPublishCommand File
ctrl+n createFileCommand File
command+p formatFileCommand File
command+h showFileHistoryCommand File
command+b buildFolderAndRefreshCommand Folder
nokey2 exportForPromptCommand Folder
command+. toggleFocusModeCommand Editor
shift+t toggleThemeCommand Editor
ctrl+p refreshParserCommand Editor
command+3 toggleMetricsCommand Editor
command+shift+h showHiddenFilesCommand Editor
command+1 previousFileCommand Navigation
command+2 nextFileCommand Navigation
command+/ toggleHelpCommand Hidden
? toggleHelpCommand Help
nokey1 showWelcomeMessageCommand Help`
    ).toObject()
  )

  initTheme() {
    document.documentElement.setAttribute("data-theme", this.theme)
  }

  get theme() {
    return localStorage.getItem("editorTheme") || "light"
  }

  toggleThemeCommand() {
    const newTheme = this.theme === "light" ? "dark" : "light"
    document.documentElement.setAttribute("data-theme", newTheme)
    localStorage.setItem("editorTheme", newTheme)
  }

  showHiddenFilesCommand() {
    this.showHiddenFiles = !this.showHiddenFiles
    delete this._files
    this.renderFileList()
  }

  bindKeyboardShortcuts() {
    const keyboardShortcuts = this.keyboardShortcuts.filter(key => !key.key.startsWith("nokey"))
    const map = {}
    keyboardShortcuts.forEach(row => (map[row.key] = row.command))
    const that = this
    // note: I do not rememeber why we do any of this stopCallback stuff but it seems hard won knowledge ;)
    Mousetrap._originalStopCallback = Mousetrap.prototype.stopCallback
    Mousetrap.prototype.stopCallback = async function (evt, element, keyPress) {
      if (map[keyPress] && (!that.codeMirrorInstance.hasFocus() || keyPress.startsWith("command"))) {
        that[map[keyPress]]()
        evt.preventDefault()
        return true
      }

      if (Mousetrap._pause) return true
      return Mousetrap._originalStopCallback.call(this, evt, element)
    }

    keyboardShortcuts.forEach(shortcut => {
      Mousetrap.bind(shortcut.key, function (evt) {
        that[shortcut.command]()
        // todo: handle the below when we need to
        if (evt.preventDefault) evt.preventDefault()
        return false
      })
    })
  }

  handleDragOver(event) {
    event.preventDefault()
    event.stopPropagation()
    event.currentTarget.classList.add("drag-over")
  }

  handleDragLeave(event) {
    event.preventDefault()
    event.stopPropagation()
    event.currentTarget.classList.remove("drag-over")
  }

  async handleDrop(event) {
    event.preventDefault()
    event.stopPropagation()
    event.currentTarget.classList.remove("drag-over")
    const files = event.dataTransfer.files
    if (files.length) {
      this.showSpinner(`Uploading ${files.length} files...`)
      await this.uploadFiles(files)
      this.hideSpinner()
      return
    }
    const html = event.dataTransfer.getData("text/html")
    if (html) {
      // Create a temporary DOM element to parse the HTML
      const div = document.createElement("div")
      div.innerHTML = html

      // Find the image element
      const img = div.querySelector("img")
      if (img) {
        const url = img.src
        const filename = this.getFilenameFromUrl(url)
        await this.handleImageUrl(url, filename)
      }
    }
  }

  async exportForPromptCommand(event) {
    this.openIframeModal("/stamp?folderName=" + this.folderName, event)
  }

  async showWelcomeMessageCommand(event) {
    let content = `container 600px

# Welcome to ScrollHub!

center
${this.folderName} is live!

center
Visit ${this.folderName}
 link ${this.permalink}
  target preview
 class newSiteLink

We make Scroll and ScrollHub to help you refine and publish your best ideas.

I'd love to hear your requests and feedback! Contact me on X, GitHub, or email.
 https://x.com/breckyunits X
  target _blank
 email breck@scroll.pub email
  target _blank
 https://github.com/breck7 GitHub
  target _blank

-Breck`
    if (new URL(window.location).searchParams.get("welcomeMessage") === "framehub") {
      content = `container 600px

# Welcome to FrameHub!

center
${this.folderName} is live!

center
Visit ${this.folderName}
 link ${this.permalink}
  target preview
 class newSiteLink

I'd love to hear your requests and feedback! Find me on Warpcast.
 https://warpcast.com/breck Find me on Warpcast

-Breck`
    }

    const html = await this.fusionEditor.scrollToHtml(content)
    this.openModal(html, "welcome", event)
    document.querySelector("#theModal").classList.add("scrollModalFit")
  }

  async showFileHistoryCommand(event) {
    if (!this.fileName) return

    try {
      this.showSpinner("Loading file history...")
      const response = await fetch(`/blame.htm?folderName=${this.folderName}&fileName=${encodeURIComponent(this.fileName)}`)

      if (!response.ok) {
        throw new Error("Failed to fetch file history")
      }

      const history = await response.text()

      // Format the history data into HTML
      const formattedHistory = `
        
          File History: ${this.fileName}
          ${history}
        
      `

      this.openModal(formattedHistory, "history", event)
      this.hideSpinner()
    } catch (error) {
      console.error("Error fetching file history:", error)
      this.showError("Failed to load file history: " + error.message)
      setTimeout(() => this.hideSpinner(), 3000)
    }
  }

  getFilenameFromUrl(url) {
    try {
      const urlObj = new URL(url)
      const pathname = urlObj.pathname
      // Get the last segment of the path and decode it
      let filename = decodeURIComponent(pathname.split("/").pop())
      // If no extension, try to get it from the Content-Type
      if (!filename.includes(".")) {
        return null // Let the Content-Type determine it later
      }
      return filename
    } catch {
      return null
    }
  }

  async handleImageUrl(url, preferredFilename) {
    try {
      const response = await fetch(url)
      const contentType = response.headers.get("Content-Type")
      const blob = await response.blob()

      // If we don't have a filename or it doesn't have an extension,
      // create one from the Content-Type
      let filename = preferredFilename
      if (!filename) {
        const ext = contentType.split("/")[1]
        filename = `image.${ext}`
      }

      const file = new File([blob], filename, { type: contentType })
      await this.uploadFiles([file])
    } catch (error) {
      console.error("Error handling image URL:", error)
    }
  }

  // New method to handle multiple file uploads
  async uploadFiles(files) {
    const uploadPromises = Array.from(files).map(file => this.uploadFile(file))

    Promise.all(uploadPromises)
      .then(() => {
        console.log("All files uploaded successfully")
        this.refreshFileListCommand()
        this.buildFolderCommand()
      })
      .catch(error => {
        console.error("Error uploading files:", error)
        // todo: show error to user
        alert("Error uploading files:" + error)
      })
  }

  // Modified uploadFile method to return a Promise
  async uploadFile(file) {
    const formData = new FormData()
    formData.append("file", file)
    formData.append("folderName", this.folderName)

    try {
      const response = await fetch("/uploadFile.htm", {
        method: "POST",
        body: formData
      })

      if (!response.ok) {
        const errorText = await response.text()
        throw new Error(errorText || "Network response was not ok")
      }

      const data = await response.text()
      console.log("File uploaded successfully:", data)
      return data
    } catch (error) {
      console.error("Error uploading file:", error.message)
      throw error // Re-throw the error if you want calling code to handle it
    }
  }

  get hostnameWithPort() {
    const hostname = window.location.hostname
    const port = window.location.port
    if (!port || port === 80 || port === 443) return hostname
    return hostname + ":" + port
  }

  get rootUrl() {
    const protocol = this.useSsl ? window.location.protocol : "http:"
    return getBaseUrlForFolder(this.folderName, this.hostnameWithPort, protocol)
  }

  updatePreviewIFrame() {
    const { rootUrl, folderName } = this
    this.previewIFrame = document.querySelector(".previewIFrame")
    this.previewIFrame.src = this.permalink

    this.updateVisitLink()
    document.title = `Editing ${folderName}`
  }

  updateVisitLink() {
    const { permalink, fileName } = this
    const text = permalink.replace(/\/index.html$/, "")
    document.getElementById("folderNameLink").innerHTML = text
    document.getElementById("folderNameLink").href = permalink
  }

  get cloneUrl() {
    const protocol = this.useSsl ? window.location.protocol : "http:"
    return getCloneUrlForFolder(this.folderName, this.hostnameWithPort, protocol)
  }

  copyClone() {
    // Create a temporary textarea element
    const textarea = document.createElement("textarea")
    textarea.value = `git clone ` + this.cloneUrl
    document.body.appendChild(textarea)

    // Select and copy the text
    textarea.select()
    document.execCommand("copy")

    // Clean up by removing the textarea
    document.body.removeChild(textarea)

    this.showSpinner("Git clone command copied to clipboard...")
    setTimeout(() => this.hideSpinner(), 3000)
  }

  openIframeModalFromClick(event) {
    this.openIframeModal(event.currentTarget.href, event)
  }

  openIframeModal(url, event) {
    const { folderName } = this
    const modalContent = `
        
  `
    this.openModal(modalContent, url, event)
  }

  // Update the updateFooterLinks method to use the new modal
  updateFooterLinks() {
    const { folderName } = this
    document.getElementById("folderLinks").innerHTML =
      `traffic · revisions · clone · download · duplicate · move · delete`
  }

  async renameFolder() {
    const newFolderName = prompt(`Rename ${this.folderName} to:`)
    if (!newFolderName) return
    const response = await fetch("/mv.htm", {
      method: "POST",
      headers: {
        "Content-Type": "application/x-www-form-urlencoded"
      },
      body: `oldFolderName=${this.folderName}&newFolderName=${newFolderName}`
    })

    const result = await response.text()
    window.location.href = `/edit.html?folderName=${newFolderName}`
  }

  async deleteFolder() {
    const userInput = prompt(`To delete this entire folder, please type the folder name: ${this.folderName}`)

    if (userInput !== this.folderName) return

    try {
      const response = await fetch("/trashFolder.htm", {
        method: "POST",
        headers: {
          "Content-Type": "application/x-www-form-urlencoded"
        },
        body: `folderName=${encodeURIComponent(this.folderName)}`
      })

      const data = await response.text()
      console.log(data)
      window.location.href = "/" // Redirect to home page after deletion
    } catch (error) {
      console.error("Error:", error)
    }
  }

  async duplicate() {
    this.showSpinner("Copying folder...")
    const response = await fetch("/cloneFolder.htm", {
      method: "POST",
      headers: {
        "Content-Type": "application/x-www-form-urlencoded"
      },
      body: `folderName=${this.folderName}&redirect=false`
    })

    const result = await response.text()
    this.hideSpinner()
    console.log(result)
    window.location.href = `/edit.html?folderName=${result}`
  }

  useSsl = window.location.protocol === "https:"

  showHiddenFiles = false
  get files() {
    if (this._files) return this._files
    const { allFiles, showHiddenFiles } = this
    const filtered = {}
    Object.keys(allFiles).forEach(key => {
      const value = allFiles[key]
      if (showHiddenFiles || value.tracked || !key.startsWith(".")) filtered[key] = value
    })

    this._files = filtered
    return this._files
  }

  async refreshFileListCommand() {
    const { folderName } = this
    try {
      const response = await fetch(`/ls.json?folderName=${folderName}`)
      if (!response.ok) throw new Error(await response.text())
      const allData = await response.json()
      const allFiles = allData.files
      delete this._files
      this.allFiles = allFiles
      this.useSsl = allData.hasSslCert
      this.renderFileList()
    } catch (error) {
      console.error("There was a problem with the fetch operation:", error.message)
    }
  }

  get filenames() {
    return Object.keys(this.files)
  }

  get scrollFiles() {
    return this.filenames.filter(file => file.endsWith(".scroll") || file.endsWith(".parsers"))
  }

  renderFileList() {
    const { files, filenames, folderName } = this
    const currentFileName = this.fileName
    const filterValue = this.fileFilter.value.toLowerCase()

    // Filter files based on search input
    const filteredFiles = filenames.filter(file => file.toLowerCase().includes(filterValue))

    // Sort files: .scroll and .parsers first, then others
    const scrollFiles = filteredFiles.filter(file => file.endsWith(".scroll") || file.endsWith(".parsers"))
    const sorted = scrollFiles.concat(filteredFiles.filter(file => !file.endsWith(".scroll") && !file.endsWith(".parsers")))

    const fileLinks = sorted.map(file => {
      const stats = files[file]
      const selected = currentFileName === file ? "selectedFile" : ""
      const isScrollFile = file.endsWith(".scroll") || file.endsWith(".parsers")
      const isTrackedByGit = stats.versioned ? "" : " untracked"
      return `${file}`
    })

    this.fileListEl.innerHTML = fileLinks.join("")
  }

  updateFilteredFileList() {
    this.renderFileList()
  }

  bindFileListListeners() {
    this.fileListEl.addEventListener("click", event => {
      if (event.metaKey || event.ctrlKey) return true
      const link = event.target.closest("a")
      if (!link) return true
      event.preventDefault()

      if (event.shiftKey) this.maybeRenameFilePrompt(link.textContent, event)
      else this.openFile(link.textContent)
    })
  }

  get fileListEl() {
    return document.getElementById("fileList")
  }

  maybeRenameFilePrompt(oldFileName, event) {
    const newFileName = prompt(`Enter new name for "${oldFileName}":`, oldFileName)
    if (newFileName && newFileName !== oldFileName) {
      this.performFileRename(oldFileName, this.sanitizeFileName(newFileName))
    }
  }

  async performFileRename(oldFileName, newFileName) {
    const { folderName } = this
    try {
      this.showSpinner("Renaming..")
      const response = await fetch("/renameFile.htm", {
        method: "POST",
        headers: {
          "Content-Type": "application/x-www-form-urlencoded"
        },
        body: `folderName=${encodeURIComponent(folderName)}&oldFileName=${encodeURIComponent(oldFileName)}&newFileName=${encodeURIComponent(newFileName)}`
      })

      if (!response.ok) throw new Error(await response.text())

      this.hideSpinner()
      console.log(`File renamed from ${oldFileName} to ${newFileName}`)
      this.refreshFileListCommand()
      this.buildFolderCommand()

      // If the renamed file was the current file, open the new file
      if (this.fileName === oldFileName) this.openFile(newFileName)
    } catch (error) {
      console.error(error)
      alert("Rename error:" + error)
    }
  }

  sanitizeFileName(fileName) {
    if (fileName === undefined || fileName === null) return ""
    // Dont allow spaces in filenames. And if no extension, auto add .scroll.
    return (fileName.includes(".") ? fileName : fileName + ".scroll").replace(/ /g, "")
  }

  async createFileCommand() {
    let fileName = this.sanitizeFileName(prompt("Enter a filename", "untitled"))
    if (!fileName) return ""
    await this.writeFile("Creating file...", "", fileName)
  }

  _isFirstOpen = true
  setFileContent(value) {
    document.getElementById("fileEditor").value = value.replace(/\r/g, "")
    this.codeMirrorInstance.setValue(value)
    const lines = value.split("\n")
    // if its a small file, put user right in editing experience
    if (lines.length  {
  window.app = new EditorApp()
  window.app.main()
})

```
