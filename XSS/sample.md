# Cross-Site Scripting (XSS) - Reflected XSS in Search Function

## Overview

This lab demonstrates a **Reflected Cross-Site Scripting (XSS)** vulnerability in the search functionality where user input is reflected in the response without proper sanitization.

---

## Vulnerability Type

* Reflected XSS

---

## Affected Endpoint

/search?q=

---

## Steps to Reproduce

1. Navigate to the search functionality of the application

2. Enter the following payload into the search box:

   <script>alert(1)</script>

3. Submit the request

4. Observe that the payload is executed in the browser

---

## Payload Used

<script>alert(1)</script>

---

## Why It Works

The application directly reflects user input into the HTML response without:

* Encoding special characters
* Validating input

As a result, the browser interprets the input as executable JavaScript.

---

## Impact

An attacker can:

* Execute arbitrary JavaScript in the victim's browser
* Steal session cookies
* Perform actions on behalf of the user

---

## Mitigation

* Implement proper output encoding (HTML entity encoding)
* Use security libraries/frameworks
* Apply Content Security Policy (CSP)

---

## Tools Used

* Burp Suite (Proxy, Repeater)
* Browser Developer Tools

---

