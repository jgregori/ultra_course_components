# Ultra Course Snippets

HTML and Tailwind CSS snippets that improve content layout and appearance in Blackboard.

## Main features

- Responsive
- Multi-language
- Accesible

## How to use

1. Select the snippet that you want to use.
2. Copy as an HTML block inside of a Blackboard Document.
3. Add your data (check each component for more information).
4. Tweak colors or modify the snippet as needed.

## Snippets

### Single Instructor snippet

![about instructor](./demo_img/about_instructor_lg.png)

A simple Card to showcase a single/main course instructor, it includes the following customizable elements:

1. **Title**
2. **Language toogle** (Default EN/FR/ES)
3. **Instructor name and pronoums**
4. **Instructor picture**
5. **Contact icons**
6. **Instructor BIO**
7. **Instructor skills/specialities**
8. **Link to research articles**

To customize the content, locate the `const = data` json around line 69 of the file. I have kept everything in a single file be able to use it directly in an ultra document.

First, inside `data` there is a section for each language, different languages can have different cotents. More locales can be added, but you will need to add the new locale to the language toogle so the option becomes available.

```json
"en": {},
"fr": {},
"es": {},

```

Now, inside each locale section, these are the elements that can be customized

1. **Headers section**. Include your own wording for `about`, `skills` and `research`

    ```json
        "en": {
                        "headers": {
                            "about": "About the Instructor",
                            "skills": "Skills",
                            "research": "My Research"
                        },
    ```

2. **Instructor section**. Change this section to populate `name`, `pronoums`(optional), `about` , `image` (needs to be hosted elsewhere) ,`LinkedIn` url, `email` and `phone`.

```json
                "instructor": {
                    "name": "Sir John Cleese",
                    "pronouns": "(He/Him/His)",
                    "about": "This course is taught by the esteemed Sir John Cleese, an expert in absurdity, master of surrealism, and co-creator of Monty Python’s Flying Circus. With decades of experience in turning the ridiculous into the profound, Sir Cleese will guide you through the nuances of comedic timing, nonsensical dialogue, and why nobody expects the Spanish Inquisition.",
                    "image": "https://ultra.elearningmedia.es/bbcswebdav/xid-669405_1",
                    "linkedin": "https://www.linkedin.com/in/john-cleese/",
                    "email": "john.cleese@example.com",
                    "phone": "+1234567890",
```

3.**Skills Section**. Add skills to the skills dictionary to have then displayed as pills in the card.

```json
                    "skills": [
                        "Crop Burning",
                        "Sailing"
                    ],
```

4.**Research section**. Add as many research papers as desired, providing `title`,`description` and `link` 

```json
                    "research": [
                        {
                            "title": "The Absurdity of Comedy",
                            "description": "A deep dive into the role of absurdity in modern comedy and its impact on audiences.",
                            "link": "https://www.example.com/absurdity-comedy"
                        },
                        {
                            "title": "Comedic Timing in Surrealism",
                            "description": "Exploring how timing enhances the absurdity in surrealist comedy.",
                            "link": "https://www.example.com/comedic-timing"
                        },
                        {
                            "title": "The Impact of Nonsense Dialogues",
                            "description": "Analyzing the effect of nonsensical dialogues in the audience's perception of humor.",
                            "link": "https://www.example.com/nonsense-dialogues"
                        }
                    ],
```

5.Finally customize the **card colors** by providing values for the card´s `background`, `text`, `pillbackground` (for skills) and `pilltext`

```json

                    "colors": {
                        "background": "#FFFFFF",
                        "text": "#d16de3",
                        "pillBackground": "#d16de3",
                        "pillText": "#FFFFFF"
                    }
                }
            },

```

## Known limitations

1. This version uses Tailwind CSS from a CDN.
2. This version imports font-awesome icons from a CDN.
3. Images need to be stored somewhere, these are currently hosted in the content collection in Learn.
4. Examples are very silly.

