# Angular: A Complete Version History & Expert Reference

> From AngularJS's digest cycle to Angular 22's signal-driven, zoneless, OnPush-default architecture —
> this document traces every major release, the reasoning behind each shift, and the milestones that
> define the framework's identity.

---

## Table of Contents

- [Three Eras of Angular](#three-eras-of-angular)
- [Complete Version Timeline](#complete-version-timeline)
- [LTS Support Matrix](#lts-support-matrix)
- [Why Angular 3 Was Never Released](#why-angular-3-was-never-released)
- [Version Deep Dives](#version-deep-dives)
  - [AngularJS 1.x — October 2010](#angularjs-1x--october-2010)
  - [Angular 2.0 — September 2016](#angular-20--september-2016)
  - [Angular 4.0 — March 2017](#angular-40--march-2017)
  - [Angular 5.0 — November 2017](#angular-50--november-2017)
  - [Angular 6.0 — May 2018](#angular-60--may-2018)
  - [Angular 7.0 — October 2018](#angular-70--october-2018)
  - [Angular 8.0 — May 2019](#angular-80--may-2019)
  - [Angular 9.0 — February 2020](#angular-90--february-2020)
  - [Angular 10.0 — June 2020](#angular-100--june-2020)
  - [Angular 11.0 — November 2020](#angular-110--november-2020)
  - [Angular 12.0 — May 2021](#angular-120--may-2021)
  - [Angular 13.0 — November 2021](#angular-130--november-2021)
  - [Angular 14.0 — June 2022](#angular-140--june-2022)
  - [Angular 15.0 — November 2022](#angular-150--november-2022)
  - [Angular 16.0 — May 2023](#angular-160--may-2023)
  - [Angular 17.0 — November 2023](#angular-170--november-2023)
  - [Angular 18.0 — May 2024](#angular-180--may-2024)
  - [Angular 19.0 — November 2024](#angular-190--november-2024)
  - [Angular 20.0 — May 28, 2025](#angular-200--may-28-2025)
  - [Angular 21.0 — November 20, 2025](#angular-210--november-20-2025)
  - [Angular 22.0 — June 3, 2026](#angular-220--june-3-2026)
- [Architectural Evolution at a Glance](#architectural-evolution-at-a-glance)
- [Reactivity: From Digest Cycle to Signals](#reactivity-from-digest-cycle-to-signals)
  - [Stage 1 — AngularJS Digest Cycle (2010–2016)](#stage-1--angularjs-digest-cycle-20102016)
  - [Stage 2 — Zone.js Interception (2016–2023)](#stage-2--zonejs-interception-20162023)
  - [Stage 3 — Signals (2023–present)](#stage-3--signals-2023present)
- [Key Concepts Glossary](#key-concepts-glossary)
- [TypeScript Compatibility Matrix](#typescript-compatibility-matrix)
- [Major Breaking Changes & Migration Highlights](#major-breaking-changes--migration-highlights)
- [Ecosystem & Tooling Evolution](#ecosystem--tooling-evolution)
- [Summary: The Angular Trajectory](#summary-the-angular-trajectory)
- [Angular Mastery Course](#angular-mastery-course)
- [Further Reading](#further-reading)

---

## Three Eras of Angular

Angular's history divides cleanly into three architectural eras, each defined by a fundamental rethinking of how applications are built:

```
Era 1 — The Classic Era (AngularJS 1.x – Angular 8)
  Two-way binding, digest cycles, NgModules, Zone.js, and class-based component logic.

Era 2 — The Ivy Era (Angular 9 – Angular 15)
  New compiler and runtime (Ivy), tree-shakable providers, standalone components,
  differential loading, and the beginning of the module-less paradigm.

Era 3 — The Reactive Signal Era (Angular 16 – present)
  Signal-based reactivity, zoneless change detection, incremental hydration,
  Signal Forms, and OnPush as the new default. Zone.js becomes optional, then unnecessary.
```

---

## Complete Version Timeline

| Version        | Release Date      | Era        | TypeScript | Key Theme                                         |
|----------------|-------------------|------------|------------|---------------------------------------------------|
| AngularJS 1.x  | October 2010      | Classic    | —          | Two-way binding, DI, MVC, digest cycle            |
| Angular 2.0    | September 2016    | Classic    | 2.x        | Full rewrite — components, RxJS, Zone.js          |
| Angular 3.0    | *(skipped)*       | —          | —          | Version skipped for router package alignment      |
| Angular 4.0    | March 2017        | Classic    | 2.1+       | Smaller bundles, improved templates, Animations   |
| Angular 5.0    | November 2017     | Classic    | 2.3+       | HttpClient, Build Optimizer, PWA groundwork       |
| Angular 6.0    | May 2018          | Classic    | 2.7+       | CLI workspaces, Ivy preview seeded, RxJS 6        |
| Angular 7.0    | October 2018      | Classic    | 3.1+       | Virtual scrolling, CDK drag-and-drop              |
| Angular 8.0    | May 2019          | Classic    | 3.4+       | Ivy opt-in preview, differential loading          |
| Angular 9.0    | February 2020     | Ivy        | 3.6+       | **Ivy default** — smaller bundles, better debug   |
| Angular 10.0   | June 2020         | Ivy        | 3.9+       | Strict mode, warnings cleanup, TypeScript 3.9     |
| Angular 11.0   | November 2020     | Ivy        | 4.0+       | HMR, logging, Webpack 5 experimental             |
| Angular 12.0   | May 2021          | Ivy        | 4.2+       | Full Ivy, nullish coalescing, Angular DevTools    |
| Angular 13.0   | November 2021     | Ivy        | 4.4+       | No IE11, persistent build cache, ESM only         |
| Angular 14.0   | June 2022         | Ivy        | 4.6+       | **Standalone components**, typed reactive forms   |
| Angular 15.0   | November 2022     | Ivy        | 4.8+       | Standalone APIs stable, image directive           |
| Angular 16.0   | May 2023          | Signal     | 5.0+       | **Signals introduced**, Optional Zone.js          |
| Angular 17.0   | November 2023     | Signal     | 5.2+       | New control flow syntax (`@if`, `@for`), `@defer` |
| Angular 18.0   | May 2024          | Signal     | 5.4+       | Stable control flow, Material 3, Zoneless preview |
| Angular 19.0   | November 2024     | Signal     | 5.5+       | Standalone by default, incremental hydration preview |
| Angular 20.0   | May 28, 2025      | Signal     | 5.7+       | **Signals fully stable**, Zoneless dev preview    |
| Angular 21.0   | November 20, 2025 | Signal     | 5.7+       | **Zoneless standard**, Vitest default, ARIA CDK   |
| Angular 22.0   | June 3, 2026      | Signal     | 5.8+       | **Signal Forms stable**, OnPush default, Resource API stable |

---

## LTS Support Matrix

Angular follows a **6-month major release cadence** (May and November) with **18 months of total support** per version: 6 months active + 12 months LTS.

| Version   | Released          | Active Support Ends | LTS Ends      | Status         |
|-----------|-------------------|---------------------|---------------|----------------|
| v16       | May 2023          | November 2023       | May 2025      | End of Life    |
| v17       | November 2023     | May 2024            | November 2025 | End of Life    |
| v18       | May 2024          | November 2024       | May 2026      | End of Life    |
| v19       | November 2024     | May 2025            | November 2026 | LTS            |
| v20       | May 2025          | November 2025       | May 2027      | LTS            |
| v21       | November 2025     | May 2026            | November 2027 | LTS            |
| v22       | June 2026         | December 2026       | May 2028      | **Active**     |

> For projects stuck on EOL versions, [HeroDevs NES](https://www.herodevs.com/support/angular-nes) provides extended commercial support.

---

## Why Angular 3 Was Never Released

When Angular 2 shipped, the `@angular/router` package was already at version 3.x — ahead of the rest of the framework. To eliminate this confusing asymmetry, the team skipped straight from Angular 2 to Angular 4, synchronizing all packages under a single major version number. The `SEMVER` strategy Angular adopted from that point forward means breaking changes only ship in major versions, predictably every six months.

---

## Version Deep Dives

---

### AngularJS 1.x — October 2010

The framework that changed the web. AngularJS introduced declarative HTML templates, two-way data binding via `$scope`, and a built-in Dependency Injection container — concepts previously only found in server-side MVC frameworks.

**Core innovations:**
- **Digest cycle:** A dirty-checking loop that propagated changes across the entire scope tree. Powerful, but expensive at scale.
- **Directives:** `ng-repeat`, `ng-if`, `ng-model` made HTML a first-class programming language for the DOM.
- **$http service:** Introduced promise-based HTTP communication in the browser.
- **Two-way binding:** `{{ expression }}` and `ng-model` kept view and model in sync automatically.

**Why it mattered:** AngularJS proved that structured application development was possible in the browser, without jQuery spaghetti. It catalyzed the modern JavaScript framework ecosystem.

**Why it ended:** The digest cycle had fundamental performance ceilings. Two-way binding made data flow unpredictable at scale. These weren't fixable incrementally — they required a ground-up redesign.

---

### Angular 2.0 — September 2016

A complete, non-backward-compatible rewrite. Angular 2 drew lessons from AngularJS's pain points and bet everything on TypeScript, components, and RxJS.

**Core innovations:**
- **Component-based architecture:** Every UI element is a component with its own template, styles, and logic. `NgModule` groups components, directives, pipes, and services.
- **TypeScript as the primary language:** Static types, decorators (`@Component`, `@Injectable`), and IDE intelligence became core to the Angular developer experience.
- **Zone.js:** Monkey-patches async APIs (setTimeout, Promise, XHR) to trigger change detection automatically. Elegant at the time; a performance bottleneck later.
- **RxJS integration:** Observables power HTTP, forms, router events, and component communication.
- **Ahead-of-Time (AoT) compilation (experimental):** Templates compiled at build time, not at runtime.

---

### Angular 4.0 — March 2017

**Theme: Smaller, faster, cleaner.**

- Reduced generated bundle sizes by ~60% compared to Angular 2 in some cases.
- `*ngIf` gained `else` and `then` block support: `*ngIf="condition; else fallback"`.
- `@angular/animations` extracted into its own package — include only when needed.
- `<ng-template>` replaced `<template>` (now conflicts with the HTML5 spec).
- TypeScript 2.1+ support introduced strict null checks compatibility.

---

### Angular 5.0 — November 2017

**Theme: Production-grade HTTP, build tools, and Universal.**

- **HttpClient:** Replaced `Http` with a new `HttpClient` module offering typed responses, interceptors, progress events, and cleaner error handling.
- **Build Optimizer:** A post-compilation tool that removed Angular decorators from production builds, shrinking bundles further.
- **Angular Universal improvements:** Better server-side rendering lifecycle hooks.
- **Progressive Web App (PWA) foundation:** `@angular/service-worker` package introduced.
- **`@angular/platform-server`** improvements laid the groundwork for Angular's serious SSR capabilities.

---

### Angular 6.0 — May 2018

**Theme: Unified CLI, tree-shakable providers, ecosystem modernization.**

- **CLI Workspaces:** `angular.json` replaced `.angular-cli.json`, enabling multiple projects in a single repository (monorepo support).
- **Tree-shakable providers:** `{ providedIn: 'root' }` allows services to be automatically removed from bundles if unused.
- **RxJS 6:** Required migration from `rxjs/operator` imports to `rxjs/operators`. The `rxjs-compat` package bridged the gap.
- **Ivy first mention:** The team publicly described Ivy as the next-generation rendering engine under development.
- **Angular Elements:** Package for wrapping Angular components as native custom elements / web components.
- **ng update / ng add:** CLI commands for automated migrations and schematic-based package integration.

---

### Angular 7.0 — October 2018

**Theme: CDK, CLI polish, and runtime performance.**

- **Virtual Scrolling** (`CdkVirtualScrollViewport`): Render only visible items in large lists — a critical performance tool.
- **Drag and Drop** (`CdkDragDrop`): First-class drag-and-drop primitives in the CDK.
- **CLI Prompts:** `ng new` and `ng add` became interactive, guiding developers through setup decisions.
- **`@angular/material` and `@angular/cdk`** reached maturity together.
- Bundle budget warnings by default in the CLI.

---

### Angular 8.0 — May 2019

**Theme: Ivy opt-in, differential loading, modern dynamic imports.**

- **Ivy Opt-In Preview:** Developers could enable Ivy via `"enableIvy": true` in `tsconfig.json`. Not yet production-ready.
- **Differential Loading:** The CLI now generates two bundles — ES2015+ for modern browsers and ES5 for legacy. Each browser loads only what it needs, reducing payload for the majority of users.
- **Dynamic Imports for Lazy Routes:** `loadChildren: () => import('./feature/feature.module').then(m => m.FeatureModule)` replaced string-based lazy loading.
- **Web Workers:** First-class CLI support for offloading CPU-intensive work off the main thread.
- **Bazel support (experimental):** Opt-in build system for extremely large monorepos.

---

### Angular 9.0 — February 2020

**Milestone: Ivy becomes the default rendering engine.**

This is one of Angular's most significant version boundaries. Ivy replaced the View Engine (VE) compiler and runtime that had powered Angular since v2.

**What Ivy changed:**
- **Locality principle:** Each component compiles independently. VE required global knowledge of the entire application; Ivy does not.
- **Smaller bundles:** Tree-shaking became dramatically more effective because Ivy's output is highly modular.
- **Better debugging:** `ng.getComponent(element)` and `ng.applyChanges()` available in dev mode from the console.
- **Faster testing:** `TestBed` was rewritten to compile components lazily, dramatically speeding up unit test suites.
- **`ngcc`:** Angular Compatibility Compiler converted existing View Engine libraries to Ivy-compatible format during `npm install`.

**TypeScript:** 3.6+

---

### Angular 10.0 — June 2020

**Theme: Strict mode and tooling quality.**

- **Strict mode:** `ng new --strict` enabled stricter TypeScript, template, and bundle-size checks out of the box. Teams adopting this caught a class of bugs at compile time.
- **Date Range Picker:** New `<mat-date-range-input>` and `<mat-date-range-picker>` in Angular Material.
- **TypeScript 3.9:** Required for improved type inference.
- **Deprecation warnings:** Aggressive warnings for patterns planned for removal in v11/v12 (e.g., `CommonModule` in lazy routes using Ivy).
- Smaller package footprint for production builds.

---

### Angular 11.0 — November 2020

**Theme: Hot Module Replacement, stricter standards.**

- **Hot Module Replacement (HMR):** `ng serve --hmr` enabled fast CSS/component refresh without full page reloads.
- **Automatic font inlining:** CLI inlines critical fonts referenced in `index.html` at build time, removing render-blocking requests.
- **Stricter typing enforced** across template expressions.
- **Webpack 5 experimental:** Opt-in support for Module Federation (micro-frontends).
- **TypeScript 4.0:** Support for variadic tuple types and labeled tuple elements.

---

### Angular 12.0 — May 2021

**Milestone: View Engine officially removed. Full Ivy adoption.**

- **Nullish coalescing** in templates: `{{ user?.name ?? 'Anonymous' }}`.
- **Strict null checks** now default in new projects.
- **Angular DevTools:** Browser extension for component tree inspection, change detection profiling, and dependency injection visualization.
- **Inline Sass:** Component styles could be written as inline Sass in `styles` metadata.
- **Webpack 5 stable** (though still not the default yet).
- **`ng serve` with ESBuild** experiments began.

---

### Angular 13.0 — November 2021

**Theme: Modern baseline, simplified APIs.**

- **IE11 support dropped:** The team could remove significant polyfill overhead and modernize the build pipeline.
- **Persistent build cache:** The CLI now caches compilation results across runs, cutting cold build times dramatically for large projects.
- **`createComponent` API:** Replaces `ComponentFactoryResolver` — dynamic components now created without factories.
- **`ViewContainerRef.createEmbeddedView`** improvements.
- **ESM-only package output:** `@angular/core` and peers ship as pure ESM.
- **TypeScript 4.4+:** Support for using `Symbol` as index signatures and `exactOptionalPropertyTypes`.

---

### Angular 14.0 — June 2022

**Milestone: Standalone components — the beginning of the module-less Angular.**

This release introduced the most transformative API addition since Ivy: standalone components, directives, and pipes that declare their own dependencies without belonging to an `NgModule`.

```typescript
@Component({
  standalone: true,
  imports: [CommonModule, RouterModule],
  template: `<h1>Hello</h1>`
})
export class AppComponent {}
```

- **Strictly typed reactive forms:** `FormControl<string>`, `FormGroup<{name: FormControl<string>}>`. Type inference all the way through.
- **`inject()` function:** Dependency injection outside constructors — usable in factory functions, guards, interceptors.
- **`bootstrapApplication()`:** Bootstrap an app from a standalone component, no `AppModule` needed.
- **Streamlined page title strategy:** Router-level title binding.
- **TypeScript 4.6+**

---

### Angular 15.0 — November 2022

**Theme: Standalone APIs reach maturity.**

- **Standalone APIs stable:** `provideRouter()`, `provideHttpClient()`, `provideAnimations()` — functional alternatives to `RouterModule.forRoot()` and friends.
- **Directive composition API:** Apply multiple directives to a component via `hostDirectives`.
- **NgOptimizedImage directive (`NgOptimizedImage`):** Automatic lazy loading, intrinsic size hints, and priority attributes for performance-critical images.
- **Stack traces improved:** Angular-generated errors now show real user code frames, not Angular internals.
- **TypeScript 4.8+**

---

### Angular 16.0 — May 2023

**Milestone: Signals introduced — the dawn of the Reactive Signal Era.**

Angular Signals introduced a new fine-grained reactivity primitive that does not require Zone.js to schedule change detection.

```typescript
// Signal-based state
const count = signal(0);
const doubled = computed(() => count() * 2);

effect(() => {
  console.log(`Count is now: ${count()}`);
});

// Mutations
count.set(5);
count.update(n => n + 1);
```

- **`signal()`, `computed()`, `effect()`:** Core reactive primitives (developer preview).
- **`toSignal()`, `toObservable()`:** Interop between Signals and RxJS Observables.
- **Signal-based inputs (experimental):** `input()` as a typed, reactive replacement for `@Input()`.
- **Required inputs:** `@Input({ required: true })` — compile-time enforcement.
- **Optional Zone.js:** New experimental `ChangeDetectionStrategy.OnPushSignals` approach.
- **Server-Side Rendering hydration (developer preview):** Non-destructive hydration replaces full client-side re-render on SSR apps.
- **esbuild-based build pipeline (developer preview):** 72% faster cold builds, 20% faster incremental builds vs Webpack.
- **TypeScript 5.0+**

---

### Angular 17.0 — November 2023

**Milestone: New template syntax, `@defer`, and a visual identity refresh.**

Angular shipped a completely redesigned website (`angular.dev`), a new logo, and a new default application template that uses standalone components and the new control flow syntax by default.

**New built-in control flow syntax (developer preview → stable in 18):**

```html
<!-- Old structural directives -->
<div *ngIf="isLoggedIn; else guest">Welcome</div>
<li *ngFor="let item of items; trackBy: trackById">{{ item.name }}</li>

<!-- New built-in control flow -->
@if (isLoggedIn) {
  <div>Welcome</div>
} @else {
  <ng-container *ngTemplateOutlet="guest" />
}

@for (item of items; track item.id) {
  <li>{{ item.name }}</li>
} @empty {
  <li>No items found.</li>
}
```

**`@defer` blocks:** Lazy-load component trees based on interaction, visibility, idle state, or timer:

```html
@defer (on viewport) {
  <heavy-chart />
} @placeholder {
  <div>Loading chart...</div>
} @loading (minimum 500ms) {
  <spinner />
} @error {
  <p>Failed to load chart.</p>
}
```

- **esbuild builder stable:** Now the default for `ng build` and `ng serve`.
- **View Transition API support.**
- **TypeScript 5.2+**

---

### Angular 18.0 — May 2024

**Theme: Stabilization of new control flow, Material 3, Zoneless preview.**

- **Built-in control flow stable:** `@if`, `@for`, `@switch`, `@empty`, `@defer` are production-ready.
- **Angular Material 3 (M3) stable:** Updated theming system based on Material Design 3 tokens.
- **Zoneless change detection (experimental):** Apps can now run without Zone.js by calling `provideExperimentalZonelessChangeDetection()`. Angular relies entirely on Signals and `markForCheck()` calls.
- **`@let` template variables (developer preview):** Declare local template variables without `*ngIf as`.
- **TypeScript 5.4+**
- **Partial hydration (developer preview):** Combine SSR with `@defer` to hydrate only what the user interacts with.

---

### Angular 19.0 — November 2024

**Milestone: Standalone is now the default.**

- **Standalone by default:** `ng generate component` no longer adds components to an `NgModule`. All new components, directives, and pipes are standalone unless `--no-standalone` is explicitly passed.
- **Incremental hydration (developer preview):** Builds on `@defer` to selectively hydrate parts of an SSR page only when they enter the viewport or receive user interaction.
- **Route-level render mode (developer preview):** Configure SSR, SSG, or CSR per individual route.
- **Hot Module Replacement for components:** Full HMR support for component state (not just styles).
- **`linkedSignal()` (developer preview):** A writable signal whose default value is computed from another signal — bridges the gap between `computed()` (read-only) and `signal()` (independent).
- **`resource()` API (developer preview):** Declarative async resource fetching driven by Signals.
- **TypeScript 5.5+**

---

### Angular 20.0 — May 28, 2025

**Milestone: Signals fully stable. The reactive foundation is complete.**

Angular 20 marks the point where the entire Signal primitive set graduates from experimental or developer preview to **stable and recommended for production**.

**Signals fully stable:**
- `signal()`, `computed()`, `effect()`, `linkedSignal()`, `toSignal()`, `toObservable()`
- Signal-based `input()`, `output()`, `viewChild()`, `viewChildren()`, `contentChild()`, `contentChildren()`
- All signal primitives are now the recommended way to write new Angular code.

**Zoneless change detection → developer preview:**
- `provideZonelessChangeDetection()` replaces `provideExperimentalZonelessChangeDetection()`.
- Fully functional for new applications.
- Smaller bundles: removing Zone.js eliminates ~10–25kb from most apps.

**Incremental hydration → stable:** Production-ready SSR hydration via `@defer` scopes.

**Route-level render mode → stable:** Per-route SSR/SSG/CSR configuration production-ready.

**Developer Experience:**
- Angular DevTools gains a Signal dependency graph visualizer.
- `effect()` cleanup functions supported.
- TypeScript 5.7+

---

### Angular 21.0 — November 20, 2025

**Milestone: Zoneless becomes the standard. Vitest replaces Karma. Angular ARIA.**

- **Zoneless change detection is the new standard:** New Angular projects no longer include `zone.js` by default. Angular drives change detection entirely through Signals and `markForCheck()`.
- **Signal Forms (experimental):** A new forms API built natively on Signals — reactive as `ReactiveFormsModule` but as ergonomic as template-driven forms.
  ```typescript
  const form = signalForm({
    name: signalInput('', { validators: [Validators.required] }),
    email: signalInput(''),
  });
  ```
- **Vitest stable default test runner:** Replaces Karma/Jasmine for new projects. 5–10× faster test runs in large workspaces, native ESM support, and no browser required for most tests.
- **Angular ARIA (CDK):** A new CDK module shipping accessible component primitives (accordion, combobox, tabs, menus) with correct ARIA roles, keyboard interactions, and focus management out of the box.
- **Angular CLI MCP Server:** The Angular CLI ships an [MCP (Model Context Protocol)](https://modelcontextprotocol.io/) server, enabling AI assistants to generate, scaffold, and refactor Angular code with deep framework awareness.
- **TypeScript 5.7+**

---

### Angular 22.0 — June 3, 2026

**Milestone: Signal Forms stable, OnPush is now the default, Resource API production-ready.**

Angular 22 is a **consolidation release** — the experimental features of the past three versions graduate to stable, and a significant default changes for all new components.

- **`OnPush` change detection is now the default strategy.** New components generated by the CLI use `ChangeDetectionStrategy.OnPush`. Existing apps are not broken (automatic migration via `ng update` sets `Default` explicitly if not already set).
  ```typescript
  // Angular 22+ generated component
  @Component({
    selector: 'app-hero',
    changeDetection: ChangeDetectionStrategy.OnPush, // now the default
    template: `...`
  })
  export class HeroComponent {}
  ```
- **Signal Forms → stable:** Includes the full Submission API, schema-based validation via `validateStandardSchema`, conditional CSS classes, and interop with existing `ReactiveFormsModule`.
- **`resource()`, `rxResource()`, `httpResource()` → stable:** Reactive async data fetching driven by Signals is now production-ready.
  ```typescript
  // httpResource: reactive HTTP — re-fetches automatically when signal changes
  readonly userId = signal(1);
  readonly user = httpResource(() => `/api/users/${this.userId()}`);
  // user.value(), user.isLoading(), user.error() all available as signals
  ```
- **Vitest as the default test runner** for all new CLI projects.
- **WebMCP integration:** Angular CLI's MCP server extended for in-browser dev tooling.
- **TypeScript 5.8+**

---

## Architectural Evolution at a Glance

```
CHANGE DETECTION MODEL
─────────────────────────────────────────────────────────────────────────────
AngularJS     │  Digest cycle — checks all $scope watchers repeatedly
Angular 2–8   │  Zone.js patches async APIs → triggers full tree check
Angular 9–15  │  Zone.js + OnPush + Ivy's efficient change marking
Angular 16–19 │  Signals (developer preview) alongside Zone.js
Angular 20–21 │  Signals stable + Zoneless (developer preview / standard)
Angular 22+   │  Signals + Zoneless + OnPush default — Zone.js optional legacy


TEMPLATE COMPILATION
─────────────────────────────────────────────────────────────────────────────
AngularJS     │  Runtime $compile — interprets templates in the browser
Angular 2–8   │  JiT (default) or AoT — AoT optional, heavy output
Angular 9–15  │  Ivy Compiler — locality, tree-shakable, composable output
Angular 16+   │  Ivy + esbuild pipeline — fast incremental builds


MODULE SYSTEM
─────────────────────────────────────────────────────────────────────────────
Angular 2–13  │  NgModule required — declarations, imports, providers, exports
Angular 14    │  Standalone components introduced (opt-in)
Angular 15    │  Standalone APIs stable (provideRouter, provideHttpClient)
Angular 19+   │  Standalone is the default — NgModule is legacy


FORMS MODEL
─────────────────────────────────────────────────────────────────────────────
Angular 2+    │  Template-driven forms (ngModel) and Reactive Forms (RxJS)
Angular 14    │  Strictly typed Reactive Forms
Angular 21    │  Signal Forms introduced (experimental)
Angular 22+   │  Signal Forms stable — reactive + ergonomic, no RxJS required


SSR / HYDRATION
─────────────────────────────────────────────────────────────────────────────
Angular 4–15  │  Angular Universal — full client-side re-render on boot
Angular 16    │  Non-destructive hydration (developer preview)
Angular 18    │  Partial hydration via @defer (developer preview)
Angular 19    │  Incremental hydration (developer preview)
Angular 20+   │  Incremental hydration stable + per-route render mode stable
```

---

## Reactivity: From Digest Cycle to Signals

The most important conceptual thread across Angular's history is how change detection evolved.

### Stage 1 — AngularJS Digest Cycle (2010–2016)

AngularJS tracked state changes by running a "digest loop" — iterating over all `$watch` expressions repeatedly until no more changes were detected ("dirty checking"). Powerful and invisible to developers, but O(n) in the number of watchers and unpredictable under heavy load.

### Stage 2 — Zone.js Interception (2016–2023)

Angular 2 replaced the digest cycle with Zone.js, which monkey-patches browser async primitives. Every `setTimeout`, `Promise.then`, `XHR` callback, and event listener automatically schedules Angular's change detection. Developers no longer think about triggering updates — Zone.js handles it.

The cost: Zone.js adds ~70kb, patches things your code didn't ask it to patch, and runs change detection on *every* async event whether or not Angular state changed. `OnPush` components were the escape hatch — but an opt-in escape hatch used by a minority of teams.

### Stage 3 — Signals (2023–present)

Angular Signals are **reactive primitives**: reading a signal inside a reactive context (a `computed()` or `effect()`) automatically registers a subscription. Mutations call `signal.set()` or `signal.update()` — Angular knows *exactly* which views depend on which signals, and only re-renders those.

```
Zone.js model:    "Something async happened → check everything."
Signals model:    "This specific value changed → update only what reads it."
```

The result: no Zone.js needed, no full-tree checks, no `markForCheck()` ceremony for every async operation. The `OnPush` component becomes the natural base — which is why Angular 22 makes it the default.

---

## Key Concepts Glossary

| Concept                        | Introduced | Description                                                                                 |
|-------------------------------|------------|---------------------------------------------------------------------------------------------|
| **NgModule**                  | v2.0       | Container grouping components, pipes, directives, and providers. Now legacy.                |
| **Ivy**                       | v9.0       | Angular's current compiler and runtime. Enables locality, tree-shaking, and fast debug.     |
| **Standalone Component**      | v14.0      | A component that declares its own `imports` without belonging to an `NgModule`.             |
| **Signal**                    | v16.0      | Fine-grained reactive value. Reading in context = auto-subscription. Setting = targeted update. |
| **Computed Signal**           | v16.0      | Derived read-only signal. Recalculates lazily only when dependencies change.                |
| **Effect**                    | v16.0      | Side effect that runs whenever its signal dependencies change.                              |
| **linkedSignal**              | v19.0      | Writable signal whose default derives from another signal. Bridges computed and independent. |
| **resource / httpResource**   | v19.0→22   | Reactive async data fetching backed by Signals. Stable in v22.                             |
| **Incremental Hydration**     | v19.0→20   | Hydrate SSR output progressively using `@defer` triggers. Stable in v20.                   |
| **Zoneless**                  | v20.0→21   | Running Angular without Zone.js. Signals drive all change detection. Standard in v21.       |
| **Signal Forms**              | v21.0→22   | Form API built on Signals. No RxJS required, typed, reactive. Stable in v22.               |
| **`@defer`**                  | v17.0      | Lazy-loads a component tree based on viewport, interaction, idle, or timer triggers.        |
| **`inject()`**                | v14.0      | Functional DI — inject services outside a constructor, in factory functions or guards.      |
| **OnPush Default**            | v22.0      | Angular CLI now generates components with `ChangeDetectionStrategy.OnPush` by default.     |
| **`provideZonelessChangeDetection()`** | v20.0 | Production-API to bootstrap an Angular app without Zone.js.                         |

---

## TypeScript Compatibility Matrix

| Angular Version | Min TypeScript | Notable TS Features Leveraged                       |
|-----------------|----------------|-----------------------------------------------------|
| v2              | 2.x            | Decorators, basic generics                          |
| v9              | 3.6            | `unknown` type, optional chaining                   |
| v11             | 4.0            | Variadic tuple types                                |
| v13             | 4.4            | `exactOptionalPropertyTypes`                        |
| v14             | 4.6            | Typed reactive forms, template type checking depth  |
| v16             | 5.0            | `const` type parameters, `satisfies` operator       |
| v17             | 5.2            | `using` keyword, decorator metadata                 |
| v18             | 5.4            | `NoInfer<T>`, preserved narrowing in closures       |
| v19             | 5.5            | Inferred type predicates                            |
| v20             | 5.7            | Path rewriting, `--erasableSyntaxOnly`              |
| v21             | 5.7            | Stable decorator metadata                           |
| v22             | 5.8            | `--isolatedDeclarations`, branded types ergonomics  |

---

## Major Breaking Changes & Migration Highlights

| Version  | Breaking Change                                   | Migration Path                                             |
|----------|---------------------------------------------------|------------------------------------------------------------|
| v2.0     | Full AngularJS rewrite                            | No automated migration. Manual rewrite required.           |
| v6.0     | RxJS 6 import paths changed                       | `rxjs-compat` shim or `tslint --fix` migration script      |
| v9.0     | View Engine removed                               | `ngcc` compiler, mostly automatic via `ng update`          |
| v13.0    | IE11 support dropped                              | Remove ES5 polyfills; update browserslist                  |
| v13.0    | `ComponentFactoryResolver` deprecated             | Use `createComponent()` API                                |
| v15.0    | `RouterModule.forRoot()` patterns deprecated      | Replace with `provideRouter()` functional API              |
| v17.0    | `*ngIf`, `*ngFor` not removed but new syntax preferred | Automated migration: `ng generate @angular/core:control-flow` |
| v19.0    | Standalone default in CLI                         | `--no-standalone` flag to opt out; NgModule apps unaffected|
| v21.0    | `zone.js` not included by default in new projects | Add manually if needed, or migrate to zoneless             |
| v22.0    | `ChangeDetectionStrategy.Default` no longer the default | `ng update` sets it explicitly on existing components  |

---

## Ecosystem & Tooling Evolution

| Tool / Package              | Status in v22  | Notes                                                               |
|-----------------------------|----------------|---------------------------------------------------------------------|
| Angular CLI                 | Active         | esbuild default since v17, MCP server since v21                     |
| Angular Material            | Active         | Material 3 stable since v18                                         |
| Angular CDK                 | Active         | ARIA module added in v21                                            |
| Angular Universal (SSR)     | Merged into core | SSR now built into `@angular/core` and CLI since v17             |
| RxJS                        | Optional       | Still supported; Signals + resource() reduce reliance on it         |
| Zone.js                     | Optional legacy | Required for pre-v21 apps; not included by default in v21+          |
| Karma / Jasmine             | Deprecated     | Replaced by Vitest (stable default in v21, enforced in v22 new projects) |
| NgModule                    | Legacy         | Supported indefinitely but not recommended for new code             |
| Webpack                     | Optional       | Replaced by esbuild as default; still available via custom builders |
| Angular DevTools (browser)  | Active         | Signal graph visualizer added in v20                                |

---

## Summary: The Angular Trajectory

Angular's journey is one of deliberate, principled evolution. Each era solved the performance and ergonomics problems of the last:

- **Era 1** proved that structured frontend development was possible and necessary.
- **Era 2 (Ivy)** delivered the compiler and runtime infrastructure needed to scale: smaller bundles, faster builds, module-less architecture.
- **Era 3 (Signals)** delivers the reactive model that removes Zone.js overhead, makes change detection predictable, and aligns Angular with how modern JavaScript runtimes actually work.

Angular 22 represents the culmination of a multi-year strategy: applications that are signal-driven, zoneless, OnPush by default, and statically typed from model to form to template. The framework has never been more opinionated — and that opinionation has never been more correct.

---

## Angular Mastery Course

### From TypeScript Foundations to Enterprise‑Grade Angular (v19+)

This repository contains a complete, end‑to‑end Angular learning path, designed to transform developers from TypeScript beginners into confident, production‑ready Angular engineers capable of building real‑world, scalable, and maintainable applications.

This course focuses on modern Angular (Signals, `rxResource`, Control Flow, Zoneless‑ready patterns), real architectural thinking, and hands‑on projects that mirror professional frontend work.

🔗 [CristianSifuentes/AngularMasteryCourse](https://github.com/CristianSifuentes/AngularMasteryCourse_)

---

## Further Reading

- [angular.dev](https://angular.dev) — Official documentation
- [Angular Blog](https://blog.angular.dev) — Release announcements and roadmap updates
- [Angular Roadmap](https://angular.dev/roadmap) — In-progress and future work
- [Angular Versioning & Releases](https://angular.dev/reference/releases) — Official LTS and release policy
- [Angular GitHub Releases](https://github.com/angular/angular/releases) — Full changelog per version
- [endoflife.date/angular](https://endoflife.date/angular) — EOL and LTS date tracker
- [HeroDevs Angular Version History](https://www.herodevs.com/blog-posts/angular-version-history-every-release-date-support-window-and-end-of-life-date-from-angularjs-to-angular-22) — Extended support and commercial coverage
