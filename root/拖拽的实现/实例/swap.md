资源互换，[演示](https://stackblitz.com/edit/sunyi-drag-swap?)

```html
<div
  class="box"
  (dragenter)="dragenter($event)"
  (dragover)="dragover($event)"
  (dragleave)="dragleave($event)"
  (drop)="drop($event)"
>
  <span
    *ngFor="let s of [1,2,3,4,5,6,7,8,9]"
    draggable="true"
    (dragstart)="dragstart($event)"
    (dragend)="dragend($event)"
    >可拖拽{{s}}</span
  >
</div>
<div
  class="box"
  (dragenter)="dragenter($event)"
  (dragover)="dragover($event)"
  (dragleave)="dragleave($event)"
  (drop)="drop($event)"
></div>
```

```ts

  span;
  dragstart(e) {
    e.target.classList.add("drag");
    this.span = e.target;
  }
  dragend(e) {
    e.target.classList.remove("drag");
  }
  dragenter(e) {
    e.stopPropagation();
    e.preventDefault();
    if (e.target.classList.contains("box")) {
      e.target.classList.add("drag");
    }
  }
  dragover(e) {
    e.stopPropagation();
    e.preventDefault();
  }
  dragleave(e) {
    e.target.classList.remove("drag");
  }
  drop(e) {
    if (e.target.classList.contains("box")) {
      this.span.parentNode.removeChild(this.span);
      e.target.appendChild(this.span);
    }
    this.span = null;
    e.target.classList.remove("drag");
  }

```

```css
div {
  border: 1px solid #eee;
  border-radius: 4px;
  height: 200px;
  width: 400px;
  background: #fefefe;
  margin: 20px;
}

span {
  display: inline-block;
  border: 2px dotted transparent;
  margin: 20px;
  background: #eee;
  padding: 2px;
  border-radius: 2px;
}
.drag {
  border-color: green;
}
```
