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
    const { tT, cT, tE, cE, tG, cG } = arr.reduce((previous, current) => {
        if (current.profession === 'Teacher') {
            previous.tT += current.salary;
            previous.cT++;
        } else if (current.profession === 'Engineer') {
            previous.tE += current.salary;
            previous.cE++;
        } else {
            previous.tG += current.salary;
            previous.cG++;
        }
        return previous;
    }, { tT: 0, cT: 0, tE: 0, cE: 0, tG: 0, cG: 0 });

    return [{ averageTeachersSalary: tT / cT },
    { averageEngineersSalary: tE / cE },
    { averageGardenersSalary: tG / cG }];
}

console.log(averageBy(data));

```
