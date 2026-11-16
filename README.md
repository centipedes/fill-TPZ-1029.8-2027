# fill-TPZ-1029.8-2027
Autofill the Tax Credit for Childcare Expenses: Application for Advance Payments form by Revenu Quebec. 

For CPES, subsidized daycares, private daycares, and home daycare services providers who do not have software to do this and want to quickly fill these pdfs for free instead of spending hours doing it by hand.

### Contact

You can contact Kyla Lea (centipedes) through private message for any questions, problems, ideas, or suggestions :)

### Step by step instructions

**Step 1: Map fillable PDF names to client information template headers [form-fields.py]**

Double check naming convention of PDF to see if it aligns with the headers in the template file.
-> It is currently up to date but you may do so by running the **form-fields.py** script which will output a list of all the fillable pdf field names in a text file.

**Step 2: Prefill fillable PDF with business information [Business number/NAS of provider, Business Address, Phone Number, Current Date]**

Can do this by hand and then save the fillable PDF. Alternatively, may also add this information to Step 5's **fill-pdf-extra.py** form fields as an embed in the .py file.

**Step 3: Sign the prefilled PDF template [sign-pdf.py]**

Get your PDF stamped with authorized provider signature.
-> Current file is optimized to the PDF template but depending on original image size you can mess with the longitudinal coordinates in **line 10** of **sign-pdf.py**, as well as signature size.

**Step 4: Fill client information in the [client_template.xlsx] file**

