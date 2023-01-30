---
description: Bulk upload users in CSV format.
---

# 🚅 Bulk Upload Users

You can bulk upload users to ShareMint using a CSV file. This makes it easy to import users from other sources such as Premint or Alphabot and attribute a referrer to these users.

To bulk import users, go to your project's dashboard, and click the "_Add Affiliate"_ button. Then go to the "_Bulk"_ tab.

Click "_Choose file"_ and select the CSV file to be uploaded.

The CSV file should have a header line followed by the users you'd to upload. The file must contain a column called "wallet\_address" representing the users address. You can also add a column called "referrer" which represents the referrers the address.

If you'd like to attribute all users to a single a referrer address fill in the "Referrer address" field. If the CSV already has a referrer value for a user this will be used instead. User rows without a referrer field will use the referrer you set in the "Referrer address" field in the form.

When you're ready click "Upload". Once complete you can go to the "Referee" tab of the dashboard to view the newly added users.

<figure><img src="../.gitbook/assets/CleanShot 2023-01-30 at 14.25.23.png" alt=""><figcaption><p>Bulk upload users via CSV</p></figcaption></figure>
