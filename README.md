# reduce.js
Average of an array of objects - use single reduce 🚩

```
const data = [
    { name: 'Johnny', profession: 'Teacher', salary: 6000 },
    { name: 'Moses', profession: 'Engineer', salary: 12000 },
    { name: 'David', profession: 'Teacher', salary: 7000 },
    { name: 'Jonathan', profession: 'Engineer', salary: 15000 },
    { name: 'Rachel', profession: 'Gardener', salary: 8000 },
    { name: 'Edward', profession: 'Gardener', salary: 9000 }
]

function averageBy(arr) {
    const { tT, cT, tE, cE, tG, cG } = arr.reduce((a, b) => {
        if (b.profession === 'Teacher') {
            a.tT += b.salary;
            a.cT++;
        } else if (b.profession === 'Engineer') {
            a.tE += b.salary;
            a.cE++;
        } else {
            a.tG += b.salary;
            a.cG++;
        }
        return a;
    }, { tT: 0, cT: 0, tE: 0, cE: 0, tG: 0, cG: 0 });

    return [{ averageTeacherSsalary: tT / cT },
    { averageEngineersSsalary: tE / cE },
    { averageGardenersSsalary: tG / cG }];
}

console.log(averageBy(data));
```
