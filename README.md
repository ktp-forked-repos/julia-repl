# julia-repl: run an inferior Julia REPL in Emacs

This is a minor mode for interacting with a Julia REPL running inside Emacs. The `julia` process is started in an ANSI terminal (`term`), which allows text formatting and colors, and interaction with the help system and the debugger.

It is recommended that you use this minor mode with [julia-mode](https://github.com/JuliaEditorSupport/julia-emacs).

## Loading

Place this in your Emacs initalization files (eg `.emacs`):
```lisp
(add-to-list 'load-path path-to-julia-repl)
(require 'julia-repl)
(add-hook 'julia-mode-hook 'julia-repl-mode) ;; always use minor mode
```

## Usage

The default keys are as follows.

key | action
----|-------
`C-c C-c` | send region (when applicable) or line to REPL
`C-c C-b` | send whole buffer to REPL
`C-c C-z` | raise the REPL or create a new one
`C-RET` | send line to REPL
`C-c C-e` | invoke `@edit` on region (when applicable) or line
`C-c C-d` | invode `@doc` on symbol

## Limitations

There should be a way to send function definitions without selecting them.

## Comparison to ESS

A well-known alternative is [ESS](https://ess.r-project.org/), which also supports Julia. `julia-repl` was written because I could not use [Gallium](https://github.com/Keno/Gallium.jl) from ESS, which is based on `comint`, and thus does not allow a fully functioning terminal.
