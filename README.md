sass-em-converter
=================

Diddy sass helper to generate CSS in EMs when your designers specify pixels

```scss

  // Helper to convert the designers' px specifications into EMs:
  // Eg: H2 { font-size: em(28px); }
  @function em( $px, $basePx: $baseFontPx ) {
    $px:     $px     / ($px     * 0 + 1);   // Strip off units to be sure we have a plain number. (eg: 20px -> 20)
    $basePx: $basePx / ($basePx * 0 + 1);   // Strip off units to be sure we have a plain number. (eg: 20px -> 20)
    @return  $px / $basePx * 1em;           // The *1em ensures we return an EM number.
  }

  $baseFontPx: 16px;

  // Sample usage:
  H1 {
      font-size: em(32px);
      SMALL {
        font-size: em(28px,32px)
      }
  }

```
