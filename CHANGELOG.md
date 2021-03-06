# Changelog

## 🕴️ 0.5.1

  - ### 🤕 Fixes

    - **Ignore files in `.genignore` _before_ walking/substitution - [schell], [pull/235] [issue/236]**

      This fixes scenarios where liquid variables cause parsing errors in files that should be ignored.

      [schell]: https://github.com/schell
      [pull/235]: https://github.com/ashleygwilliams/cargo-generate/pull/235
      [issues/236]: https://github.com/ashleygwilliams/cargo-generate/issues/236

    - **Fix in CLI `help` option - [SirWindfield], [pull/234]**

      This fix the display of the `--branch` option in the help message, when executing `cargo generate --help`.

      [SirWindfield]: https://github.com/SirWindfield 
      [pull/234]: https://github.com/ashleygwilliams/cargo-generate/pull/234

  - ### 👯 New Templates

    - **`generust`: a template that provides a Rust web server and WASM client with some [interesting features](https://github.com/KyleU/generust/blob/master/doc/features.md) - [KyleU], [pull/203]**

      [KyleU]: https://github.com/KyleU
      [pull/203]: https://github.com/ashleygwilliams/cargo-generate/pull/203

    - **`orbtk`: a template that lets you create user interfaces using [OrbTk](https://github.com/redox-os/orbtk-template) - [FloVanGH], [pull/214]**

      [FloVanGH]: https://github.com/FloVanGH
      [pull/214]: https://github.com/ashleygwilliams/cargo-generate/pull/214

    - **`template-rust-backend-with-electron-frontend`: a template that lets you write a Rust native cdylib backend with [Electron](https://www.electronjs.org/) frontend - [usagi], [pull/218]**

      [usagi]: https://github.com/usagi
      [pull/218]: https://github.com/ashleygwilliams/cargo-generate/pull/218

    - **`swift-rust-xcode-template`: a template that lets you write an iOS app with [Swift](https://www.apple.com/swift/) and Rust - [simlay], [pull/219]**

      [simlay]: https://github.com/simlay
      [pull/219]: https://github.com/ashleygwilliams/cargo-generate/pull/219

    - **`Win32`: a template that provides an interface to write low-level Win32 applications in Rust - [ArmsOfSorrow], [pull/220]**

      [ArmsOfSorrow]: https://github.com/ArmsOfSorrow
      [pull/220]: https://github.com/ashleygwilliams/cargo-generate/pull/220

    - **`QuickStart WebAssembly`: a template that lets you create a WebAssembly application with Rust - [PankajChaudhary5], [pull/227]**

      [PankajChaudhary5]: https://github.com/PankajChaudhary5
      [pull/227]: https://github.com/ashleygwilliams/cargo-generate/pull/227

    - **`rust-cli-template`: a template that lets you create easily a CLI with interesting features in it ([color_eyre](https://docs.rs/color_eyre), [tracing](https://docs.rs/tracing), in addition to benchmarking and testing boilerplate) - [9999years], [pull/239]**

      [9999years]: https://github.com/9999years
      [pull/239]: https://github.com/ashleygwilliams/cargo-generate/pull/239

    - **`mongodb-service-template`: a template that lets you create a GraphQL service with MongoDB as backing storage - [bdbmammoth], [pull/243]**

      [bdbmammoth]: https://github.com/bdbmammoth
      [pull/243]: https://github.com/ashleygwilliams/cargo-generate/pull/243

  - ### 🛠️ Maintenance

    - **Support for `owner/repo` abbreviation for git URL format - [9999years], [pull/242]**

      [9999years]: https://github.com/9999years
      [pull/242]: https://github.com/ashleygwilliams/cargo-generate/pull/242

    - **Usage of default git branch instead of `master` - [9999years], [pull/241]**

      [9999years]: https://github.com/9999years
      [pull/241]: https://github.com/ashleygwilliams/cargo-generate/pull/241

    - **Updated `cargo-generate` to the latest and greatest in the Rust ecosystem - [Veetaha], [pull/237]**

      - Update all dependencies versions to latest ones
      - Replace `rustfmt-preview` with `rustfmt`
      - Replace `failure` with `anyhow`
      - Remove `quicli` completely
      - Update cargo authors copied code to latest cargo master
      - Fix clippy lints:
        - Replace &PathBuf to &Path in code
        - Remove bare `use crate_name` entires
        - Replace unexported `pub` with `pub(crate)`
      - Apply some cosmetic impl refactorings

      [Veetaha]: https://github.com/Veetaha
      [pull/237]: https://github.com/ashleygwilliams/cargo-generate/pull/237

    - **Code refactoring - [SirWindfield], [pull/233]**

      [SirWindfield]: https://github.com/SirWindfield 
      [pull/233]: https://github.com/ashleygwilliams/cargo-generate/pull/233


    - **Support all `liquid` filters - [sassman], [pull/225]**

      - Upgrade `liquid` to v0.20
      - Enables all `liquid` default filters
      - Fix some findings of clippy

      [sassman]: https://github.com/sassman
      [pull/225]: https://github.com/ashleygwilliams/cargo-generate/pull/225

    - **Typo fixes in CONTRIBUTING.md - [Darrenmeehan], [pull/222]**

      [Darrenmeehan]: https://github.com/Darrenmeehan
      [pull/222]: https://github.com/ashleygwilliams/cargo-generate/pull/222

## 🧟‍♀️ 0.5.0

  - ### ✨ Features

    - **Add a verbose flag for printing excluded files - [EverlastingBugstopper], [pull/199]**

      cargo-generate can now be run with a `--verbose` flag that will print the list of files/directories that it is ignoring. This means that by default the output for templates that exclude files will appear no differently from templates that do exclude files.

      [EverlastingBugstopper]: https://github.com/EverlastingBugstopper
      [pull/199]: https://github.com/ashleygwilliams/cargo-generate/pull/199

  - ### 🤕 Fixes

    - **Update two failure scenarios to exit with code 1 - [EverlastingBugstopper], [pull/198]**

      When cargo-generate fails due to an issue with git or if a target directory already exists, it will now fail with an exit code of 1.

      [EverlastingBugstopper]: https://github.com/EverlastingBugstopper
      [pull/198]: https://github.com/ashleygwilliams/cargo-generate/pull/198

    - **Fix path display on Windows - [tommyshem], [issue/192] [pull/195]**

      Changes Windows file output from `"C:\\Users\\Me\\src\\example-com\\.genignore"` to `"C:\Users\Me\src\example-com\.genignore"`

      [tommyshem]: https://github.com/tommyshem
      [pull/195]: https://github.com/ashleygwilliams/cargo-generate/pull/195
      [issue/192]: https://github.com/ashleygwilliams/cargo-generate/issues/192

    - **Don't remove .github directory when only .git should be removed - [softprops], [issue/190] [pull/191]**

      When generating a new project, cargo-generate will remove the `.git` directory and initialize a new git tree. In doing so, it would remove any file or directory containing `.git`, including `.github`. This release fixes that bug! 

      [softprops]: https://github.com/softprops
      [pull/191]: https://github.com/ashleygwilliams/cargo-generate/pull/191
      [issue/190]: https://github.com/ashleygwilliams/cargo-generate/issues/190

  - ### 🛠️ Maintenance

    - **Fix a dead link in TEMPLATES.md - [yaahc], [pull/186]**

      [yaahc]: https://github.com/yaahc
      [pull/186]: https://github.com/ashleygwilliams/cargo-generate/pull/186

    - **Use Cargo.lock when compiling binary - [xortive], [pull/188]**

    [xortive]: https://github.com/xortive
    [pull/188]: https://github.com/ashleygwilliams/cargo-generate/pull/188

## 🍕 0.4.0

  - ### ✨ Features

    - **Add config file for configuring include / exclude of files to template - [xortive], [pull/174]**
        
        Adds support for the [cargo-generate.toml](https://github.com/ashleygwilliams/cargo-generate/blob/master/README.md#include--exclude) file, which allows templates to configure which files should be processed, either using a whitelist method (`include`), or a blacklist method (`exclude`). When both `include` and `exclude` are present, `include` will be preferred. This mirrors [similar `include`/`exclude` behavior in `cargo`](https://doc.rust-lang.org/cargo/reference/manifest.html#the-exclude-and-include-fields-optional), and uses some of the same code.

        #### Include List

        ```toml
        [template]
        include = ["Cargo.toml", "src/lib.rs"] # Only search for and replace template tags in Cargo.toml and src/lib.rs
        ```

        #### Exclude List

        ```toml
        [template]
        exclude = ["public/image.js"] # Don't look for template tags in public/image.js
        ```

        #### Invalid Configuration

        ```toml
        [template]
        # This is an "invalid" configuration, so cargo-generate takes the "more specific" include option
        # and will only search for and replace template tags in Cargo.toml.
        include = ["Cargo.toml"]
        exclude = ["public/image.js"]
        ```
       
        [xortive]: https://github.com/xortive
        [pull/174]: https://github.com/ashleygwilliams/cargo-generate/pull/174

  - ### 🤕 Fixes

    - **Respect default branch name of template - [RotationMatrix], [pull/166]**
    
        The `--branch` flag will now work as intended and set the initial HEAD to the specified branch name. For example, running `cargo generate --git <gh pages template> --branch gh-pages` will set your generated project's default branch to `gh-pages`.
        
        [RotationMatrix]: https://github.com/RotationMatrix
        [pull/166]: https://github.com/ashleygwilliams/cargo-generate/pull/166

  - ### 🛠️ Maintenance

    - **Cleanup of lingering clippy / rustfmt warnings - [ashleygwilliams], [pull/175]**
    
        [ashleygwilliams]: https://github.com/ashleygwilliams
        [pull/175]: https://github.com/ashleygwilliams/cargo-generate/pull/175

    - **Fix assert! macro usage - [rasendubi], [pull/157]**

        [rasendubi]: https://github.com/rasendubi
        [pull/157]: https://github.com/ashleygwilliams/cargo-generate/pull/157

## 🛠 0.3.1

  - ### 🤕 Fixes

    - **Fix messages related to rename behavior - [xortive], [pull/162]**
        
        `--force` would stop `cargo-generate` renaming your project, but we would
        still message that the rename was happening. Not anymore!

        [xortive]: https://github.com/xortive
        [pull/162]: https://github.com/ashleygwilliams/cargo-generate/pull/162

    - **Use Vendored OpenSSL for macOS - [xortive], [pull/169]**
      
        Our prebuilt binaries for macOS were using dynamically linked OpenSSL, 
        and our CI was dynamically linking to a version of OpenSSL not installed
        by default on most macs. Now, the macOS release build of `cargo-generate`
        will work out of the box utilizing staticly linked, vendored OpenSSL.

        [xortive]: https://github.com/xortive
        [pull/169]: https://github.com/ashleygwilliams/cargo-generate/pull/169

  - ### 👯 New Templates

    - **`bluepill` stm32 microcontroller board template - [mendelt], [pull/156]**

        [mendelt]: https://github.com/mendelt
        [pull/156]: https://github.com/ashleygwilliams/cargo-generate/pull/156

    - **`cmdr` commandline appliction template - [mendelt], [pull/156]**

        [mendelt]: https://github.com/mendelt
        [pull/156]: https://github.com/ashleygwilliams/cargo-generate/pull/156

    - **`ggez` rust gamedev template - [cyclowns], [pull/167]**
    
        [cyclowns]: https://github.com/cyclowns
        [pull/167]: https://github.com/ashleygwilliams/cargo-generate/pull/167

- ### 🛠️ Maintenance

    - **Update to liquid 0.19 - [epage], [pull/165]**

        [epage]: https://github.com/epage
        [pull/165]: https://github.com/ashleygwilliams/cargo-generate/pull/165

## ⭐ 0.3.0

  - ### ✨ Features

    - **Support case filters in templates - [epage], [issue/117] [pull/140]**

        Because we leverage `liquid` as a templating engine under the hood, we
        can add some specific filters to our substitutions to add a little more
        awesome. This feature adds 4 filters:

        - `capitalize`
        - `pascal_case`
        - `kebab_case` 
        - `snake_case`

        Now we can tame any set of letters with any type of capitalization or
        dash! Give them a try and let us know what other types of features you'd
        like to see.

        [issue/117]: https://github.com/ashleygwilliams/cargo-generate/issues/117
        [pull/140]: https://github.com/ashleygwilliams/cargo-generate/pull/140

  - ### 🤕 Fixes

    - **Windows releases on Appveyor - [jaysonsantos], [issue/145] [pull/146]**

        Thanks to a new tool, [`wrangler`], that uses `cargo-generate` as a
        dependency, it was discovered that we were shipping broken Windows
        binaries. We've fixed that now!

        [`wrangler`]: https://github.com/ashleygwilliams/cargo-generate
        [jaysonsantos]: https://github.com/jaysonsantos
        [issue/145]: https://github.com/ashleygwilliams/cargo-generate/issues/145
        [pull/146]: https://github.com/ashleygwilliams/cargo-generate/pull/146

  - ### 👯 New Templates

    - **`procmacro-quickstart` template - [eupn], [pull/141]**

        [eupn]: https://github.com/eupn
        [pull/141]: https://github.com/ashleygwilliams/cargo-generate/pull/141

  - ### 🛠️ Maintenance

    - **Update to 2018 Edition - [ashleygwilliams], [issue/131] [pull/147]**

        This was a fun one and additionally involved upgrading us to `quicli` 0.4!
        Welcome to 2018, `cargo-generate`.

        [issue/131]: https://github.com/ashleygwilliams/cargo-generate/issues/131
        [pull/147]: https://github.com/ashleygwilliams/cargo-generate/pull/147

    - **Shallow `main` refactor - [DD5HT], [pull/115]**

        [pull/115]: https://github.com/ashleygwilliams/cargo-generate/pull/115

    - **Update `liquid` - [epage], [pull/139]**

        [epage]: https://github.com/epage
        [pull/139]: https://github.com/ashleygwilliams/cargo-generate/pull/139

## 🌟 0.2.2

  - ### 🤕 Fixes

    - **fix relative paths to templates - [DD5HT], [issue/128] [pull/129]**

      When we previously merged the PR in 0.2.0 that leveraged `cargo` to clone the templates,
      enabling folks to work with private repositories- we introduced a `GitConfig::new` function
      (replacing work done previously by `libgit2`). This function works great- but did not support
      relative paths. We didn't catch this because we weren't testing the relative paths usecase!

      With this PR, [DD5HT] has restored the relative path functionality- and added a test to prevent
      further regressions of this function!

      [issue/128]: https://github.com/ashleygwilliams/cargo-generate/issues/128
      [pull/129]: https://github.com/ashleygwilliams/cargo-generate/pull/129

  - ### 🛠️ Maintenance

    - **cargo update/cargo fmt - [ashleygwilliams], [pull/134] [pull/133]**

      [pull/133]: https://github.com/ashleygwilliams/cargo-generate/pull/133
      [pull/134]: https://github.com/ashleygwilliams/cargo-generate/pull/134

## 🌠 0.2.1

  - ### 🤕 Fixes

    - **don't error on missing `.genignore` file - [DD5HT], [issue/116] [pull/120]**

      With 0.2.0 we introduced the idea of a `.genignore` file, however, we didn't account
      the situation where one would not be present. Thanks for filing [an issue][issue/116]
      [Diggsey] and thanks for the quick fix [DD5HT]!

      [issue/116]: https://github.com/ashleygwilliams/cargo-generate/issues/116
      [pull/120]: https://github.com/ashleygwilliams/cargo-generate/pull/120
      [Diggsey]: https://github.com/Diggsey

    - **enable use on private repositories- [ChristopherMacGown], [pull/119]**

      This PR leveraged `cargo` to enable the ability to pull authenticated repos. As this
      project grows into something we'd like to integrate into `cargo`, this gives us
      greater functionality and also moves us closer to `cargo`'s codebase. Yay!

      [ChristopherMacGown]: https://github.com/ChristopherMacGown
      [pull/119]: https://github.com/ashleygwilliams/cargo-generate/pull/119

    - **exclude submodules git metadata - [ChristopherMacGown], [pull/119]**
  
      Two bugs, one PR! Adding a test found that git metadata wasn't being excluded from
      submodules- now it is! Thanks so much!

  - ### 👯 New Templates

    - **`actix-tera` template - [antweiss], [pull/123]**
    - **`samp rust sdk` template - [Sreyas-Sreelal], [pull/121]**

    [antweiss]: https://github.com/antweiss
    [pull/123]: https://github.com/ashleygwilliams/cargo-generate/pull/123
    [Sreyas-Sreelal]: https://github.com/Sreyas-Sreelal
    [pull/121]: https://github.com/ashleygwilliams/cargo-generate/pull/121

## 💫 0.2.0

  - ### ✨ Features

    - **Support templates that use git submodules - [k0pernicus], [issue/83] [pull/104]**

      We now support templates that use git submodules! Yay!

      [k0pernicus]: https://github.com/k0pernicus
      [issue/83]: https://github.com/ashleygwilliams/cargo-generate/issues/83
      [pull/104]: https://github.com/ashleygwilliams/cargo-generate/pull/104

    - **Binary Releases for Linux, MacOS, and Windows - [ashleygwilliams], [issue/99] [pull/111] [pull/112]**

      Motivated by a desire to more easily distributed the project - we now build binaries
      for our releases. No more waiting for compilation! You can just download and go!

      [issue/99]: https://github.com/ashleygwilliams/cargo-generate/issues/99
      [pull/111]: https://github.com/ashleygwilliams/cargo-generate/pull/111
      [pull/112]: https://github.com/ashleygwilliams/cargo-generate/pull/112

    - **Allow Liquid Templating `date` filter - [ashleygwilliams], [issue/70] [pull/106]**

      By request, we've turned on the `date` filter for our templates. Now you can add
      nicely formatted dates to your projects! For more information, check out the
      [Liquid `date` filter documentation].

      [Liquid `date` filter documentation]: https://shopify.github.io/liquid/filters/date/
      [issue/70]: https://github.com/ashleygwilliams/cargo-generate/issues/70
      [pull/106]: https://github.com/ashleygwilliams/cargo-generate/pull/106

    - **Add `.genignore`, ability to ignore files - [DD5HT], [issue/82] [pull/96]**

      You can now add a `.genignore` file to your template. This file will specify the files
      to be "cleaned up" or "removed" from the template once it has been cloned to the user's
      local machine.

      [issue/82]: https://github.com/ashleygwilliams/cargo-generate/issues/82
      [pull/96]: https://github.com/ashleygwilliams/cargo-generate/pull/96

    - **Add `--branch` for specifying a branch - [posborne], [issue/71] [pull/94]**

      We originally had no way to specify a git template on a per branch basis, opting to
      only support the primary branch. Now you can specify a branch:

      ```
      cargo generate --git <gitURL> --branch <branchname>
      ```

      [posborne]: https://github.com/posborne
      [issue/71]: https://github.com/ashleygwilliams/cargo-generate/issues/71
      [pull/94]: https://github.com/ashleygwilliams/cargo-generate/pull/94

    - **Warn user if we change project name casing - [k0pernicus], [issue/65] [pull/84]**

      `cargo-generate` will automagically "fix" the casing of your project name to
      match Cargo standards. If we end up changing the name you provide- we'll warn
      to let you know!

      [k0pernicus]: https://github.com/k0pernicus
      [issue/65]: https://github.com/ashleygwilliams/cargo-generate/issues/65
      [pull/84]: https://github.com/ashleygwilliams/cargo-generate/pull/84

    - **Add `--force` flag to skip casing check on project name - [toVersus], [issue/66] [pull/69]**

      `cargo-generate` will automagically "fix" the casing of your project name to 
      match Cargo standards. If you'd like to skip that, you can add `--force`.

      [toVersus]: https://github.com/toVersus
      [issue/66]: https://github.com/ashleygwilliams/cargo-generate/issues/66
      [pull/69]: https://github.com/ashleygwilliams/cargo-generate/pull/69

    - **Add short flag `-n` for `--name` - [DD5HT], [issue/73] [pull/77]**

      [issue/73]: https://github.com/ashleygwilliams/cargo-generate/issues/73
      [pull/77]: https://github.com/ashleygwilliams/cargo-generate/pull/77

    - **List of available templates - [ashleygwilliams], [issue/74] [issue/50] [pull/75]**

      We are now keeping a running list of templates that are available to use with
      `cargo-generate`. Please add more!

      [issue/74]: https://github.com/ashleygwilliams/cargo-generate/issues/74
      [issue/50]: https://github.com/ashleygwilliams/cargo-generate/issues/50
      [pull/75]: https://github.com/ashleygwilliams/cargo-generate/pull/75

    - **Add short command `cargo gen` - [DD5HT], [issue/53] [pull/72]**

      You can now use `cargo gen` as a short command for `cargo generate`.

      [DD5HT]: https://github.com/DD5HT
      [issue/53]: https://github.com/ashleygwilliams/cargo-generate/issues/53
      [pull/72]: https://github.com/ashleygwilliams/cargo-generate/pull/72

  - ### 🛠️ Maintenance

    - **Fixed some clippy warnings - [4tm4j33tk4ur], [pull/109]**

      [4tm4j33tk4ur]: https://github.com/4tm4j33tk4ur
      [pull/109]: https://github.com/ashleygwilliams/cargo-generate/pull/109

    - **Test safety of `.genignore` - [ashleygwilliams], [issue/97] [pull/98]**

      [issue/97]: https://github.com/ashleygwilliams/cargo-generate/issues/97
      [pull/98]: https://github.com/ashleygwilliams/cargo-generate/pull/98

    - **`cargo update` and update `cargo fmt` call - [ashleygwilliams], [issue/86] [pull/88]**

      [issue/86]: https://github.com/ashleygwilliams/cargo-generate/issues/86
      [pull/88]: https://github.com/ashleygwilliams/cargo-generate/pull/88

    - **Test project name casing - [ashleygwilliams], [issue/63] [pull/64]**

      [issue/63]: https://github.com/ashleygwilliams/cargo-generate/issues/63
      [pull/64]: https://github.com/ashleygwilliams/cargo-generate/pull/64

    - **Move from `ident_case` to `heck` - [csmoe], [issue/57] [pull/62]**

      [issue/57]: https://github.com/ashleygwilliams/cargo-generate/issues/57
      [pull/62]: https://github.com/ashleygwilliams/cargo-generate/pull/62

## 💥 0.1.1

  - ### 🤕 Fixes

    - **Fix command to work properly as a cargo command - [csmoe], [issue/39] [pull/44]**

      Previous to this commit, `cargo-generate` was a CLI tool that was invoked by the
      command `cargo-generate` (note the dash). However, this tool intends to be a cargo
      subcommand! This commit changes how you invoke the tool- no more dash!

      ```
      cargo generate --git https://github.com/username/project --name look-ma-no-dash
      ```

      [csmoe]: https://github.com/csmoe
      [issue/39]: https://github.com/ashleygwilliams/cargo-generate/issues/39
      [pull/44]: https://github.com/ashleygwilliams/cargo-generate/pull/44

    - **Fix casing on `crate_name` substitution - [ashleygwilliams], [issue/41] [pull/56]**

      `crate_name` substitution is supposed to be a convenience, converting the given
      project's name to a name that you could use with `extern crate` or in other *in-code*
      situations. Just one problem- before this commit, it didn't change the case! 
      Now it will. Thanks so much to [fitzgen] for filing this issue (and a bunch of others)!

      [ashleygwilliams]: https://github.com/ashleygwilliams
      [issue/41]: https://github.com/ashleygwilliams/cargo-generate/issues/41
      [pull/56]: https://github.com/ashleygwilliams/cargo-generate/pull/56
      [fitzgen]: https://github.com/fitzgen

  - ### 📖 Documentation

    - **Document build and runtime dependencies - [migerh], [issue/42] [pull/45]**

      There are a few dependencies for the project that we hadn't documented. Many folks
      have these already installed, but some don't- so it's great that they are now well
      documented in the `README`.

      [migerh]: https://github.com/migerh
      [issue/42]: https://github.com/ashleygwilliams/cargo-generate/issues/42
      [pull/45]: https://github.com/ashleygwilliams/cargo-generate/pull/45

    - **Update README and demo.gif to address The Dash - [ashleygwilliams], [pull/60]**

      [pull/60]: https://github.com/ashleygwilliams/cargo-generate/pull/60

    - **Typo Fix - [rahulthakoor], [pull/36]**

      [rahulthakoor]: https://github.com/rahul-thakoor
      [pull/36]: https://github.com/ashleygwilliams/cargo-generate/pull/36

  - ### 🛠️ Maintenance

    - **Test substitutions - [ashleygwilliams], [issue/34] [pull/56]**

      We had features we weren't testing. This PR now adds test coverage for:

        - substitution of `crate_name`
        - correct casing change of `crate_name`
        - substitution in files beyond `Cargo.toml`

      We still don't have full coverage but at least it's improving!

      [issue/34]: https://github.com/ashleygwilliams/cargo-generate/issues/34

    - **Split test helpers into files - [ashleygwilliams], [issue/33] [pull/35]**

      "i like small files and i cannot lie"

      [ashleygwilliams]: https://github.com/ashleygwilliams
      [issue/33]: https://github.com/ashleygwilliams/cargo-generate/issues/33
      [pull/35]: https://github.com/ashleygwilliams/cargo-generate/pull/35

## 🌌 0.1.0

- First release! 
