#  Week 3 - Wednesday

##  React Router Blog ✔️

### Description 

Create a blog with React Router and get info from posts from a json file.

### Example

![blog example gif](/src/images/blog.gif)

<details>
  <summary>Index</summary>
  
  ```js
  
  import ReactDOM from 'react-dom/client';
  import { BrowserRouter, Routes, Route } from 'react-router-dom';
  import Blog from './challenges/react-blog/Blog';
  import { Article } from './challenges/react-blog/Article'
  
  const root = ReactDOM.createRoot(document.getElementById('root'));



  root.render(
      <BrowserRouter>
          <Routes>
              <Route path="/" element={<Blog />} />
              <Route path=":id" element={ <Article /> } />
              <Route 
                  path='*'
                  element={
                      <h2>There's nothing here..</h2>
                  }    
                  />
          </Routes>
      </BrowserRouter>
  );

  ```
  
</details>

<details>
  <summary>Blog Component</summary>
  
  ```js
  
  import { getArticles } from './data';
import { Link } from 'react-router-dom';

const Blog = () => {

    const articles = getArticles();

    return (
        <>
            <h2
                style={{
                    padding: "1rem",
                    borderBottom: "solid 1px",
                    textAlign: "center"
                }}
            >
                Core Code Blog
            </h2>
            {articles.map((article) => {
                return (
                    <div style={{ 
                        borderBottom: "solid 1px",
                        padding: "0.5rem"
                        }} key={article.id}>
                        <Link to={article.id}>{article.title}</Link>
                        <p>Created by {article.creator} - {article.releaseDate}</p>
                    </div>
                );
            })}
        </>
    )
}

export default Blog;
  
  ```
  
</details>

<details>
  <summary>Article Component</summary>
  
  ```js
  
  import { useParams, Link } from "react-router-dom";
import { getArticle } from "./data";

const Article = () => {

    let params = useParams();
    let article = getArticle(params.id);
    
    return(
        <>
            <h2>{article.title}</h2>
            <p>{article.body}</p>
            <p>Created by: {article.creator}</p>
            <Link to="/">Go Back</Link>
        </>
    );
}

export { Article };
  
  ```
  
</details>

</details>

<details>
  <summary>Data</summary>
  
  ```js
  
  let articles = [
    {
        title: "Hello World",
        body: "This is the first article!! \nWelcome to React journey from cero to master.\n Stay tune...",
        creator: "Jesus Chavez",
        releaseDate: "02/05/22",
        id: "1first"
    },
    {
        title: "Follow the crumbs",
        body: "The main thing a developer needs to know is how to follow the crumbs, in this case is not literally following breadcrumbs but instead know how to google every hint we have to make the job done.",
        creator: "Jesus Chavez",
        releaseDate: "02/05/22",
        id: "2nd"
    },
    {
        title: "Always look for a partner",
        body: "Partners, coding as in real life will be easier if we have someone with us to travel along the path!",
        creator: "Jesus Chavez",
        releaseDate: "02/05/22",
        id: "3rd"
    },
]

const getArticles = () => {
    return articles;
}

const getArticle = (number) => {
    return articles.find( 
        (article) =>  article.id === number
    );
}

export {getArticles, getArticle};
  
  ```
  
</details>
