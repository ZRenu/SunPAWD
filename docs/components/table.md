# Table 表格

## 示例

```html
   <nz-date-picker [(ngModel)]="date" (ngModelChange)="onChange($event)"></nz-date-picker>
    <br />
    <nz-month-picker
      [(ngModel)]="date"
      (ngModelChange)="onChange($event)"
      nzPlaceHolder="Select month"
    ></nz-month-picker>
    <br />
    <nz-year-picker [(ngModel)]="date" (ngModelChange)="onChange($event)" nzPlaceHolder="Select year"></nz-year-picker>
    <br />
    <nz-range-picker [(ngModel)]="dateRange" (ngModelChange)="onChange($event)"></nz-range-picker>
    <br />
    <nz-week-picker [(ngModel)]="date" (ngModelChange)="getWeek($event)" nzPlaceHolder="Select week"></nz-week-picker>
    <br />
    <button nz-button nzType="default" (click)="changeLanguage()">Switch language for all pickers</button>
````
## API
| 左对齐 | 右对齐 | 居中对齐 |
|-----|-----|-------|
| 单元格 | 单元格 | 单元格   |
| 单元格 | 单元格 | 单元格   |

## JSON结构

```json
{
   tableTile:{
 ...
   },
   tableItem:{
...
   }
}
```

