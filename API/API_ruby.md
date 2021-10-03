### API call for Ruby

#### Example - Weather API :

```
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://community-open-weather-map.p.rapidapi.com/weather?q=London%2Cuk&lat=0&lon=0&callback=test&id=2172797&lang=null&units=imperial&mode=xml")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["x-rapidapi-host"] = 'community-open-weather-map.p.rapidapi.com'
request["x-rapidapi-key"] = 'xxxxxxxx'

response = http.request(request)
puts response.read_body
```
```
# Output in command line:

test({"coord":{"lon":-0.1257,"lat":51.5085},"weather":[{"id":803,"main":"Clouds","description":"broken clouds","icon":"04d"}],"base":"stations","main":{"temp":57.2,"feels_like":56.28,"temp_min":54.36,"temp_max":59.11,"pressure":1003,"humidity":78},"visibility":10000,"wind":{"speed":12.66,"deg":230},"clouds":{"all":75},"dt":1633281444,"sys":{"type":2,"id":2019646,"country":"GB","sunrise":1633241064,"sunset":1633282464},"timezone":3600,"id":2643743,"name":"London","cod":200})
```