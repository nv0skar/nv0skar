# こんにちは世界！🐙
## Something about me 👽
```rust
#![allow(non_snake_case)]
const FRAME_CHARACTER: &str = "◼︎";

struct Myself {
    name: String,
    target: String,
    remainingFuel: String,
}

mod beautify {
    use crate::FRAME_CHARACTER;
    pub enum Frame {
        X(usize),
        Y,
    }
    pub fn print_fancy_border(position: Frame, newLine: bool) {
        match position {
            Frame::X(max_repeat) => { print!(" \x1b[93m{}{}\x1b[0m", FRAME_CHARACTER.repeat(max_repeat), { if newLine { "\n" } else { "" } }); }
            Frame::Y => { print!("\x1b[93m{}{}\x1b[0m", FRAME_CHARACTER, { if newLine { "\n" } else { "" } }); }
        }
    }
    pub fn print_beautifully(string_list: &[String]) {
        let longest_line = check_longest(&string_list);
        print_fancy_border(Frame::X(longest_line), true);
        for line in string_list {
            print_fancy_border(Frame::Y, false);
            print!("\x1b[97m{}\x1b[0m{}", line, {
                if line.chars().count() != longest_line {
                    " ".repeat(longest_line - line.chars().count())
                } else {
                    String::default()
                }
            });
            print_fancy_border(Frame::Y, true);
        }
        print_fancy_border(Frame::X(longest_line), true);
    }
    pub fn check_longest(string_list: &[String]) -> usize {
        let mut longest: usize = 0;
        for line in string_list {
            if longest < line.chars().count() {
                longest = line.chars().count();
            }
        }
        longest + 1
    }
}

fn main() {
    // Define my name
    let name: String = String::from("Oscar");
    // Define my target
    let target: String = String::from("Going to stars and beyond ⭐️");
    // Define my remaining fuel
    let remainingFuel: String = String::from("∞ and more!");
    // Define myself
    let myself: &Myself = &Myself { name, target, remainingFuel };
    // Show on screen
    {
        let to_display = [
            { String::from(format!(" Hey! My name is {}.", { &myself.name })) },
            { String::from(format!(" {}", &myself.target)) },
            { String::from(format!(" Remaining fuel: {}", { &myself.remainingFuel })) },
        ];
        beautify::print_beautifully(&to_display);
    }
}
```

## What languages I speak? 🚀
- I love Rust! 🦀
- Native speaker in Python 🥷
- A little bit of Swift 🦉
- Typescript-guy 💪
- I defend myself at C and C++, but I'm not a extensive speaker of those 😅

## What I want to checkout? 🤔
- [ ] Vlang
- [ ] C#
- [ ] Julia
- [ ] Crystal
- [ ] Golang

## Communities 💫
<a href="https://dev.to/nv0skar">
  <img src="https://dev-to-uploads.s3.amazonaws.com/uploads/logos/resized_logo_UQww2soKuUsjaOGNB38o.png" alt="ItsTheGuy's DEV Community Profile" height="40">
</a>
