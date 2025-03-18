# Describe-It Plugin Details

## Getting started
Once on the page, typically in your `<head>` section:
- include script file from cdn hosted at `https://cdn.benchmarkdigital.com/plugins/ai/describe-it/js/benchmarkgensuite.describe-it-ai.min.umd.js`
- include style file from cdn hosted at 
`https://cdn.benchmarkdigital.com/plugins/ai/describe-it/css/benchmarkgensuite.describe-it-ai.min.css`
- set license key provided to your team. YOUR_LICENSE_KEY_GOES_HERE should be replaced.

```html+js
<script src="https://cdn.benchmarkdigital.com/plugins/ai/describe-it/js/benchmarkgensuite.describe-it-ai.min.umd.js">
<link rel="stylesheet" href="https://cdn.benchmarkdigital.com/plugins/ai/describe-it/css/benchmarkgensuite.describe-it-ai.min.css">
<script>
    describeItAI.setLicenseKey('YOUR_LICENSE_KEY_GOES_HERE')
</script>
```

- later on, for whatever textarea you want to enhance with the Describe-It AI, add the `bmgs-describeit-ai` class to your textarea. Other classes can still be used for style purposes

```html
 <textarea class="bmgs-describeit-ai"></textarea>
```
That's it!

### Notes
- It is highly recommended that you protect your key and store it securely and embed as needed on pages. In the incident a license key needs to be replaced due to feature requests, or other upgrades, you would want to replace it once, rather than multiple times
- license keys are valid for the length of a contract specified unless otherwise revoked manually by the Benchmark Gensuite team

---

## Customizing
### Adding Report Value
Various properties on your text area are used to track and generate reports, those fields are:

- `id` (optional) this is the html property of id of the textarea element itself
- `name` (optional) the html property of name of the textarea element
- `data-bmgs-describeit-ai-ext-ref-type` (optional) optional html property on the textarea element to be used for custom data tracked in reporting. This is commonly an application name, form type, or other "grouping" to describe the textarea
- `data-bmgs-describeit-ai-ext-ref-id` (optional) an optional specific external id to be tracked within that previous ref-type. This is commonly a form or record id
- `data-bmgs-describeit-ai-ext-ref-name` (optional) similar to the previous external references, but an additional name property for further grouping, categorization, or friendly and readable identification

#### Examples

`id` & `name`
```html
 <textarea id="my-description" name="Description Input Area" class="bmgs-describeit-ai"></textarea>
```
all of the above, still allowing for normal text area properties like rows and max length
```html
<textarea name="InspectionAddress" class="form-control editorial-ai bmgs-describeit-ai" rows="2" maxlength="1000" id="f8604730-0e4e-46cc-a32c-d9dea296967b" data-bmgs-describeit-ai-ext-ref-type="test-ref-type" data-bmgs-describeit-ai-ext-ref-id="1234" data-bmgs-describeit-ai-ext-ref-name="foobar"></textarea>
```
any additional classes, styles, or properties should not interfere with the plugin

---

### Disabling Questions
Questions can be disabled by adding properties such as:

- `data-bmgs-disable-questions` (optional) - this is a list of questions to disable
    - valid questions are:
        - `fall` - the question that prompts how far did a person or object fall if a fall was detected
        - `burn` - the question that asks what degree of burn to be added if a burn was detected
    - single or multiple flags can be added by comma separation
- `data-bmgs-disable-flags` (optional) - this is a list of flags to disable
    - valid flags are:
        - `pii` - this is a flag for names, emails, and other basic pii detections
    - single or multiple flags can be added by comma separation

#### Examples

Disable fall question
```html
 <textarea id="my-description" name="Description Input Area" class="bmgs-describeit-ai" data-bmgs-disable-questions="fall"></textarea>
```
disable fall and burn questions

```html
 <textarea id="my-description" name="Description Input Area" class="bmgs-describeit-ai" data-bmgs-disable-questions="burn,fall" ></textarea>
```

disable fall and burn questions, and pii flag
```html
 <textarea id="my-description" name="Description Input Area" class="bmgs-describeit-ai" data-bmgs-disable-questions="fall,burn" data-bmgs-disable-flags="pii"></textarea>
```

---

## Questions?

Please reach out to your Benchmark Gensuite Support liaison for custom support.

---

Copyright © 2025 Benchmark Gensuite LLC. All rights reserved.
