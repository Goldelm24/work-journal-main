Nextjs Is a framework for building fast and search engine friendly applications. <br/>
Today I learned about Data fetching, caching, static and dynamic rendering.

```
  const UsersPage = async () => {
  const res = await fetch('https://jsonplaceholder.typicode.com/users', { cache: 'no-store'});
  const users: User[] = await res.json(); 
```
Static renders at build time.

```
○  (Static)  automatically rendered as static HTML (uses no initial props)
```
Dynamic renders at request time. 

``` λ  (Server)  server-side renders at runtime (uses getInitialProps or getServerSideProps)
    ○  (Static)  automatically rendered as static HTML (uses no initial props)
```
