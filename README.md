# Standards of Practice

## Member Comments
To add yourself as a member who can comment:
- Go to [main.scss](./assets/css/main.scss)
- At the bottom of the page, add the following code:
```
.name {
  color: YourColor;
  &:before {
    font-weight: bold;
    content: "[XXX Name Says: ";
  }
  &:after {
    font-weight: bold;
    content: "]";
  }
}
```
- Change name to your first name both in the class name and the content. Change YourColor to magenta if you are faculty or orange if you are a student.

To make a comment in line, write the following code:
```
<span class="name">Your comment</span>
```

## Using TODOs Inline
To create a todo in the text, add the following code:
```
<span class="todo">The TODO text</span>
```

## Adding an Image
When inserting an image for lesson guides, use the code
```
![image description](../resources/images/FILENAME)
```

## Adding and Linking a Local Resource
When adding a local resource, add the file to the folder:
```
/_docs/resources/
```
and name the file PART-LESSON_FILE-NAME.PDF (e.g. 2-1_intro-to-programming.pdf).

When linking a local resource, use the code
```
[Resource Title](../resources/FILENAME)
```

## Editing Lessons
Do not touch the yml code on lines 1-4.  
On line 5, begin all lessons with Subject as header 2 (header 1 is inherited from the page title).

# TODO

## Curriculum Enhancement
For each lesson,
- Copy and format content from MS Word
- Save all resources as pdf and add to _docs/resources
  - Use same file name as in SharePoint
- Save lesson plan images in _docs/resources/images/
  - File name should be PART-LESSON_DESCRIPTOR1-DESCRIPTOR2.EXTENSION (e.g. 2-2_cat-circuit.png)
- Link the image in the .md file
- Check all links

- [ ] 3-1
  - [ ] Add visual arts standards
  - [ ] Create scaffold for creating symbolism in stories
  - [ ] Need card stock dimensions
  - [ ] Change footer on Brainstorm Posters
  - [ ] Change footer on Brainstorm Scoot
- [ ] 3-2
  - [ ] Add visual arts standards
  - [ ] Create example Ledger Art Projects

## User Experience
- [X] /_docs/index.md
  - [X] Create a big picture summary of the curriculum and the connections made.

## Content Transfer
- [X] 1-1
- [X] 1-2
- [X] 2-1
- [X] 2-2
- [ ] 3-1 (needs enhancement due to change from narrative to symbols and visual arts standards)
- [ ] 3-2 (needs examples of ledger art projects and visual arts standards)
- [X] 3-3
- [X] 4-1
- [X] 4-2
- [X] 4-3
- [X] 5-1
- [X] 5-2
- [X] 5-3
