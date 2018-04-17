select box error

```html
<select formControlName="type" (change)="licenseChange();">
                <option value="" selected>할당하지 않음</option>
                <option *ngFor="let type of types">{{type.name}}</option>
</select>

<select formControlName="code">
    <option value="" selected>할당하지 않음</option>
    <option *ngFor="let code of codes">{{code.name}}</option>
</select>
```

type을 선택하면 그에 맞는 codes가 불러진다.  그러나 licenseChange()의 함수 호출로 codes가 불러지더라도 fromControlName에 "code"의값은 불러지지 않는다. 왜냐하면 클릭을 하지 않았기 때문이다. 그래서 "할당하지 않음" option을 넣어주어 사용자의 클릭을 유도하여햐 한다.