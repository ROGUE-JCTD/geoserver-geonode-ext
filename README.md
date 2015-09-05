building geoserver 2.6 for mapstory
=============================================
Do run the tests when appropriate:
 
use the build/build.sh script to build the gs with the proper dependancies. You should rebase custome commits to geoserver and geotools on top of latest 2.6.x and 12.x branches correspondingly. 


geoserver-geonode-ext
=====================

GeoNode extends GeoServer with certain JSON, REST, and security capabilities.

Security
--------

GeoServer delegates authentication and authorization to GeoNode.

When the GeoServer plugin sees a request, it attempts to authorize with
GeoNode:

- If the request has a valid `sessionid` cookie (this links to a user in
  GeoNode), GeoNode looks up the user's permissions and replies.

- If there are HTTP credentials in the request (via the `HTTP_AUTHORIZATION`
  header) and they match those configured in the `OGC_SETTINGS`,
  GeoNode replies that this user is a super-user.

- **Uploads** is a special case: here, GeoNode makes the original request
  using the `OGC_SETTINGS` credentials.

JSON
----

TODO

.. todo:: Document GeoServer GeoJSON extensions

REST
----

TODO

.. todo:: Document GeoServer REST extensions
