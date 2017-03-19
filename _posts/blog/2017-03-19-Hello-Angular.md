---
layout: post
title: "สวัสดี Angular2 เรามาลองสร้าง Hello angular กันเถอะ"
modified:
categories: blog
excerpt:
tags: [angular]
image:
  feature:
date: 2017-03-19T19:00:00+07:00
modified: 
author: muggle
comments: true
share: true
---
   
    
สร้าง Project Angular2 ง่าย ๆ ด้วย tools angular/cli  

<figure>
	<img src="/images/blogs/201703/angular2.jpg" alt="image">
</figure>

เรามาสร้าง Project angular เริ่มต้นด้วย @angular/cli 

### เครื่องมือที่ต้องใช้
 * [Node](https://nodejs.org/en/)


ข้้นแรกให้เราเปิด Command Prompt (Admin)

แล้วพิมพ์คำสั่งดังนี้ (เพื่อติดตั้ง @angular/cli)

~~~bash
  npm install -g @angular/cli
~~~

เมื่อติดตั้งเสร็จให้เราลองใช้คำสั่ง เพื่อเช็คให้แน่ใจว่าติดตั้ง angular/cli เรียบร้อยแล้ว

~~~bash
  ng --version
~~~

จะได้หน้าตาประมาณนี้

~~~bash
   / \   _ __   __ _ _   _| | __ _ _ __     / ___| |   |_ _|
  / △ \ | '_ \ / _` | | | | |/ _` | '__|   | |   | |    | |
 / ___ \| | | | (_| | |_| | | (_| | |      | |___| |___ | |
/_/   \_\_| |_|\__, |\__,_|_|\__,_|_|       \____|_____|___|
               |___/
@angular/cli: 1.0.0-rc.2
node: 7.7.2
os: win32 x64
~~~

ต่อไปให้เราย้ายตำแหน่งไปที่เราต้องการสร้าง Project ซึ่งผมจะสร้างไว้ที่ D:/Projects
ผมก็ใช้คำสั่ง

~~~bash
  cd D:/Projects
~~~

คราวนี้เราก็เริ่มสร้าง Project ด้วยคำสั่งนี้

~~~bash
  ng new hello-angular
~~~
> new #สร้าง Project ใหม่  
> hello-angular #ชื่อ Project  

รอจนติดตั้งเสร็จจะมีหน้าตาประมาณนี้

~~~bash
D:\Projects>ng new hello-angular
installing ng
  create .editorconfig
  create README.md
  create src\app\app.component.css
  create src\app\app.component.html
  create src\app\app.component.spec.ts
  create src\app\app.component.ts
  create src\app\app.module.ts
  create src\assets\.gitkeep
  create src\environments\environment.prod.ts
  create src\environments\environment.ts
  create src\favicon.ico
  create src\index.html
  create src\main.ts
  create src\polyfills.ts
  create src\styles.css
  create src\test.ts
  create src\tsconfig.app.json
  create src\tsconfig.spec.json
  create src\typings.d.ts
  create .angular-cli.json
  create e2e\app.e2e-spec.ts
  create e2e\app.po.ts
  create e2e\tsconfig.e2e.json
  create .gitignore
  create karma.conf.js
  create package.json
  create protractor.conf.js
  create tsconfig.json
  create tslint.json
Successfully initialized git.
Installing packages for tooling via yarn.
Installed packages for tooling via yarn.
Project 'hello-angular' successfully created.
~~~

โครงสร้างหน้าตากก็จะมีประมาณนี้ 

<figure>
	<img src="/images/blogs/201703/str.jpg" alt="image">
</figure>

> ในส่วนนี้ผมจะอธิบายการทำงานของแต่ล่ะ Folder ไม่ครบทั้งหมดนะครับ  
> เอาแค่หลักๆที่ใช้งานก็จะมี  
> app  จะเก็บ  folder ย่อยต่างๆ อีก เช่น service component  
> assets จะไว้เก็บจำพวกไฟล์ css, js  
> .angular-cli.json ไว้ import ต่างๆ เช่น css, javascript เป็นต้น  

ไหนๆ ลองสั่งรันดูสิ

~~~bash
ng serve
~~~

รอจนเสร็จจะได้หน้าตาประมาณนี้

~~~bash
** NG Live Development Server is running on http://localhost:4200 **
Hash: 32b86d423536384634c9
Time: 8214ms
chunk    {0} polyfills.bundle.js, polyfills.bundle.js.map (polyfills) 157 kB {4} [initial] [rendered]
chunk    {1} main.bundle.js, main.bundle.js.map (main) 4.11 kB {3} [initial] [rendered]
chunk    {2} styles.bundle.js, styles.bundle.js.map (styles) 9.77 kB {4} [initial] [rendered]
chunk    {3} vendor.bundle.js, vendor.bundle.js.map (vendor) 2.69 MB [initial] [rendered]
chunk    {4} inline.bundle.js, inline.bundle.js.map (inline) 0 bytes [entry] [rendered]
webpack: Compiled successfully.
~~~

ลองเปิด บราวเซอร์ เข้าตามลิ้งค์ [http://localhost:4200](http://localhost:4200)

<figure>
	<img src="/images/blogs/201703/app-work.jpg" alt="image">
</figure>

อุต๊ะ !!! ออกมาแล้ววววว

ไหนลองเปลี่ยนข้อความดูหน่อยสิ

~~~typescript
//app.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'Hello Angular2';
}
~~~

แค่กด Save เราก็ไปรอหน้าเว็บรีโหลดเองโดยที่เราไม่ต้องทำอะไรเลย

<figure>
  <img src="/images/blogs/201703/hello-angular2.jpg" alt="image">
</figure>

เป็นอันเรียบร้อย เราได้ Project เริ่มต้นแล้ว

คราวหน้าเรามาต่อกัน ด้วยการเพิ่มหน้าและ Routes เบื้้องต้นกัน

credit: [angular.io/](https://angular.io/), [@angular/cli](https://github.com/angular/angular-cli)

