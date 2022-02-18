<template>
  <div>
    <Nav />
    <Dashboard/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
  layout: 'empty',
  head() {
    return {
      link: [
        { rel: "preconnect", href:"https://fonts.googleapis.com" },
        { rel: "preconnect", href: "https://fonts.gstatic.com", crossorigin: true},
        { href: "https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&display=swap", rel: "stylesheet"},
        { href: "https://fonts.googleapis.com/icon?family=Material+Icons", rel: "stylesheet" }
      ]
    }
  }
})
</script>
<style >

:root {
    
    /* Colors */

    --clr-dark: 0 0% 31%;
    --clr-light: 0 0% 94.9%;
    --clr-white: 0 0% 100%;

    --clr-primary: 214 84% 56%;
    --clr-secondary: 0 0% 20%;
    --clr-tertiary: 0 0% 51%;
    --clr-accent1: 0 0% 77%;
    --clr-accent2: 0 0% 88%;

    /* Font Sizes */
        /* consider using clamp for your custom fonts sizes
        Also, consider using vmin and vmax
        */
        --fs-900: clamp(5rem, calc(7vw + 1rem), 9.375rem);
        --fs-800: clamp(2rem, calc(6vw + 1rem), 3.5rem);
        --fs-700: clamp(1.8rem, calc(5vw + 1rem), 2.25rem);
        --fs-600: clamp(1.5rem, calc(4vw + 1rem), 1.875rem);
        --fs-500: clamp(0.9375rem, calc(3vw + 1rem), 1.5rem);
        --fs-400: clamp(0.625rem, calc(1vw + 0.7625rem), 1.125rem);
        --fs-300: clamp(0.725rem, calc(0.5vw + 1rem), 1rem);
        --fs-200: clamp(0.6rem, calc(0.5vw + 0.5rem), 0.875rem);

    /* Font families */
    --ff-sans-cond: 'Inter', sans-serif;

    /* Font weight */
    --fw-reg: 500;
    --fw-bold: 600;
    --fw-bolder: 700;
}

/* ------------------------- */
/* ~~~~~~~ Reset ~~~~~~~ */
/* ------------------------- */

/* Box sizing */

*,
*::before,
*::after {
    box-sizing: border-box;
}

/* Reset Margins */

body,
h1,
h2,
h3,
h4,
h5,
h6,
p,
figure,
picture {
    margin: 0;
    padding: 0;
}

h1,
h2,
h3,
h4,
h5,
h6,
p {
    font-weight: var(--font-weight, 400);
}

/*  Set up the body */
body {
    font-family: var(--ff-sans-cond);
    font-size: 16px;
    font-weight: var(--fw-reg);
    background-color: hsl(var(--clr-white));
    color: hsl(var(--clr-dark));
    line-height: 1.5;
    min-height: 100vh;
    margin: 0;
    padding: 0;
    /* display: grid;
    grid-template-rows: min-content 1fr; */
}

/* Make images easier to work with */
img,
picture {
    max-width: 100%;
    /* display: block; */
}

/* Make forms easier to work with  */
input,
button,
textarea,
select {
    font: inherit;
}

/* Remove text decoration */
a {
  text-decoration: unset;
  color: inherit;
}

/* Remove animations for people who turned them off */
@media (prefers-reduced-motion: reduce) {
    *,
    *::before,
    *::after {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
        scroll-behavior: auto !important
    }
}

/* ------------------------- */
/* ~~~~~~~ Utilities ~~~~~~~ */
/* ------------------------- */

/* general */

.flex {
    display: flex;
    gap: var(--gap, 1rem);
}

.grid {
    display: grid;
    gap: var(--gap, 1rem);
}

.d-block {
    display: block;
}

.d-none {
    display: none;
    transition: ease-in-out 3s;
}
/* .flow > *:not(:first-child) {
    margin-top: 1rem; 
} */
.flow > * + * {
    margin-top: var(--flow-space, 1rem);
}
.flow > *:where(:not(:first-child)) {
    margin-top: var(--flow-space, 1rem);
}

.flow--space-small {
    --flow-space: 0.5rem
}

.container {
    padding: 1rem;
    margin: 0 auto;
    /* max-width: 90rem; */
}

.sr-only { /*screen reader only */
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0,0,0,0);
    white-space: nowrap;
    border: 0;
}

.skip-to-content {
    background: hsl( var(--clr-white));
    color: hsl(var(--clr-dark));
    padding: 0.5em 1em;
    margin-inline: auto;
    position: absolute;
    z-index: 250;
    transform: translateY(-100%);
    opacity: 0;
    transition: opacity 500ms linear, transform 750ms ease-in-out

}
.skip-to-content:focus {
    opacity: 1;
    transform: translateY(0);
}

/* colors */
.bg-dark { background-color: hsl(var(--clr-dark))}
.bg-light { background-color: hsl(var(--clr-light))}
.bg-white { background-color: hsl(var(--clr-white))}

.bg-primary { background-color: hsl(var(--clr-primary))}
.bg-secondary { background-color: hsl(var(--clr-secondary))}
.bg-tertiary { background-color: hsl(var(--clr-tertiary))}
.bg-accent1 { background-color: hsl(var(--clr-accent1))}
.bg-accent2 { background-color: hsl(var(--clr-accent2))}

.text-dark { color: hsl(var(--clr-dark))}
.text-light { color: hsl(var(--clr-light))}
.text-white { color: hsl(var(--clr-white))}

.text-primary { color: hsl(var(--clr-primary))}
.text-secondary { color: hsl(var(--clr-secondary))}
.text-tertiary { color: hsl(var(--clr-tertiary))}
.text-accent1 { color: hsl(var(--clr-accent1))}
.text-accent2 { color: hsl(var(--clr-accent2))}

/* typography */

.ff-sans-cond { font-family: var(--ff-sans-cond); } 

.letter-spacing-1 { letter-spacing: 4.75px; } 
.letter-spacing-2 { letter-spacing: 2.7px; } 
.letter-spacing-3 { letter-spacing: 2.35px; }

.fw-reg { font-weight: var(--fw-reg);}
.fw-bold { font-weight: var(--fw-bold);}
.fw-bolder { font-weight: var(--fw-bolder);}

.uppercase { text-transform: uppercase; }

.fs-900 { font-size: var(--fs-900); }
.fs-800 { font-size: var(--fs-800); }
.fs-700 { font-size: var(--fs-700); }
.fs-600 { font-size: var(--fs-600); }
.fs-500 { font-size: var(--fs-500); }
.fs-400 { font-size: var(--fs-400); }
.fs-300 { font-size: var(--fs-300); }
.fs-200 { font-size: var(--fs-200); }


.fs-900,
.fs-800,
.fs-700,
.fs-600 {
    line-height: 1.1;
}

.mx-7rem {
    margin-left: 7rem;
    margin-right: 7rem;
}

hr {
    border: none;
    background: #EAECF0;
    height: 1px;
}
</style>
