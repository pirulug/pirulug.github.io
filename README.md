# 1
## Tablas

|hola|hola|
|---|---|
|hola|hola|

### code

```javascript
function previewValue(){
  const contenido = document.getElementById('pr-editor-content').value;
  document.getElementById("pr-editor-preview").innerHTML = marked(contenido);
  console.log(md.render('# holas'));
}
```
#### citas

> esta es una cita

##### 5
###### 6

**Negrito**

*Italico*

---
1. lista
2. lista
---
* lista
* lista
---
- [x] List item
- [ ] List item

[imagen](https://cde.laprensa.e3.pe/ima/0/0/2/3/8/238082.jpg)

![imagen](https://cde.laprensa.e3.pe/ima/0/0/2/3/8/238082.jpg)
