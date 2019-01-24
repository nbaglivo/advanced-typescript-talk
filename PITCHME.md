@title[1]

### Record

```
export enum Services {
    DoorToDoor = 'DoorToDoor',
    AirDelivery = 'AirDelivery',
    SpecialDelivery: 'SpecialDelivery',
    InStore: 'InStore',
}

type Email = string;
type ClientServicesList = Record<Services, Email[]>

const list: ClientServicesList {
    [Services.DoorToDoor]: ['nico@fc', 'lean@fc'],
    lala: ['nico@fc', 'lean@fc'], // Error
    [Services.InStore]: 'nico@fc' // Error
}
```

@title[2]

### Keyof

```
export enum Services {
    DoorToDoor = 'DoorToDoor',
    AirDelivery = 'AirDelivery',
    SpecialDelivery: 'SpecialDelivery',
    InStore: 'InStore',
}

type keys = keysof Services
// ['DoorToDoor', 'AirDelivery', 'SpecialDelivery', 'InStore']
```

---

@title[3]

### Partial


```
interface Props {
    color: string;
    background: string;
}

interface PartialProps {
    color?: string;
    background?: string;
}

const props1: Props = {
    color: 'red'; // Error
}

const props2: PartialProps = {
    color: 'red'; // Fine
}

const props3: Partial<Props> = {
    color: 'red'; // Fine
}

```

---

@title[4]

### Partial (continuation)

Use it as defaults.

```
interface Props {
    color: string;
    background: string;
}

const defaultProps: Partial<Props> = {
    color: 'red'; // Fine
}

```

---

@title[5]

### Pick

```
type C = { a: string; b: string; c: boolean; d: string; }
type D = { b: string; c: boolean; }
type pickCkeys = Pick<C, 'c'>
type pickCD = Pick<C, keyof D>;

```

---

@title[6]

### Difference between type and interface?

Homework, reading this:
https://stackoverflow.com/questions/36782896/in-typescript-what-is-the-difference-between-type-and-interface
