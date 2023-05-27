#acunetix-api
Use https://github.com/jenkinsci/acunetix-plugin/blob/master/src/main/java/com/acunetix/Engine.java

The api provided in it is rewritten from

Globally depends on the obtained api-key
```
headers = {"X-Auth":apikey,"content-type": "application/json"}
```
1. Add task
```
post /api/v1/targets

data = {"address":url,"description":url,"criticality":"10"}
```
2. Scan task
```
post /api/v1/scans

data = {"target_id":target_id,"profile_id":"11111111-1111-1111-1111-111111111111","schedule": {"disable": False,"start_date":None,"time_sensitive": False}}
```
target_id is the result returned by adding the task in the first step


3. Get task summary
```
get /api/v1/scans
```
4. Get task details
```
get /api/v1/scans/+scan_id
```
5. Generate report
```
post /api/v1/reports

data = {"template_id":"11111111-1111-1111-1111-111111111111","source":{"list_type":"scans","id_list":[scan_id]}}
```
6. Stop scanning
```
POST /scans/" + scanId + "/abort
```
7. Delete scan
```
DELETE /api/v1/scans/+scan_id
```
Details reference

http://0cx.cc/about_awvs11_api.jspx#   a c u n e t i x - a p i  
 