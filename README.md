# sesame
DIY door opener

## Possible Parts
- http://www.adafruit.com/products/1697
- http://www.adafruit.com/products/2487

## Pieces
- Controller to accept BLE authentication
- Actuator to open door
- Protocol to authenticate
- Mechanism to pair phone and opener
- iOS app
- android app

## Protocol
### Pairing
A button on the device and the app must be open (while open app is activley scanning). App confirms. Pairing also records location to use for increasing scan frequency when inactive.

Public key of app is recorded by opener.

### Opening
The door is opened when the phone is close to the door. Similar to a badge, but it would be more useable if the phone could say in your pocket or bag.

When the app is open it is actively scanning for openers.

When app is closed scanning can be triggerd by a combination of:
- location (i.e. close to known opener)
- motion (phone taken out of pocket and held to door)
- time window (typical time opener is trigggered)
- polling (simply try to connect every 10-30 seconds)

Depending on energy impact of a poll every 10-30 seconds the phone may be able to detect the opener while the user is
walking to the door. In this case the poll frequency can be increased such that when the target distance is reached there
is no preceived latency.

## Open questions
- How does locking work without draining phone power while in the office?
- How to prevent energy drain when the door remains in close proximity after opening (i.e. small locked office)

## Possible features
- Allow someone access by sharing key from one phone to another without physical access to lock.
- Administer lock access from phone
- Physicall reset of lock access
