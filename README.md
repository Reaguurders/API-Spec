# API-Spec
The Dumpert.nl API documented (all the info that is known)

## Most important API Features summed up
* Getting the current day toppers
* Search API to find videos
* Getting latest uploaded video
* Getting video info
* Getting comment info

# API Endpoint
Dumpert has two API endpoints, one for video related info and one for getting comment info.
API Endpoint (Video-related): https://api.dumpert.nl/mobile_api/json/
API Endpoint (Comment-related): https://comments.dumpert.nl/api/v1.0/

## Video
The main endpoint for videos is: https://api.dumpert.nl/mobile_api/json/

### top5
#### dag
GET: https://api.dumpert.nl/mobile_api/json/top5/dag/{DATE}  
Purpose: Get the top videos of the given date (YYYY-mm-dd), {DATE}.

| Parameter | Format | Example |
|----------|----------|----------|
|'{DATE}'|YYYY-mm-dd|`https://api.dumpert.nl/mobile_api/json/top5/dag/2018-12-30`|

#### week
GET: https://api.dumpert.nl/mobile_api/json/top5/week/{DATE}  
Purpose: Get the top videos of the given week (ww) in the year (YYYY), {DATE}.

| Parameter | Format | Example |
|----------|----------|----------|
|'{DATE}' | YYYYww |`https://api.dumpert.nl/mobile_api/json/top5/week/201852`|

#### maand
GET: https://api.dumpert.nl/mobile_api/json/top5/maand/{DATE}  
Purpose: Get the top videos of the given month (mm) in the year (YYYY), {DATE}.

| Parameter | Format | Example |
|----------|----------|----------|
|'{DATE}'|YYYYmm|`https://api.dumpert.nl/mobile_api/json/top5/maand/201812`|

---

### latest
#### latest
GET: https://api.dumpert.nl/mobile_api/json/latest/{Page}  
Purpose: Get the latest videos that have been uploaded, on page {Page}.

| Parameter | Format | Example |
|----------|----------|----------|
|'{Page}'|int (0-11457)|`https://api.dumpert.nl/mobile_api/json/latest/0`|

Note: The max value of 11457 will change overtime if more videos have been uploaded

---

### classics
#### classics
GET: https://api.dumpert.nl/mobile_api/json/classics/{Page}  
Purpose: Get the latest 'classic' videos (from the app) that have been uploaded, on page {Page}.

| Parameter | Format | Example |
|----------|----------|----------|
|'{Page}'|int|`https://api.dumpert.nl/mobile_api/json/classics/0`|

---

### related
#### related
GET: https://api.dumpert.nl/mobile_api/json/related/{DumpertID}  
Purpose: Get videos that are related to the video {DumpertID}.

| Parameter | Format | Example |
|----------|----------|----------|
|'{DumpertID}'|Dumpert ID, underscore|`https://api.dumpert.nl/mobile_api/json/related/6693587_7ea8097a`|

---

### rating
#### rating
GET: https://api.dumpert.nl/mobile_api/json/rating/{DumpertID}/{UpDown}  
Purpose: {UpDown} the kudos of video {DumpertID}.

| Parameter | Format | Example |
|----------|----------|----------|
|'{DumpertID}' |Dumpert ID, underscore|`https://api.dumpert.nl/mobile_api/json/rating/6693587_7ea8097a/{UpDown}`|
|'{UpDown}'|up|`https://api.dumpert.nl/mobile_api/json/rating/6693587_7ea8097a/up`|
|'{UpDown}'|down|`https://api.dumpert.nl/mobile_api/json/rating/6742636_13351bf3/down`|

---

### info
#### info
GET: https://api.dumpert.nl/mobile_api/json/info/{DumpertID}  
Purpose: Get the info from a video, like title, id, description, date, views, kudos, media url.

| Parameter | Format | Example |
|----------|----------|----------|
|'{DumpertID}'|Dumpert ID, underscore|`https://api.dumpert.nl/mobile_api/json/info/6693587_7ea8097a`|

---

### search
#### {SearchString}
GET: https://api.dumpert.nl/mobile_api/json/search/{SearchString}/{Page}  
Purpose: Search videos using a string, and get page {Page} of the results.

| Parameter | Format | Example |
|----------|----------|----------|
|'{SearchString}'|string|`https://api.dumpert.nl/mobile_api/json/search/keiglad/{Page}`|
|'{Page}'|int|`https://api.dumpert.nl/mobile_api/json/search/keiglad/1`|

---

### dumperttv
GET: https://api.dumpert.nl/mobile_api/json/dumperttv  
Purpose: Get the latest Dumpert TV videos.

---

### hotshiz
GET: https://api.dumpert.nl/mobile_api/json/hotshiz  
Purpose: Get the latest 'hotshiz'(?) videos.  
Note: It is unknown on what hotshiz is based.

## Comments
The main endpoint for comments is: https://comments.dumpert.nl/api/v1.0/

### articles
#### {DumpertID}
GET: https://comments.dumpert.nl/api/v1.0/articles/{DumpertID}/comments/?includeitems={01}
Purpose: Get all the comments, or comment count, of a {DumpertID}, this also gives comment ids, which are used by the /comments/ endpoint.
Includeitems determines if the comments should be included, else you only get stats of the comments of the {DumpertID}

| Parameter | Format | Example |
|----------|----------|----------|
|'{DumpertID}'|Dumpert ID, slash|`https://comments.dumpert.nl/api/v1.0/articles/7590061/1a3188c7/comments/?includeitems={01}`|
|'{01}'|0 or 1|`https://comments.dumpert.nl/api/v1.0/articles/7590061/1a3188c7/comments/?includeitems=1`|

### comments
#### {CommentID}
GET: https://comments.dumpert.nl/api/v1.0/comments/{CommentID}/
Purpose: Get all data of a comment id like, DumpertID, title, auther, comment, time, banned, kudos, childern, reported, parent.

| Parameter | Format | Example |
|----------|----------|----------|
|'{CommentID}'|Comment ID|`https://comments.dumpert.nl/api/v1.0/comments/49136/`|
