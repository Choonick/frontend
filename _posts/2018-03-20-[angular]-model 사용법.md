# angular model 사용법

### model/ model.ts

```typescript
export class Model {
    name: string;
    title: string;
}
```

### /test.component.ts

```typescript
model = new Model();
...
this.model.name = 'abc';
this.model.title = 'eeed';
```

