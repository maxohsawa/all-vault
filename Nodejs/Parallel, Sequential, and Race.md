## Parallel
- run multiple tasks at the same time
```
const promisify = (item, delay) =>
	new Promise((resolve) =>
	setTimeout( () =>
		resolve(item, delay));
const a = () => promisify('a', 100);
const b = () => promisify('b', 5000);
const c = () => promisify('c', 3000);

async function parallel() {
	const promises = [a(), b(), c()];
	const [output1, output2, output3] = await Promise.all(promises);
	return `parallel is done: ${output1} ${output2} ${output3}`
}

parallel().then(console.log);
// same as parallel().then( data => console.log(data));
```