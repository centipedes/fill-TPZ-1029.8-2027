# fill-TPZ-1029.8-2027
Autofill the Tax Credit for Childcare Expenses: Application for Advance Payments form by Revenu Quebec. 

For CPEs, subsidized daycares, private daycares, and home daycare services providers who do not have software to do this and want to quickly fill these pdfs for free instead of spending hours doing it by hand.

> **Privacy Note:** Never upload populated `client_template.xlsx` files, signed PDFs, or your `signature.png` to a public GitHub repository. Keep all client SINs and signature files strictly on your local machine.

### Prerequisites & Setup

1. Install **Python 3.10+** (check "Add Python to PATH" during installation on Windows).
2. Open your terminal/command prompt inside this folder and install the required libraries:
   ```bash
   pip install pypdf reportlab openpyxl

### Step by step instructions

**Step 1: Prefill fillable PDF with business information [Business number/NAS of provider, Business Address, Phone Number, Current Date] & Fill client information in the [client_template.xlsx] file**

Can do this by hand and then save the fillable PDF. Alternatively, may also add this information to Step 3B's **3b-fill-pdf-extra.py** form fields as an embed in the .py file.

Fill the client information template. Make sure all SIN numbers are correct. Each row pertains to a particular client parent filer. 

All children belonging to a single parent filer go into subsequent columns, with:

> nom1a being the child's Lastname, First name

> date1a being the child's date of birth in YYYYMMDD format

> tarif1a being the child's daily rate

> jour1a being the total number of attendance days in the fiscal year

Any subsequent children follow the header convention on the row [nom2a,date2a,tarif2a,jour2a] etc up to 6 children

**Step 2: Sign the prefilled PDF template [2-sign-pdf.py]**

Get your PDF stamped with authorized provider signature. You may omit if you have Adobe Acrobat PRO installed that can sign fillable PDFs.

-> Current file is optimized to the PDF template but depending on original image size you can mess with the longitudinal coordinates in **line 15** of **2-sign-pdf.py**, as well as signature size.  

Place a transparent PNG of your signature named signature.png in the project folder alongside the base PDF ACTCA-2027.pdf or signed_ACTCA-2027.pdf & filled client_template.xlsx.

Run the signing script:
   ```bash
   python 2-sign-pdf.py

**Step 3: Batch-Generate Client PDFs**

__Option A [3a-fill-pdf.py]: Prefilled and Saved Business Information (NEQ/Nas, Business name, Address, Phone, Date) in Step 1__
   ```bash
   python 3a-fill-pdf.py

__Option B [3b-fill-pdf-extra.py]: Add this information directly to [fill-pdf-extra.py]__
   ```bash
   python 3b-fill-pdf-extra.py

All completed parent forms will be saved to the output directory ready for distribution.

### Contact
Have questions, bugs, or suggestions? Open an Issue in this repository or reach out to Kyla Lea (@centipedes).

