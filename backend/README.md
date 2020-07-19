# Strapi application

# Start Strapi app.
$ yarn create strapi-app backend --quickstart --no-run
$ yarn strapi install graphql
$ npm run develop 

## setting data
@ http://localhost:1337/admin/plugins/content-type-builder
1. Create categories by Add New 'Collection'
You may want to assign a category to your article (news, trends, opinion). You are going to do this by creating another content type in Strapi.

2. Create a category content type with the following field
'name' with type 'Text'

3. Create a new field in the Article content type which is a Relation Category has many Articles like below:
Strapi relational fields

4. Click on the Roles & Permission and click on the public role. And check the 'category' 'find' and 'findone' routes and save.
Now you'll be able to select a category for your article in the right sidebox.

get date : 
method 1 : 
GET http://localhost:1337/articles

method 2 : (by graphql)
POST http://localhost:1337/graphql
body : 
query Articles {
    articles {
        title
        content
        image {
            url
        }
        published_at
    }
}

response : 
{
    "data": {
        "articles": [
            {
                "title": "titleTest",
                "content": "Contest\nContest\nContest\n\nContest\nv\nContest\nv\nv\nContest\n\nContest\nContest\nContest\nContest\n",
                "image": {
                    "url": "/uploads/1593843054127122_2991f51c5d.png"
                },
                "published_at": null
            },
            {
                "title": "article2",
                "content": "article2\narticle2\narticle2\narticle2\n",
                "image": {
                    "url": "/uploads/18384501412_37bebf5737_o_ac05aaa753.jpeg"
                },
                "published_at": "2020-07-06"
            }
        ]
    }
}


# Start frontend React app.
$ yarn create react-app frontend
$ cd frontend
$ yarn dev
$ yarn add react-router-dom
$ yarn add apollo-boost @apollo/react-hooks graphql react-apollo
$ vim .env
REACT_APP_BACKEND_URL="http://localhost:1337"
$ yarn start

@ http://localhost:3000/


ref : 
https://strapi.io/blog/build-a-blog-with-react-strapi-and-apollo


