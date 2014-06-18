#colorful-listmap


```
@mixin colorful-listmap($listmap){
  @each $item in $listmap{
    $key: nth($item, 1);
    $value: nth($item, 2);

    &-#{$key}{
      background: $value;
    }
  }
}
```
##Example Sass
```
%button{
  padding: 1em 0.328em;
  color: #FFFFFF;
  border: none;
  border-radius: 0.618em;
  margin: 0 auto;
  width: 11.09em;
}

$primary-color: #ff0000;
$secondary-color: #888888;
$tertiary-color: #313030;

$btn-color: (
  primary $primary-color,
  secondary $secondary-color,
  tertiary $tertiary-color
);

.button{
  @extend %button;
  @include colorful-listmap($btn-color);
}
```
##Output CSS
```
.button {
  padding: 1em 0.328em;
  color: #FFFFFF;
  border: none;
  border-radius: 0.618em;
  margin: 0 auto;
  width: 11.09em;
}

.button-primary {
  background: #ff0000;
}

.button-secondary {
  background: #888888;
}

.button-tertiary {
  background: #313030;
}
```
## To Install
```
$ bower install colorful-listmap --save
```
In your Grunt file(using Grunt-Sass):

```
sass: {
  dist: {
    files: {
      'application.css': 'sass/application.scss'
    },
    options: {
      includePaths: [
        './bower_components/colorful-listmap'
      ]
    }
  }
}
```
In your Sass manifest:

```
@import "colorful-listmap";
```

