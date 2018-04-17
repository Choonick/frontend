# Angular @Output

 자식 component의 이벤트를 부모가 듣고있는다.



### 자식 component

```
import { Component, EventEmitter, Input, Output } from '@angular/core';

@Component({
  selector: 'app-voter',
  template: `
    <button (click)="vote()">Disagree</button>
  `
})
export class VoterComponent {
  @Output() onVoted = new EventEmitter<boolean>();


  vote() {
    this.onVoted.emit('hello output');
  }
}
```



### 부모 component

```
import { Component }      from '@angular/core';

@Component({
  selector: 'app-vote-taker',
  template: `
    <app-voter *ngFor="let voter of voters"
      (onVoted)="onVoted($event)">
    </app-voter>
  `
})
export class VoteTakerComponent {
  agreed = 0;
  disagreed = 0;
  voters = ['Mr. IQ', 'Ms. Universe', 'Bombasto'];

  onVoted($event) {
    console.log($event);
  }
}
```



부모 component에서 property로 이벤트 바인딩을 이용하여 자식 component로 보낸다. 

자식 component는 이를 @Output으로 받은 다음 결과값을 this.onVoted.emit(''); 메소드를 통해서 보낸다.

[참조](https://angular.io/guide/component-interaction)

