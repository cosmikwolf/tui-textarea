<a name="v0.1.2"></a>
# [v0.1.2](https://github.com/rhysd/tui-textarea/releases/tag/v0.1.2) - 25 Jun 2022

- Indent with hard tab is now supported. `TextArea::set_hard_tab_indent` method enables indentation with a hard tab on hitting a tab key.
  ```rust
  let mut textarea = TextArea::default();

  textarea.set_hard_tab_indent(true);
  textarea.insert_tab();
  assert_eq!(textarea.lines(), ["\t"]);
  ```
  Screencast with `cargo run --example editor`:
  <img src="https://user-images.githubusercontent.com/823277/175755458-5bf60e84-e01f-410d-9194-d3117031eff6.gif" alt="screencast" width=452 height=140>
- Add `TextArea::indent` method to get an indent string of textarea.
  ```rust
  let mut textarea = TextArea::default();

  assert_eq!(textarea.indent(), "    ");
  textarea.set_tab_length(2);
  assert_eq!(textarea.indent(), "  ");
  textarea.set_hard_tab_indent(true);
  assert_eq!(textarea.indent(), "\t");
  ```

[Changes][v0.1.2]


<a name="v0.1.1"></a>
# [v0.1.1](https://github.com/rhysd/tui-textarea/releases/tag/v0.1.1) - 21 Jun 2022

- Add `TextArea::yank_text` and `TextArea::set_yank_text` to set/get yanked text of the textarea.
  ```rust
  let mut textarea = TextArea::default();
  textarea.set_yank_text("hello, world");
  assert_eq!(textarea.yank_text(), "hello, world");
  textarea.paste();
  assert_eq!(textarea.lines(), ["hello, world"]);
  ```
- Add `CursorMove::Jump(row, col)` variant to move cursor to arbitrary (row, col) position with `TextArea::move_cursor`.
  ```rust
  let mut textarea = TextArea::from(["aaaa", "bbbb"]);
  textarea.move_cursor(CursorMove::Jump(1, 2));
  assert_eq!(textarea.cursor(), (1, 2));
  ```
- Fix hard tabs are not rendered (#1)

[Changes][v0.1.1]


<a name="v0.1.0"></a>
# [v0.1.0](https://github.com/rhysd/tui-textarea/releases/tag/v0.1.0) - 19 Jun 2022

First release :tada:

- GitHub repository: https://github.com/rhysd/tui-textarea
- crates.io: https://crates.io/crates/tui-textarea
- docs.rs: https://docs.rs/tui-textarea/latest/tui_textarea/

[Changes][v0.1.0]


[v0.1.2]: https://github.com/rhysd/tui-textarea/compare/v0.1.1...v0.1.2
[v0.1.1]: https://github.com/rhysd/tui-textarea/compare/v0.1.0...v0.1.1
[v0.1.0]: https://github.com/rhysd/tui-textarea/tree/v0.1.0

 <!-- Generated by https://github.com/rhysd/changelog-from-release -->