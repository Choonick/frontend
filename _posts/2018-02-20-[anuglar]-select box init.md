# select box init

```
<select #country (change)="change($event)">
	<option value="" selected disabled hidden>시/도</option>
	<option *ngFor="let city of citys">{{city}}</option>
</select>
```

