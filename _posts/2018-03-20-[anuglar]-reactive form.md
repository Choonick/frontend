# reactive form
```html
<form (ngSubmit)="onSubmit()" [formGroup]="prodForm" novalidate>

  <h4 class="pl-5 mt-5">상품 정보</h4>
  <fieldset class="mx-5 mb-5 p-3 rounded">
	    <div class="input-group pl-5 my-3">
	      <span class="input-group-addon" id="product-name">상품명</span>
	      <input type="text" formControlName="name" class="form-control col-4"/>
	    </div>
	
	    <div class="input-group pl-5 my-3">
	      <span class="input-group-addon" id="product-listPrice">상품가격</span>
	      <input type="number" formControlName="listPrice" class="form-control col-4"/>
	    </div>
	
	    <div class="input-group pl-5 my-3">
	      <span class="input-group-addon" id="product-qty">상품수량</span>
	      <input type="number" formControlName="qty" class="form-control col-4"/>
	    </div>
	    <div class="input-group pl-5 my-3">
	    <textarea class="form-control col-6" formControlName="desc"
	              rows="4" placeholder="상품 상세 설명"></textarea>
	    </div>
      	<div>
            <input type="submit" value="제출하기">
      </div>
  </fieldset>
  
<from>
```

put formControlName="name" in a tag 

### ../app.module.ts
import:[ReactiveFormsModule]
### ../app.component.ts

```typescript
...

	prodForm: FormGroup;
	constructor(public fb: FormBuilder) {
    this.prodForm = this.fb.group(
      {
        name: ['', Validators.required],
        listPrice: [0,
          Validators.compose([
            Validators.required,
            NumberRangeValidator.min(1000),
            NumberRangeValidator.max(1000000),
            Validators.pattern('[1-9]\\d*')
          ])
        ],
        qty: [0,
          Validators.compose([
            Validators.required,
            NumberRangeValidator.min(1),
            NumberRangeValidator.max(100),
            Validators.pattern('[1-9]\\d*')
          ])
        ],
        desc: ['',
          Validators.compose([
            Validators.required,
            Validators.minLength(5),
            Validators.maxLength(100)
          ])
        ]
      });
  }
 
 onSubmit() {
    alert(`제출\n${JSON.stringify(this.prodForm.value)}`);
  }
 
 ...
```


## Radio button

