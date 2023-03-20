# JS-Rest-API
JS-Rest-API


<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no" />
</head>
<body class="px-2">
<div><main class="container mx-auto max-w-4xl">
<h2>Guide</h2>
<p>Below you'll find examples using <a href="https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API">Fetch API</a> but you can JSONPlaceholder with any other language.</p>
<p>You can copy paste the code in your browser console to quickly test JSONPlaceholder.</p>
<div id="crbn"></div>
<h3>Getting a resource</h3>
<pre><code class="language-js">fetch('https://jsonplaceholder.typicode.com/posts/1')
  .then((response) =&gt; response.json())
  .then((json) =&gt; console.log(json));
</code></pre>
<p>👇 <em>Output</em></p>
<pre><code class="language-js">{
  id: 1,
  title: '...',
  body: '...',
  userId: 1
}
</code></pre>
<h3>Listing all resources</h3>
<pre><code class="language-js">fetch('https://jsonplaceholder.typicode.com/posts')
  .then((response) =&gt; response.json())
  .then((json) =&gt; console.log(json));
</code></pre>
<p>👇 <em>Output</em></p>
<pre><code class="language-js">[
  { id: 1, title: '...' /* ... */ },
  { id: 2, title: '...' /* ... */ },
  { id: 3, title: '...' /* ... */ },
  /* ... */
  { id: 100, title: '...' /* ... */ },
];
</code></pre>
<h3>Creating a resource</h3>
<pre><code class="language-js">fetch('https://jsonplaceholder.typicode.com/posts', {
  method: 'POST',
  body: JSON.stringify({
    title: 'foo',
    body: 'bar',
    userId: 1,
  }),
  headers: {
    'Content-type': 'application/json; charset=UTF-8',
  },
})
  .then((response) =&gt; response.json())
  .then((json) =&gt; console.log(json));
</code></pre>
<p>👇 <em>Output</em></p>
<pre><code class="language-js">{
  id: 101,
  title: 'foo',
  body: 'bar',
  userId: 1
}
</code></pre>
<p><strong>Important</strong>: resource will not be really updated on the server but it will be faked as if.</p>
<h3>Updating a resource</h3>
<pre><code class="language-js">fetch('https://jsonplaceholder.typicode.com/posts/1', {
  method: 'PUT',
  body: JSON.stringify({
    id: 1,
    title: 'foo',
    body: 'bar',
    userId: 1,
  }),
  headers: {
    'Content-type': 'application/json; charset=UTF-8',
  },
})
  .then((response) =&gt; response.json())
  .then((json) =&gt; console.log(json));
</code></pre>
<p>👇 <em>Output</em></p>
<pre><code class="language-js">{
  id: 1,
  title: 'foo',
  body: 'bar',
  userId: 1
}
</code></pre>
<p><strong>Important</strong>: resource will not be really updated on the server but it will be faked as if.</p>
<h3>Patching a resource</h3>
<pre><code class="language-js">fetch('https://jsonplaceholder.typicode.com/posts/1', {
  method: 'PATCH',
  body: JSON.stringify({
    title: 'foo',
  }),
  headers: {
    'Content-type': 'application/json; charset=UTF-8',
  },
})
  .then((response) =&gt; response.json())
  .then((json) =&gt; console.log(json));
</code></pre>
<p>👇 <em>Output</em></p>
<pre><code class="language-js">{
  id: 1,
  title: 'foo',
  body: '...',
  userId: 1
}
</code></pre>
<p><strong>Important</strong>: resource will not be really updated on the server but it will be faked as if.</p>
<h3>Deleting a resource</h3>
<pre><code class="language-js">fetch('https://jsonplaceholder.typicode.com/posts/1', {
  method: 'DELETE',
});
</code></pre>
<p><strong>Important</strong>: resource will not be really updated on the server but it will be faked as if.</p>
<h3>Filtering resources</h3>
<p>Basic filtering is supported through query parameters.</p>
<pre><code class="language-js">// This will return all the posts that belong to the first user
fetch('https://jsonplaceholder.typicode.com/posts?userId=1')
  .then((response) =&gt; response.json())
  .then((json) =&gt; console.log(json));
</code></pre>
<h3>Listing nested resources</h3>
<p>One level of nested route is available.</p>
<pre><code class="language-js">// This is equivalent to /comments?postId=1
fetch('https://jsonplaceholder.typicode.com/posts/1/comments')
  .then((response) =&gt; response.json())
  .then((json) =&gt; console.log(json));
</code></pre>
<p>The available nested routes are:</p>
<ul>
<li><a href="/posts/1/comments">/posts/1/comments</a></li>
<li><a href="/albums/1/photos">/albums/1/photos</a></li>
<li><a href="/users/1/albums">/users/1/albums</a></li>
<li><a href="/users/1/todos">/users/1/todos</a></li>
<li><a href="/users/1/posts">/users/1/posts</a></li>
</ul>
</main>
</div>
</body>
</html>
