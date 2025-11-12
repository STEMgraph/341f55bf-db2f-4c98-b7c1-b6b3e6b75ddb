<!---
{
  "id": "341f55bf-db2f-4c98-b7c1-b6b3e6b75ddb",
  "teaches": "Using the Terminal-Emulator to Explore the *nix Filesystem",
  "depends_on": ["e46ffb8b-00d6-44a2-ad40-552ea03b4e3a"],
  "author": "Stephan Bökelmann",
  "first_used": "2025-04-01",
  "keywords": ["shell", "filesystem", "cd", "pwd", "ls"]
}
--->

# Using the Terminal-Emulator to Explore the *nix Filesystem

## 1) Introduction

We interface with our filesystem using the operating system's kernel. The kernel talks to the filesystem driver and can store and retrieve data from locations identified by **filenames**. Filenames are used as aliases for physical locations on storage media that would otherwise be hard to address directly.

The **filesystem** is the structure that maps names to physical addresses—much like a phonebook. When users interact with "directories," they are in fact using long filename prefixes that organize and group files. In truth, there are no actual directories or folders on a hard drive — these are conceptual groupings provided by the filesystem.

Suffixes like `.pdf`, `.docx`, or `.jpg` typically indicate the file's type, while prefixes such as `Documents/` or `Downloads/` indicate grouping. Navigating these logical groupings is made easier with the `cd` (change directory) command, which tells the shell to treat a different prefix as the current working context.

A typical command line prompt might look like:

```bash
user@host:/home/user$
```

Here, `user` is your username, `host` is the machine name, and `/home/user/` is the current directory. When you issue a command, filenames will be resolved relative to this path unless explicitly stated otherwise.

In this challenge, you will:

- Use the `cd` command to navigate your filesystem,
- Use `ls` to list files in the current directory,
- Use `pwd` to print the current working directory.

## 2) Tasks

1. **Inspecting the Current Directory**

   ```bash
   pwd
   ```

   This prints your "present working directory" — the path prepended to any relative filenames. You’ll likely see something like `/home/<username>`, even though your shell prompt might display `~`. This is because `~` is a shorthand for your home directory.

2. **Creating and Resolving Files**

   ```bash
   touch myfile.txt
   ls
   realpath myfile.txt
   ```

   The `touch` command creates an empty file (or updates the timestamp if it exists). `realpath` shows the absolute path to that file.

3. **Exploring Other Directories**

   ```bash
   ls /
   ls /home
   ```

   These commands let you inspect the root directory `/` and the home directory for all users.

4. **Using `ls` Options**

   Try the following commands and explain what changes:

   ```bash
   ls -l
   ls -lS
   ls -lh
   ls -la
   ls -l /
   ls -l /home
   ```

5. **Changing Directories**

   Use `cd` to move around:

   ```bash
   pwd
   cd /
   ls -l
   cd /home/<your-username>
   pwd
   cd /
   cd <any directory>
   ls -l
   ```

6. **Special `cd` Shortcuts**

   ```bash
   cd
   pwd
   cd -
   pwd
   cd ..
   pwd
   ```

## 3) Questions

- What does the `pwd` command show, and why is it different from `~` in the prompt?
- How are filenames structured in a filesystem, and what do prefixes and suffixes tell us?
- What is the difference between an absolute and a relative path?
- How does the `cd` command change your working directory?
- What does the `ls` command show, and what do its options (`-l`, `-S`, `-h`, `-a`) do?
- What is the purpose of `cd -`, `cd ..`, and just `cd`?
- Why might it be useful to see the full path of a file using `realpath`?

## 4) Advice

Linguistically, "to prompt" means to incite, suggest, or encourage — which is exactly what the CLI prompt does: it invites you to give the next instruction. If you get tired of typing long directory paths, press the `Tab` key to autocomplete them. If multiple completions exist, press `Tab` twice to see suggestions.
