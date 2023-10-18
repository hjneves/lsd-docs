# Flatpickr - um date picker

Componente para apresentaçãod e calendários em campos de input de datas
https://flatpickr.js.org/

## Instalação

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/flatpickr/dist/flatpickr.min.css">

<script src="https://cdn.jsdelivr.net/npm/flatpickr"></script>
```

## Utilização

```html
<div class="container">
      <form>
        <div class="form-group">
          <label for="formGroupExampleInput">Escolha uma data</label>
          <input
            type="text"
            class="form-control date"
            id="formGroupExampleInput"
            placeholder="Example input"
          />
        </div>
      </form>
    </div>
```

`.birthdate` é a classe de referência no campo de `<input>`

```js
flatpickr(".birthdate", {
        //enableTime: true,
        dateFormat: "Y-m-d",
        //defaultDate: new Date()
      });
      
```