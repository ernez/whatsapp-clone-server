https://www.tortilla.academy/Urigo/WhatsApp-Clone-Tutorial/master/next/step/3

Now we need to compile the tsfile to turn it into a Javascript file the Node can run.

For that we will use Typescript and its tsccommand. The command has many options, but instead of writing them in the command line, we can specify them in a tsconfig.jsonfile at the root of the project.

Our server is gonna use the following tsconfig.jsonfile, feel free to make the necessary modifications based on your needs:

Step 4:

Assuming that the server is running, we can already test our GraphQL endpoint. Because it's exposed to us via a REST endpoint, we can use a $ curlcommand to send a request to GET localhost:4000/graphqland get a response with all the data. Again, the query that we're gonna use to fetch the chats is:

chats {
  id
  name
  picture
  lastMessage {
    id
    content
    createdAt
  }
}
The one-liner version of it with a $ curlcommand looks like so:

curl \
  -X POST \
  -H "Content-Type: application/json" \
  --data '{ "query": "{ chats { id name picture lastMessage { id content createdAt } } }" }' \
  localhost:4000/graphql

Query za playground:

{
  chats {
    id
    name
    picture
    lastMessage {
      id
      content
      createdAt
    }
  }
}

