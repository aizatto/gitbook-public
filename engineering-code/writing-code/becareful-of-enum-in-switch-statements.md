# Becareful of enum in switch statements

If an `enum` is in more than one `switch` statement. Consider making a factory class which returns singleton class for the enum value.

For example, if you only have one instance of this, its ok:

```text
function getName(Color $color) {
  switch($color) {
    case Color::RED:
      return 'Red';

    case Color::BLUE:
      return 'Blue';
  }
}
```

But if you add another function, then make a factory class which returns an instance.

```text
function getRGB(Color $color) {
  switch($color) {
    case Color::RED:
      return '#FF0000';

    case Color::BLUE:
      return '#0000FF';
  }
}
```

Do this instead:

```text
class ColorFactory {
  public static function get(ColorEnum $color) {
    switch ($color) {
      case ColorEnum::RED:
        return ColorRed::get();

      case ColorEnum::Blue:
        return ColorBlue::get();
    }
  }
}

class Color extends Color {
  public function get(ColorEnum $color) {
    switch ($color) {
      case ColorEnum::RED:
        return ColorRed::get();

      case ColorEnum::Blue:
        return ColorBlue::get();
    }
  }
}

abstract class ColorBase extends Color {
  public function getName(): string;
  public function getRGB(): string;
}

final class ColorRed extends Color {
  public function getID(): Color {
    return Color::RED;
  }

  public function getName(): string {
    return 'Red';
  }

  public function getRGB(): string {
    return '#FF0000';
  }
}

final class ColorBlue extends Color {
  public function getID(): Color {
    return Color::Blue;
  }

  public function getName(): string {
    return 'Blue';
  }

  public function getRGB(): string {
    return '#0000FF';
  }
}

function main() {
  $color = ColorFactory::get($color)
  return $color->getName();
}
```

Yes there is more code, but its easier to manage the code. When adding a new Enum you are not required to remember which files to update, the compiler will catch any undefined functions.

