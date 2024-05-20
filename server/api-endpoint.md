# api end point

<details>
  <summary>Article end-points</summary>
    GET all article -----
   method : GET , access : public , path : /article?query=params

query :

---

1.  page (default : 1 ) - current page number
2.  limit (default : 10) the number of article will be return
3.  page (default : 1 ) - current page number
4.  sort by (default updatedAt) - the property that will used to sort .it could be either updated at or title
5.  search - the search term to filter the article based on the titles

---

###

response :

          success,
          article data
          id,
          title,
          cover,
          author :
                id,
                name,
          timestamp,
          pagination :
           page ,
            limit,
            nextpage ,
            previouspage ,
            totalpage
          links
           self
           nextpage
           previouspage,
           comments,
           author
          400 :
              message,
          500 :
            message,

---

create a new article -----
method : POST , access : private , path : /article,

requestBody :

          title
          body
          cover (optional),
          status (default : draft)
            response :
                      201 :
                        message,
                        article,
                         pagination :
                          page ,
                          limit,
                          nextpage ,
                          previouspage ,
                          totalpage
                          links
                          self
                          nextpage
                          previouspage,
                          comments

                      400 :
                       message
                       data (array of messages)
                        field
                        message
                      500 :
                       message

get a single article -----
method : GET , access : pubic , path : /articles?query=params

query :

                expand (default none) : values or author

Response

           200
            id ,
            title ,
            cover ,
            body,
            timestamp,
            author (optional),
            comments (optional),

            links

          400

           message

          500

          message

update an article (put) -----

method : PUT , access : private , path : /articles/:id,

request body :

                id (optional),
                title ,
                body,
                cover (optional),
                status (default draft)

response :

          200
           message ,
           article data
          links :
           self
          400 :
           message
           data (array of error message )
            field
            message

update an article (patch) -----

method : PATCH , access : private , path : /articles/:id,

request body :

                id (optional),
                title (optional),
                body (optional),
                cover (optional),
                status (default draft)

response :

          200 / 201
           message ,
           article data
          links :
           self
          400 :
           message ,
           data (array of error message ),
            field,
            message ,
           401 :
           message ,
           data (array of error message ),
            field,
            message ,
            404
             message


delete  an article (delete) -----

method : DELETE , access : private , path : /articles/:id,

response : 
            
             204 :
             message 
            404 :
            message 
            401 :
            message 


get all comments in  an article (GET) -----

method : GET , access : public , path : /articles/:id/comments,

query : 

      limit : 10
      page : 1

response 
       
       200 : 
        ok 
       response :
                      201 :
                        comments data :
                         body
                         timestamp
                         author : 
                          id ,
                          name ,
                        message,
                        article,
                         pagination :
                          page ,
                          limit,
                          nextpage ,
                          previouspage ,
                          totalpage
                          links
                              self
                              nextpage
                              previouspage,
                              comments

                      404 :
                       message
                       
                      500 :
                       message
      

###

```markdown
## Article end point

1.  GET [public] -/article?query=params (this endpoint will return a list of articles and we can pass query params to filter or sort or pagination).

2.  POST [private] -/articles (this endpoint will create and return a new post or article ).

3.  PUT [private] -/article/:id (this endpoint will create or update an existing article).

4.  PATCH [private] -/article/:id (this endpoint will update an existing article or create a new article).

5.  DELETE [private] -/article/:id (this endpoint will delete an article article based on user id /author id ).

6.  GET [public] -/articles:id?expand=author,comment (this endpoint will return a single article including author name id and email and also populate recent comments or selected resources).

7.  GET [public] -/article/:id/comments (this endpoint will return a list of comments based on the given id
    of an article ).

8.  GET [private] -/article/:self (this endpoint will return a list of articles and we can pass query params to filter or sort or pagination).
```

</details>

###

<details>
  <summary>Comments end-points</summary>

```markdown
1. GET -/ comments?query=params (this endpoint will return a list of comments based on the given id of an article ).
```

</details>

<details>
  <summary>Admin end-points</summary>

```markdown
1. write here
```




## mock 
  - description: SwaggerHub API Auto Mocking
    url: https://virtserver.swaggerhub.com/thebluesky/ariticle-management-system/1.0.0