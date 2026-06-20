# Lab: DOM XSS in innerHTML sink using source location.search

## 🎯 Objective

Exploit a DOM based Vulenariblity where user input is taken from a source `location.seach` and written directly into DOM using a sing `innerHTML`.

## 🌐 Application Overview

Application contain a search bar for navigating to a specific blog post.

![Front Page](assets/img-1.png)

---

## 🔍 Recon

I intered simple hello word to see what happens.

![Hello](assets/img-2.png)

- OBSERVATION : Input is displayed on the screen.

---

## 🔎 Inspection

By inspect Element it can be seen that the input is placed within `ID "searchMessage"`.

![searchMessage](assets/img-3.png)

Now looking for the Code in the source Tab that handles the input.

![source-Code](assets/img-4.png)

- OBSERVATION : Application takes the input from `location.search` and put it inside `id "searchMessage"`.

---

## 💥 Exploit

Trying to craft a javaScript payload to see whether input is sanitized or not.

payload used `<img scr=x onerror='alert(1)'>`

![Payload](assets/img-5.png)

---

## 📸 Proof of Exploit

After the payload is injected, pop up appeared so it doesn't sanitized the input.

![Pop up](assets/img-6.png)