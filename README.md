What to configure?

Configure jwt issuer-uri of authorization server in application.yml


a) Request to resource server with Authorization header

curl --location 'http://localhost:8081/users' \
--header 'Authorization: Bearer <tokenValue>' \
--header 'Cookie: JSESSIONID=3EABD073A4738AF67081BF7C7AACCA82'

How should i get a value for Authorization header??

You can get it by invoking following api

curl --location 'http://localhost:8080/realms/appsdeveloperblog/protocol/openid-connect/token' \
--header 'grant_type: authorization_code' \
--header 'client_id: <client-app-id>' \
--header 'client_secret: <client-secret>' \
--header 'code: <code which you would see after login and while redirecting in browser if you are using>' \
--header 'redirect_uri: http://localhost:8083/callback' \
--header 'scope: read_custom_scope' \
--header 'Content-Type: application/x-www-form-urlencoded'

