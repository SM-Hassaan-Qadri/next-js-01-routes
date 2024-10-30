how to make it 
Here’s a detailed guide on creating routes in Next.js:
1. **Setting Up Basic Routes**

    In Next.js, each file you add to the pages directory automatically becomes a route.
    For example:
        pages/index.js corresponds to the home route (/).
        pages/about.js corresponds to /about.

2. **Creating Nested Routes**

    To create nested routes, organize files within subdirectories in pages.
    For instance:
        pages/blog/index.js will be accessible at /blog.
        pages/blog/post.js will be accessible at /blog/post.

3. **Adding Dynamic Routes**

    Dynamic routes allow you to create pages with paths that include variables.
    To create a dynamic route, wrap the filename in square brackets.
    Example:
        pages/blog/[id].js enables routes like /blog/1, /blog/2, where id is a variable.
    Access the variable in the page using useRouter:

    javascript

    import { useRouter } from 'next/router';
    const Post = () => {
      const router = useRouter();
      const { id } = router.query;
      return <div>Post ID: {id}</div>;
    };
    export default Post;

4. **Defining API Routes**

    To handle backend logic, create files in the pages/api directory. Each file becomes an API endpoint.
    For example, pages/api/hello.js would be available at /api/hello.
    Sample API route:

    javascript

    export default function handler(req, res) {
      res.status(200).json({ message: 'Hello from Next.js API' });
    }

