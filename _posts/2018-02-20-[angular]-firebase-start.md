## Source
### 1. npm i firebase angularfire2 --save
### 2. ../environments/environment.ts

```
export const environment = {
  production: false,
  firebase: {
    apiKey: '',
    authDomain: '',
    databaseURL: '',
    projectId: '',
    storageBucket: '',
    messagingSenderId: ''
  }
};
```
### 3. ../app.module.ts

```
import { environment } from '../environments/environment';
import { AngularFireDatabaseModule, AngularFireDatabase } from 'angularfire2/database';
...

 imports: [
 	...
   AngularFireModule.initializeApp(environment.firebase),
   AngularFireDatabaseModule
  ],
```


### 4. ../app.compomonent.ts

```
import { Component, OnInit } from '@angular/core';
import { FirebaseListObservable } from 'angularfire2/database-deprecated';
import { AngularFireDatabase, AngularFireList } from 'angularfire2/database';
import { Observable } from 'rxjs/Observable';

...

export class AppComponent implements OnInit {

  itemsRef: AngularFireList<any>;
  items: Observable<any[]>;

  constructor(public af: AngularFireDatabase) {
    this.itemsRef = af.list('/');
    this.items = this.itemsRef.snapshotChanges().map(changes => {
      return changes.map(c => ({key: c.payload.key, val: c.payload.val()}));
    });

    this.items.subscribe(o => console.log(o));
  }


  addItem(newName: string) {
    this.itemsRef.push({ text: newName });
  }
  updateItem(key: string, newText: string) {
    this.itemsRef.update(key, { text: newText });
  }
  deleteItem(key: string) {
    this.itemsRef.remove(key);
  }
  deleteEverything() {
    this.itemsRef.remove();
  }
}
```

### 5. ../app.component.html

```
<!--The content below is only a placeholder and can be replaced.-->
<div style="text-align:center">
  <h1>
    Welcome to
  </h1>
 </div>

<h2>Here are some links to help you start: </h2>
<ul>
  <li *ngFor="let item of items | async">
    <input type="text" #updatetext [value]="item.val.text"/>
    <button (click)="updateItem(item.key, updatetext.value)">Update</button>
    <button (click)="deleteItem(item.key)">Delete</button>
  </li>
</ul>
<input type="text" #newitem />
<button (click)="addItem(newitem.value)">Add</button>
<button (click)="deleteEverything()">Delete All</button>

```

[참고](https://github.com/angular/angularfire2)
