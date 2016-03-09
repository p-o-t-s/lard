# Lard

Too simple, Too clean, Sass `flexbox` mixin library.

## Usage

Import `_lard.scss`

## Example

[CodePen](http://codepen.io/p-o-t-s/pen/LNpyOZ)


``` HTML
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <title>Lard Exaple</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
<div id="lard">
    <div class="lard-container">
        <div class="lard-container-row">
            <div class="lard-container-row__col"></div>
            <div class="lard-container-row__col"></div>
            <div class="lard-container-row__col"></div>
            <div class="lard-container-row__col"></div>
            <div class="lard-container-row__col"></div>
            <div class="lard-container-row__col"></div>
            <div class="lard-container-row__col lard-container-row__col--half"></div>
            <div class="lard-container-row__col lard-container-row__col--300"></div>
        </div>
    </div>
</div>
</body>
</html>
```

``` SCSS
/* Import Lard */
@import "../lard";

.lard-container {
  @include lard-container();
  &-row {
    @include lard-row();
    &__col {
      @include lard-columns(12) {
        background-color: cornflowerblue;
        border: 1px solid darkslategray;
        height: 3em;
      }
      &--half {
        @include lard-columns(2) {
          background-color: red;
        }
      }
      &--300 {
        @include lard-column(300px) {
          align-self: flex-end;
        }
      }
    }
  }
}
```

``` CSS
/* Import Lard */
.lard-container {
  margin-right: auto;
  margin-left: auto;
  padding-right: 10px;
  padding-left: 10px;
  max-width: 100%;
}

.lard-container-row {
  display: flex;
  flex-wrap: wrap;
  margin-right: -10px;
  margin-left: -10px;
}

.lard-container-row__col {
  flex: 0 0 8.33333%;
  max-width: 8.33333%;
  background-color: cornflowerblue;
  border: 1px solid darkslategray;
  height: 3em;
}

.lard-container-row__col--half {
  flex: 0 0 50%;
  max-width: 50%;
  background-color: red;
}

.lard-container-row__col--300 {
  flex-basis: 300px;
  max-width: 300px;
  align-self: flex-end;
}
```

## Feature

* `offset`
* `position`

## Browser support

`Lard` is, does not have any of the vendor prefix.

[Can I use...](http://caniuse.com/#search=flex)

## log

9 March 2016 : add `$no-garter` arguments for `-columns` and `-column`

## License

GPLv2 or later