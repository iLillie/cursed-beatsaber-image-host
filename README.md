# Cursed Beat Saber Image Host
A way to host the Beat Saber preview images

## How do I use it?
1. Fork the repository
2. Add OCULUS_TOKEN as a repository secret in repository settings under "Secrets and Variables" 
3. Go to actions
4. Select the workflow
5. Call with obb binary id of version you want to extract covers out of

## Where can I find obb binary id

### Find binary id of the live version
```bash
curl --request POST \
  --url https://graph.oculus.com/graphql \
  --header 'Content-Type: application/x-www-form-urlencoded' \
  --data access_token=OCULUS_ACCESS_TOKEN_HERE_REPLACE_ME \
  --data doc_id=2885322071572384 \
  --data 'variables={"applicationID": "2448060205267927"}' > versions-response.json
```

Search for LIVE to get the latest binary version, and then copy its id

### Get binary details
```bash
curl --request POST \
  --url https://graph.oculus.com/graphql \
  --header 'Content-Type: application/x-www-form-urlencoded' \
  --data access_token=OCULUS_ACCESS_TOKEN_HERE_REPLACE_ME \
  --data doc_id=24072064135771905 \
  --data 'variables={"binaryID": "BINARY_ID_HERE_REPLACE_ME"}' > binary-response.json
```

Then search for obb, and you will find the binary id for it.
