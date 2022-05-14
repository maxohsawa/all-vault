# Javascript Async
## Promises
- a promise is an object that map produce a single value some time in the future
- either a resolved value or a reason that it's not resolved
- states
	- fulfilled
	- rejected (+ reason for rejection)
	- pending
- example
```
const promise = new Promise( (resolve, reject) => {
	if (true) {
		resolve('stuff worked');
	} else {
		reject('error, it broke');
	}
});

promise
	.then(result => result + '!')
	.then(result2 => result2 + '?')
	.catch( () => console.log('error'))
	.then(result3 => {
		console.log(result3 + '~');
	});

const promise2 = new Promise( (resolve, reject) => {
	setTimeout(resolve, 100, 'hi');
});

const promise3 = new Promise( (resolve, reject) => {
	setTimeout(resolve, 1000, 'pookie');
});

const promise4 = new Promisef( (resolve, reject) => {
	setTimeout(resolve, 5000, "is it me you're looking for?");
});

Promise.all([promise, promise2, promise3, promise4])
	.then( values => {
		console.log(values);
});
```

- another example
```
const urls = [
	'https://jsonplaceholder.typicode.com/users',
	'https://jsonplaceholder.typicode.com/users',
	'https://jsonplaceholder.typicode.com/users'
];

Promise.all( urls.map( url => {
	return fetch(url).then( res => res.json());
})).then( results => {
	console.log(results[0]);
	console.log(results[1]);
	console.log(results[2]);
}).catch( () => console.log('error'))
	.finally( () => console.log('extra'));
```

## Async Await
- promise example
```
movePlayer(100, 'left')
	.then( () => movePlayer(400, 'left'))
	.then( () => movePlayer(10, 'right'))
	.then( () => movePlayer(330, 'left'))
```

- async await example
```
async function playerStart() {
	const firstMove = await movePlayer(100, 'left');
	await movePlayer(400, 'left');
	await movePlayer(10, 'right');
	await movePlayer(330, 'left');
}

playerStart();
```

- the await keyword can precede a function that returns a promise
- another async await example
```
fetch('https://jsonplaceholder.typicode.com/users')
	.then(resp => resp.json())
	.then(console.log);

async function fetchUsers() {
	const res = await fetch('https://jsonplaceholder.typicode.com/users');
	const data = await res.json();
	console.log(data);
}

fetchUsers();
```

- another async await example, multiple asynchronous function calls
```
const urls = [
	'https://jsonplaceholder.typicode.com/users',
	'https://jsonplaceholder.typicode.com/users',
	'https://jsonplaceholder.typicode.com/users'
];

Promise.all( urls.map( url => {
	return fetch(url).then( res => res.json());
})).then(results => {
	console.log(results[0]);
	console.log(results[1]);
	console.log(results[2]);
}).catch( () => console.log('error'));

const getData = async function() {
	try {
		const [ users, posts, albums ] = await Promise.all(urls.map( url => {
			return fetch(url).then( res => res.json());
		}));
		console.log('users', users);
		console.log('posts', posts);
		console.log('albums', albums);
	} catch(error) {
		console.log('error', error);
	}
}
```

- another async await example, multiple asynchronous function calls but with *for-await-of*
```
const getData2 = async function() {
	const arrayOfPromises = urls.map( url => fetch(url));
	for await (let req of arrayOfPromises) {
		const data = await request.json();
		console.log(data);
	}
}
```
#promises #async #asyncawait