# GraphCMS Headless Blog
![GraphCMS Headless Blog](https://i.ibb.co/NmnJnKD/image.png)

YT Tutorial: https://www.youtube.com/watch?v=HYv55DhgTuA
GH Soucrce: https://github.com/adrianhajdin/project_graphql_blog
GH https://github.com/raphlev/react23-nextjs-graphcms-graphql-blog-jsm
graphcms: https://app.graphcms.com/

back-end = graphcms
front-end = react + nextjs + graphql + tailwindcss

## Introduction
This is a code repository for the corresponding video tutorial. 

With featured and recent posts, categories. full markdown articles, author information, comments, and much more, this fully responsive CMS Blog App is the best Blog Application that you can currently find on YouTube. And what's best of all is that you and your clients can manage the blog from a dedicated Content Management System.

You'll also learn how to work with GraphCMS. GraphCMS is a headless content management system based on GraphQL technology enabling seamless integration with any application.

## Graphcms schema creation
- YT : 0h:13mn - 0h:19mn : schema definition: Author, Category, Post, Comment
- YT : 0h:48mn - 0h:50mn : graphql data fetching playground in graphcms
- YT : 2h:45mn - 2h:46mn : missing reference attribute

## Graphcms - Permanent Auth Tokens
- YT : 2h:46mn - 2h:47mn : full permission API Access > Permanent Auth Token
Need to create Token to be used to create / post comments in graphcms. Give it full permission
- https://app.graphcms.com/f15453d723154bc885856cf61f4f6090/master/settings/api-access#tokens
## graphcms - comment submitted for review
- YT : 2h:46mn:40sec - 2h:47mn:40sec 
When user add comment, it is not displayed directly in the blog, some comment may not be appropriate, blog owner want to select which one is allowed
- the comment appears as "draft" in the Content > Comment section - this is created by DEV token 
- need to edit it and select "Publish" green button on graphcms dashboard to make this comment appeared !!!
- https://app.graphcms.com/f15453d723154bc885856cf61f4f6090/master/content/1e5cc4728a62481f94691d4805352ea3/view/173a19b506064b90805d335e8add5cb6
- as a rsult, this comment will appear in the blog page
## Graphcms code playground
- see services/index.js
- https://app.graphcms.com/f15453d723154bc885856cf61f4f6090/master/graphiql = online code playground
Try this:
query MyQuery {
      postsConnection {
        edges {
          cursor
          node {
            author {
              bio
              name
              id
              photo {
                url
              }
            }
            createdAt
            slug
            title
            excerpt
            featuredImage {
              url
            }
            categories {
              name
              slug
            }
          }
        }
      }
    }
