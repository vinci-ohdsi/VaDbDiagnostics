# svGUI 1.0.1

- More tests added.

- A pgkdown site is created to better document the 'svGUI' package.

- `NEWS.md` slightly reworked to be compatible with `R CMD build` format.

# svGUI 1.0.0

- Code of conduct added in Github repository.

- A bug led to an error while trying to use `gui$startUI()`. Corrected.

# svGUI 0.9-57

- Switch to snake_case function names. The camelCase version are still there for backward compatibility.

# svGUI 0.9-56

- Switch to Github for development; CI added.

# svGUI 0.9-55

- `Author` and `Authors@R` fields reworked in the `DESCRIPTION` file.

# svGUI 0.9-54

- The package now store temporary data in `SciViews:TempEnv` instead of `TempEnv` and it needs 'svMisc' >= 0.9-68.

# svGUI 0.9-53

- Minor tweaking of the internal code.

# svGUI 0.9-52

- R 2.15.0 complains about argument partial match in `print.gui()`: `guiAsk(gui = x)`. Fixed.

# svGUI 0.9-52

- Large refactoring of SciViews-R packages. Most of the functions to interface with Komodo are moved to the 'svKomodo' package: `koCmd()`, `guiInstall()`, `guiUninstall()`, `guiRefresh()`, `guiAutoRefresh()`. The functions dealing with the httpServer are moved to 'svHttp': `parHttp()`, `startHttpServer()`, `stopHttpServer()`, `HttpServerPort`, `HttpServerName()` & `HttpClientsNames()`. So... basically, nothing much left here from previous version! But now it contains functions to manage 'gui' objects, used by 'svWidgets' and 'svDialogs'.

- S3 objects of class 'gui' are added. They are supposed to be created by `guiAdd()` and a series of functions is provided to manipulate them. They are not terribly useful by themselves, but they provide the foundation for a flexible organization of GUI elements in R (see for instance 'svDialogs' or 'svWidgets').

# svGUI 0.9-51

- HTTP server now works with the new version of `captureAll()` from 'svMisc' 0.9-62 and it is compatible with its `echo =` and `split =` arguments.

# svGUI 0.9-50

- HTTP server now works correctly with incomplete commands (bug corrected).

# svGUI 0.9-49

- HTTP server code processing now uses `parseText()` of 'svMisc' >= 0.9-60 instead of the deprecated `Parse()` function.

# svGUI 0.9-48

- `koCmd()` now should prepend `<<<js>>>` to the JavaScript code to get it evaluated in Komodo (starting with SciViews-K 0.9-18). Komodo now also accepts RJsonP strings, prepended with `<<<rjson>>>`. If there is no code prepended to the string send to Komodo, it is just printed in the local R console. A new 'type' argument specifies what kind of string we send to Komodo.

- The R http server is modified to work with either RJsonP calls, or with plain text exchange, as the SciViews socket server works. RJsonP objects returned use `list()` to create lists, but also structures or new S4 objects.

# svGUI 0.9-47

- A new series of function to communication with a SciViews GUI client like Komodo/SciViews-K by using the R http help server is added. It offers a tcltk-free alternative to the 'svSocket' server.

- The package no longer starts the socket server implemented in 'svSocket' and it does not import 'svSocket' any more. As the HTTP server is an alternative, one could now choose to run SciViews communication through the HTTP server without using 'svSocket', and thus, without starting Tcl/Tk any more.

# svGUI 0.9-46

- Use of `svTaskCallbackManager()` of 'svSocket' >= 0.9-48 to register task callback that are also executed after each R code send by socket clients.

- `guiRefresh()` now clears active items and MRU lists in Komodo for non-defined active data frames and 'lm' objects.

# svGUI 0.9-45

- Added `guiRefresh()` and `guiAutoRefresh()` to refresh automatically the content of the GUI (Komodo) object explorer and the lists of active objects.

# svGUI 0.9-44

- Preparation for CRAN submission: polishing the package.

# svGUI 0.9-43

- Made compatible with R 2.6.x (previous version was compatible with R 2.7.0).

# svGUI 0.9-42

- `koCmd()` is now more robust and do not issue a warning or an error if the
Komodo server is not available (but the error message is returned by the
function with a 'try-error' class, so that it can be processed by the caller)
.

# svGUI 0.9-41

- Correction of a bug in the first example of `koCmd()`.

- `guiInstall()` now creates a hook to `koCmd()`: `.koCmd()` in `SciViews:TempEnv`.

# svGUI 0.9-40

- This is the first version distributed on R-forge. It is completely refactored from older versions (on CRAN since 2003) to make it run with SciViews-K and Komodo Edit (Tinn-R is also supported, but not SciViews-R Console any more).
