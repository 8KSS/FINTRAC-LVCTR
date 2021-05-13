##  FINTRAC-LVCTR
HTML page to generate JSON-LD formatted Large Virtual Currency Transaction Report (LVCTR) for upload into F2R @ FINTRAC.  

## DISCLAIMER
1. The source is free and not endorsed by FINTRAC or others.
2. When using the HTML form in the browser, _**none of the information entered is transmitted or stored**_.  The HTML page runs stand-alone through your browser.


## INTRODUCTION
The initial HTML file has been created to demonstrate how to create the JSON-LD formatted Large Virtual Currency Transaction Report that can be upload to the F2R system for Reporting Entities. It is meant to help AML compliance officers test out and convey to their technical teams how to create of the LVCTR.  This is AS-IS code and at this time is meant to help with getting to the June 1, 2021 deadline.  It is hoped that by making this open to the Dealers in Virtual Currency (DiVC) community in Canada the repository will grow and expand to make it a fully functional library for a wide variety of technical implementations to the benefit of all involved and who need this.  Ultimately, where it goes is up to the community!

## TABS
1. Root tab

This tab holds the base information about the entity, including, the reporting entity number, the internal report reference code, activity sector code, and various other sundry items.  It is meant to hold the fields that are global in nature.  

2. Identities tab

This tab holds the various identities for the person(s) or entity/entities that will be referenced in the Transaction tab.  

3. Transaction tab

This tab holds the details about the transaction and references to the persons or entities (subject) in the Identities tab.

4. FILL TEST DATA button

This button allows for the most basic version of the data to be filled in to test out the JSON file for submission into F2R.  It is by no means complete and it is hoped through the community various other use cases will be added to allow for the variety of DiVC’s transaction reporting sets.

## ASPECTS WORTH NOTING

During the creation of this HTML page there were certain items that were not clear in the documentation provided by FINTRAC. While it may be apparent to existing reporting entities who use batch modes for EFT reporting, they were not really clear to the uninitiated.  Note this section will be updated as more discoveries are made.

1. reportingEntityNumber (Root tab)

After logging into F2R (https://www6.fintrac-canafe.gc.ca/f2r/secure/reports-management/home/) this number can be found under the second tab "Organization" -> "My Organization" as "Organization number".

2. contactNumber 

This is in relation to the person who will be the contact point for the  LVCTR report that is sumitted.  It must be assigned to one of the Reporting Entities assigned persons or you will get an error.  After logging into F2R (https://www6.fintrac-canafe.gc.ca/f2r/secure/reports-management/home/) this number can be found under the second tab "Organization" -> "Users". From theredownload the users using the "Export to Excel" button.  In the file there is a field called "Contact number" which will be assigned to each authorized users of the F2R system for your organization.  Note that person has have the "Reporting permission" for "Large Virt. Crcy Transaction Report" to be able to upload the file so do check the approriate boxes in the user permissions.

3. locationReference (Transaction tab in HTML)

This is in relation to where the transaction took place.  Given that most DiVC are online, it is expect to be the place of business where the transaction take place. After logging into F2R (https://www6.fintrac-canafe.gc.ca/f2r/secure/reports-management/home/) this number can be found under the second tab "Organization" -> "Location" and is easily identified on the page under the heading, "Location identifier".

4. $id/$sref

At this time it seems that these two are tied together and that the $id is the person or entity that is setup in the Identities tab and then referenced in the various Transaction tab sections.  It seems to work that way so far, but we have yet to test out all the various use cases to confirm this.

## OTHER NOTES

1. This project is AS-IS.  

As this is a work-in-progress, not all aspects and variations of the code have been tested and thought through.  As more information becomes available and/or the community pitches in, it is hoped that this README.md file (or other parts) will grow and adapt to the specific needs, various permutations, and other use cases.

2. Pitch in! 

This code is given freely! Please help to keep it free and open to the community. If you use the code and make new discoveries or changes, please share them with the rest of the community by doing a pull request and submitting for approval.    Please ensure you test it thoroughly to help us reduce the amount of time that may be involved patching the HTML code.

3. Help make it more users friendly.

The initial version is very basic and is not user friendly.  It was done this way to bridge the initial gap between the business side (AML compliance officer) and the technical side (developers).  Any and all assistance to make this code more useable will welcomed.

4. Refactoring of the code.

The initial version was put together in under 2 weeks to be able to start testing and acquiring the knowledge in relation to filling out and submitting LVCTR JSON-LD file.  The code has not been optimized or refactored.  Any and all assistance to clean it up and optimize will be welcome.

5. Keep it as a HTML page

The initial goal to this code is to keep it as a straight up HTML page.  In this way there is no requirement to place it on a server and/or have server-side functions.  It should remain that way to allow anyone to download the HTML page, fill the fields, and submit into the F2R system.  If you have any specific implementations for other platforms or frameworks, they will be welcomed as the more we add to this the better the who industry for DiVC will be.

6. Desired functions 

Working with the initial version, there are some desired functions that would be nice to add.  So if you feel so inclined please do help out.  These desired functions include;

a) Auto-pull Blockchain sender data

Given that the biggest challenge with the Transaction portion of the LVCTR is inputting all the sending addresses, as some can be very large, there is a desire to have the ability to input in the COIN, the HASH for the transaction, and the receiving address so that the HTML page will do some sort of automatic (eg. AJAX) call to the block specific COIN block explorer to fill in all the sending addresses. 

b) Validation of JSON output before uploading

The validation rules around the JSON output currently numbers 516!  In talking with developers, it is apparent that to create the file and then upload it to find out any errors if very cumbersome.  Two levels of validation is desired in the HTML.  The first being that validation should happen as the user fills in the data, and the second at the end once the user presses submit. The first is sort of done, but still needs to be more intuitive in relation to other sections that are being filled in.  This will become apparent as more of the community gets involved.

c) Copy/Paste button or create JSON downloadable file

Once the user selects submit, they must do a select all and copy of the output to be able to paste it or upload to the F2R site.  Two options are desired at this point.  One, to be able to click a button to do the select all and copy, and the other to be able to click a button and download the JSON file for upload. 

d) Expand the “FILL TEST DATA” button for other use cases

As more learnings and the variety of use cases arises, it is hoped that this button will be expanded to include a dropdown list of the various uses cases to allow DiVC to test them out and see what results are provided for a better understanding on how to code the various use cases.  Please ensure you use FAKE data for testing, and we do not want to cause a privacy issues.  

## FINAL THOUGHTS

Given that the initial cost to develop this was not free, any and all donations are welcome to help pay for the initial development and continue to provide support for the project.  It is not a requirement, and the code is still free, but it would definitely help!

BTC - 1P2w7F1h29faKmpTmYegK6sM2HA7oMuT89

ETH - 0x38ef1B2297553Feaf65ad13A21A9C6daA5eE2849

LTC - LUHHeErdP1roxJRiu6L68DbvyD6mttREsn

DOGE - D6uGRoM95omCmJFbWZ2Bmg3bDVNoQ7Qago


Thanks in advance!

Joseph Iuso, CAMS

