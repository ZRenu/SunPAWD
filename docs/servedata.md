## 数据对接

Sunray PAWD of Angular是基于是[Ant Design of Angular](https://ng.ant.design/docs/introduce/zh)二次封装开发，若无特殊说明均按照其组件结构返回数据结构。

#### 参考实例 — Menu导航菜单

其它组件服务端数据返回结构请对照[Ant Design of Angular](https://ng.ant.design/docs/introduce/zh)组件结构设计。

#### 前端代码

``` html
<ul nz-menu nzMode="inline" style="width: 240px;">
      <ng-container *ngTemplateOutlet="menuTpl; context: { $implicit: menus }"></ng-container>
      <ng-template #menuTpl let-menus>
        <ng-container *ngFor="let menu of menus">
          <li
            *ngIf="!menu.children"
            nz-menu-item
            [nzPaddingLeft]="menu.level * 24"
            [nzDisabled]="menu.disabled"
            [nzSelected]="menu.selected"
          >
            <i nz-icon [nzType]="menu.icon" *ngIf="menu.icon"></i>
            <span>{{ menu.title }}</span>
          </li>
          <li
            *ngIf="menu.children"
            nz-submenu
            [nzPaddingLeft]="menu.level * 24"
            [nzOpen]="menu.open"
            [nzTitle]="menu.title"
            [nzIcon]="menu.icon"
            [nzDisabled]="menu.disabled"
          >
           <ul>
              <ng-container *ngTemplateOutlet="menuTpl; context: { $implicit: menu.children }"></ng-container>
            </ul>
          </li>
        </ng-container>
      </ng-template>
    </ul>
```

#### 服务端返回JSON

``` json
  menus = [
    {
      level: 1,
      title: 'Mail Group',
      icon: 'mail',
      open: true,
      selected: false,
      disabled: false,
       children: [
        {
          level: 2,
          title: 'Group 1',
          icon: 'bars',
          open: false,
          selected: false,
          disabled: false,
          children: [
            {
              level: 3,
              title: 'Option 1',
              selected: false,
              disabled: false
            },
            {
              level: 3,
              title: 'Option 2',
              selected: false,
              disabled: true
            }
          ]
       ]
  ]
         
```
返回JSON结构说明请对照[Menu导航菜单](https://ng.ant.design/components/menu/zh#api)

















