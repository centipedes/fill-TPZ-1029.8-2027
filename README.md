# fill-TPZ-1029.8-2027
Autofill the Tax Credit for Childcare Expenses: Application for Advance Payments form by Revenu Quebec. 

For CPES, subsidized daycares, private daycares, and home daycare services providers who do not have software to do this and want to quickly fill these pdfs for free instead of spending hours doing it by hand.

### Contact

You can contact Kyla Lea (centipedes) through private message for any questions, problems, ideas, or suggestions :)

### Step by step instructions

**Step 1: Prefill fillable PDF with business information [Business number/NAS of provider, Business Address, Phone Number, Current Date] & Fill client information in the [client_template.xlsx] file**

Can do this by hand and then save the fillable PDF. Alternatively, may also add this information to Step 3's **fill-pdf-extra.py** form fields as an embed in the .py file.

Fill the client information template. Make sure the SIN numbers are correct. Each row pertains to a particular client parent filer. 

All children belonging to a single parent filer go into subsequent columns, with:

> nom1a being the child's Lastname, First name

> date1a being the child's date of birth in YYYYMMDD format

> tarif1a being the child's daily rate

> jour1a being the total number of attendance days in the fiscal year

Any subsequent children follow the header convention on the row [nom2a,date2a,tarif2a,jour2a] etc up to 6 children

**Step 2: Sign the prefilled PDF template [2-sign-pdf.py]**

Get your PDF stamped with authorized provider signature. You may omit if you have ADOBE Acrobat PRO that can sign fillable PDFs.

-> Current file is optimized to the PDF template but depending on original image size you can mess with the longitudinal coordinates in **line 15** of **2-sign-pdf.py**, as well as signature size.  

**Step 3: Create a prefilled pdf for each client parent filer**

__Option A [3a-fill-pdf.py]: Prefilled and Saved Business Information (NEQ/Nas, Business name, Address, Phone, Date) in Step 1__

__Option B [3b-fill-pdf-extra.py]: Add this information directly to [fill-pdf-extra.py]__
