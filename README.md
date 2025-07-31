import requests
API_KEY = 'YOUR_API_KEY'
LOCATION = '22.5726,88.3639'
RADIUS = 1000
TYPE = 'restaurant'
url= f"https://maps.googleapis.com/maps/api/place/nearbysearch/json?location={LOCATION}&radius={RADIUS}&type={TYPE}&key={API_KEY}"
response = requests.get(url)
data= response.json()
for i,place in enumerate(data['results'],1):
    name = place.get('name')
    address= place.get('vicinity')
    rating = place.get('ratings')
    print(f"{i}.{name}\n address:{address}\n rating:{rating}\n")
    
