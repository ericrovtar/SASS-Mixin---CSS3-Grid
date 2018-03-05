# Description

With browser support of CSS 3 Grids finally out there and usable, I needed a way to still support browsers who don't fully support CSS Grids. (Yes, I have a job where I have to support IE 11. I causes me much pain sometimes, but who doesn't like a good challenge?)

This SASS file provides a basic Grid class (`.grid`) that can be used throughout your application that utilizes Flexbox as a fallback for legacy browsers.

Further, I included a mix-in (`@include grid-columns(...)`)you can use to help define your column layout. The mix-in will create a class that contains all the appropriate CSS needed to generate the column template you specify. The class will be named with the prefix `col-`, then the total number of columns you specified, `--`, and finally the percentages of each column. (See below for a better example.)

# Usage

1. Import the `grid.scss` file into your SASS files.
2. Apply `.grid` to your container.
3. Use the `grid-columns` mix-in to define a column layout (ex: `@include grid-columns((25% 25% 50%))`).
4. Apply the class created by the mix-in (ex: `.col-3--25-25-50`) to the same container you applied the `.grid` class to.

# Example

```
// Import Grid
@import './grid.scss';

// Use grid-columns mix-in
@include grid-columns((10% 20% 30% 40%));
```

```
<!-- CONTAINER -->
<div class="grid col-4--10-20-30-40">
    <!-- COLUMN 1: 10% -->
    <div></div>

    <!-- COLUMN 2: 20% -->
    <div></div>

    <!-- COLUMN 3: 30% -->
    <div></div>

    <!-- COLUMN 4: 40% -->
    <div></div>
</div>
```

# Caveats

For now, this is pretty basic. I might expand it, but its intent was for basic grids to avoid unnecessary `table` usage.

# Questions

If you have any questions or suggestions, let me know. I'm happy to hear how you want to use this or what stops you from using it.

# Honorable Mentions

This solution makes use of Brian Franco's excellent <a href="https://github.com/mastastealth/sass-flex-mixin" target="_blank">flexbox mix-ins</a>. Seriously, if you're note using these to ensure legacy browser support of flexbox, you're missing out. With so many revisions to the spec, this makes it very manageable.

# Happy coding