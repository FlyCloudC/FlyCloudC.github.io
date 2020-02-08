---
layout: post
title: New features in es6
---

# ECMAScript6������

�⼸������е����ã���ES6��д��֮ǰд�ļ�����ҳ������д�Ĺ�����ѧ���˼���ES6�ļ��ɣ���������¼һ�¡�

## let��������

let�Ĺ�����var���ƣ���������һ������������let�ĺô����ǣ�������������������ڿ鼶�������У�����й¶��ȫ��������

```javascript
for(var i = 0; i < 5; ++i){
  //......
}

for(let j = 0; j < 5; ++j){
  //......
}

console.log(i);//5
console.log(j);//error: j is not defined
```

���µ�ES6����淶�У����鲻��ʹ��var��

## ģ���ַ���

�򵥵�˵�����ǿ����ø����ķ�ʽ���ѱ���(���߱��ʽ)�Ž��ַ������档

```javascript
//ES5
var x = '������' + year + '��' + month + '��' + day + '��';

//ES6
let x = `������${year}��${month}��${day}��`;
```

ԭ�����紦��8���ַ�����ģ���ַ���ֻҪ3���ַ���������ӽ��ա�

## for...of ѭ��

����һ��ѭ�����������Ƶ����������ã����Ա����������ÿ��Ԫ��

```javascript
var arr = [2, 3, 3, 3, 3];
var sum = 0;

//ES5
for(var i = 0; i < arr.length; ++i)
  sum += arr[i];
//or
for(var i in arr) sum += arr[i];

//ES6
for(let x of arr) sum += x;
```

����ѭ�����õ�`i`�ĵط�ȫ������`arr[i]`ʱ��������for...of����

## ��ͷ����

���Ƕ�������������һ�ַ�������ͷǰд��������ͷ��д����ֵ�����顣

```javascript
var arr = [2, 3, 4 ,5, 6];

//ES5
arr.map(function (x) {
  return x * x;
});

//ES6
arr.map(x => x * x);
```

˲����ˬ���١�

## �⹹��ֵ

�⹹��ֵ��������������ͬʱ�����������ֵ��

```javascript
let [a, b] = [1, 2];
console.log(a);//1
console.log(b);//2

let {x, y} = { y: 0, x: 1 };
console.log(x);//1
console.log(0);//0
```

������������һ�������ŵؽ���������ֵ��

```javascript
var a = 1, b = 2;

//ES5
var tmp = a;
a = b;
b = tmp;

//ES6
[a, b] = [b, a];
```

�����ϼ�ͷ�����������map()��������ȡDOMԪ�ص�ʱ��ͷ�����ˡ�

```javascript
var a, b, c;

//ES5
window.onload = function () {
  a = document.getElementById('a');
  b = document.getElementById('b');
  c = document.getElementById('c');
}

//ES6
window.onload = () => {
  [a, b, c] = ['a', 'b', 'c'].map(x => document.getElementById(x));
}
```

һ����˵��"�⹹��ֵ+map()+��ͷ����"�������ڶԲ�ͬ����ִ����ͬ����������˵����ı任��

```javascript
[x, y] = [x, y].map(x => Math.floor(x / blockSideLen));
```

�⹹��ֵ����for...ofѭ��Ҳ��һ��������

```javascript
let list = [
  ['Alex', 21],
  ['Bob', 20],
  ['David', 22]
];

window.onload = () => {
  for(let [name, age] of list)
    console.log(`${name} is ${age}.`);
}
```

ֻҪ��list�����д洢ÿ�����ӵı�������ӣ���ҳ�������б�Ϳ��������ַ���������

���⣬�����Ĳ�������Ҳ����ʹ�ý⹹��ֵ����Ϊ����ʵ����Ҳ��һ�ָ�ֵ��

����ĳЩ�¼��Ļص���������һ������������һ�����󣬶���ʱ������ֻ��Ҫ�õ����еļ���ֵ����ʱ��Ϳ����ں����Ĳ����������ý⹹��ֵ�����������⹹��

```javascript
//ES5
button.onclick = function (event) {
  var x = event.offsetX;
  var y = event.offsetY;
  //......
}

//ES6
button.onclick = ({ offsetX: x , offsetY: y }) => {
  //......
}
```

## ���ݽṹMap��Set

ǰ�涼���﷨�ϵ��Ż���������������ϵ��Ż���

��ES6�У��������˼������ݽṹ�����ڴ��漯��(Set)���ֵ��(Map)��Map��Set���ڲ�ʵ����Hash��Ҳ����˵���Խ���O(1)����ɾ�Ĳ顣���������Ҫ������λ�ò����ɾ��һ��Ԫ�ص�ʱ�临�Ӷ���O(n)��

���ԣ�����Ҫ��ͣ���ӻ�ɾ���ĳ��ϣ�Map��Set���������ó���

���⣬Map��SetҲ֧��for...ofѭ����Set���ص��ǵ���Ԫ�أ�Map���ص��Ǽ�ֵ�����顣

## ��β

��ʵ�ϣ�ES6�Ǵ���������֧�ֵ����°汾��Ҳ�����Ա仯�Ƚ϶�İ汾��ES6�ı仯��Զ��ֹ��Щ������class��async������ģ�黯�ȵȣ�����̫��Ķ���ֵ��ȥѧ��

��������ѧϰES6�����ӣ�

[��ECMAScript 6 ���Ž̡̳�by ��һ��](http://es6.ruanyifeng.com/)