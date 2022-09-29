# Semver
This package is used to manage the versions.
```js
const semver=require("semver");
const range= new semver.Range("~2.22.2");   //~ sign means only patch version can be updated.
                                            //Range() function determines the update range of that packages.
console.log(range);
/*
Range {
    options: {},
    loose: false,
    includePrerelease: false,
    raw: '~2.22.2',
    set: [ [ [Comparator], [Comparator] ] ],
    range: '>=2.22.2 <2.23.0-0'
  }
*/

var satisfy=semver.satisfies("2.22.27",range);
console.log(satisfy);   //true

//inc() incremented the version by 1 depending on 2nd parameter. if 2nd parameter is patch then patch value will be updated.
console.log(semver.inc("1.3.3","patch"));   //1.3.4
console.log(semver.inc("1.3.3","minor"));   //1.4.0
console.log(semver.inc("1.3.3","major"));   //2.0.0

console.log(semver.parse("1.3.4-beta.10"));

/*SemVer {
    options: {},
    loose: false,
    includePrerelease: false,
    raw: '1.3.4-beta.10',
    major: 1,
    minor: 3,
    patch: 4,
    prerelease: [ 'beta', 10 ],
    build: [],
    version: '1.3.4-beta.10'
  }
  */
```

