import urllib.request, json

endpoint = 'https://maps.googleapis.com/maps/api/directions/json?'
api_key = 'AIzaSyCF8tXYrAZpxLZnwakBLTUgc2wGP0aH0tw'

origin = input('What is your current location?: ').replace(' ','+')

f = open('location.txt','r')
x = f.read()
x = x.replace("\n",'')

print (x)

destination = x.replace(' ', '+')
print (destination)

nav_request = 'origin={}&destination={}&key={}'.format(origin,destination,api_key)
print(nav_request)
request = endpoint + nav_request

response = urllib.request.urlopen(request).read()

directions = json.loads(response)
print(directions)
