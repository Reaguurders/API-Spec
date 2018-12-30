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
### top5
#### dag
GET: https://api.dumpert.nl/mobile_api/json/dag/top5/{DATE}

| Parameter | Format | Function | Example |
|----------|----------|----------|----------|
|'{DATE}' | YYYY-mm-dd | Get the top videos of the given date (YYYY-mm-dd), {DATE}.|`https://api.dumpert.nl/mobile_api/json/dag/top5/2018-12-30`|

#### week
GET: https://api.dumpert.nl/mobile_api/json/week/top5/{DATE}

| Parameter | Format | Function | Example |
|----------|----------|----------|----------|
|'{DATE}' | YYYYww | Get the top videos of the given week (ww) in the year (YYYY), {DATE}.|`https://api.dumpert.nl/mobile_api/json/week/top5/201852`|

#### maand
GET: https://api.dumpert.nl/mobile_api/json/maand/top5/{DATE}

| Parameter | Format | Function | Example |
|----------|----------|----------|----------|
|'{DATE}' | YYYYmm | Get the top videos of the given month (mm) in the year (YYYY), {DATE}.|`https://api.dumpert.nl/mobile_api/json/week/top5/201852`|

### latest
GET: https://api.dumpert.nl/mobile_api/json/latest/{INT}

| Parameter | Format | Function | Example |
|----------|----------|----------|----------|
|'{INT}' | int (0-11457) | Get the latest videos that have been uploaded on page {INT}.|`https://api.dumpert.nl/mobile_api/json/latest/0`|
Note: The max value of 11457 will change overtime if more videos have been uploaded


