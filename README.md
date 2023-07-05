#Javascript Async Await & handling Promise.all 


console.log('person1: shows ticket');
console.log('person2: shows ticket');

const perMovie = async () => {
    const promiseWifeBringingTicks = new Promise((resolve, reject) => {
        setTimeout(() => {
            resolve('ticket');
        }, 3000)
    });
    const getPopcorn = new Promise((resolve, reject) =>resolve(`popcorn`));
    const addButter = new Promise((resolve, reject) =>resolve(`butter`));
    const getColdDrinks = new Promise((resolve, reject) =>resolve(`ColdDrinks`));
    let ticket = await promiseWifeBringingTicks;  
    let [popcorn, butter,ColdDrinks] = await Promise.all([getPopcorn, addButter, getColdDrinks])
    console.log(`${popcorn}, ${butter}, ${ColdDrinks}`)
    return ticket;
}
perMovie().then((m) => console.log(`person3: shows ${m}`));

console.log('person4: shows ticket');
console.log('person5: shows ticket');
