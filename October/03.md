## Learning about routing & navigation in Nextjs

A Dynamic segment can be created by wrapping a folder's name in square brackets:
`[folderName]`. Example: `[id]` or `[slug]` <br/>
### Dynamic routes <br/>
is a route with a parameter. Below is an example of how it works using Typescript. One of the beauties of working with `Typescript` is that it makes it easier to catch and prevent certain types of bugs which helps improve code quality. 

```
interface Props {
    params: { id: number; photoId: number}
}

const PhotoDetail = ({ params: {id, photoId}}: Props) => {
  return (
    <div>
      Photo{id} {photoId}
    </div>
  )
}

export default PhotoDetail;
```
### Catch-all Segments
Dynamic segments can be extended to catch-all susbsequent segments by adding an ellipsis inside the brackets. <br/>
Example: `pages/products/[[...slug]]`

### Link
`<Link>` is a React component that prefetches the links that are in the viewport. It's used link between pages in your application. 
```
const sortedUsers = sort(users).asc(
    sortOrder === 'email' 
    ? (user) => user.email 
    : (user) => user.name
  );

  return (
    <div>
      <table className="table table-bordered">
        <thead>
          <tr>
            <th>
              <Link href="/users?sortOder=name">Name</Link>
            </th>
            <th>
              <Link href="/users?sortOrder=email">Email</Link>
            </th>
          </tr>
        </thead>
        <tbody>
          {sortedUsers.map((user) => (
            <tr key={user.id}>
              <td>{user.name}</td>
              <td>{user.email}</td>
            </tr>
          ))}
        </tbody>
      </table>
```
 It only downloads the content of the target page. <br/> 
 Caches pages on the client.

 ### Programmatic Navigation
 The two ways to navigate between routes in Nextjs: <br/>
 - Using `<Link>` <br/>
 - Using `useRouter` Hook

### Today's learning
It is important to keep in mind that Nextjs behaves different than standard React or Vite, it is a powerfull framework that large companies take advantage of. There's so much to learn about nextjs and so far what I have been putting to practice has helped me understand the cool features that it has like `use client`, `Client cache` that allows browsers to access files without communicating with the web server, `Dynamic routes` it takes one or more parameters, `layout` which creates UI that is shared between multiple pages and `Prefetching` it brings the data into the cache before the actual requests occur. 

### Last
I have spent a good amount of hours today learning variety of things and so far it has been fun and bit challenging. On top of the topics I have mentioned above I also learned about `fast-sort` and `DaysiUI`. Fast sort makes faster and more memory-efficient sorting. Below is an example: 
```
import { sort } from 'fast-sort';

  // Sort flat arrays
  const ascSorted = sort([1,4,2]).asc(); // => [1, 2, 4]
  const descSorted = sort([1, 4, 2]).desc(); // => [4, 2, 1]

  // Sort users (array of objects) by firstName in descending order
  const sorted = sort(users).desc(u => u.firstName);
```
DaysiUI takes `TailwindCSS` to another level allowing you give component class names so you can make beautiful websites faster than ever. Is easy to use and the documentation setup is straight forward, works on different frameworks. For now I think that has been enough of learning for the day, tomorrow I'll be going over Building APIs.

 
