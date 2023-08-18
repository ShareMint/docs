---
description: Steps to take as part of your prelaunch checklist.
---

# 🧪 Checking your program before launch

There are two things to check before launching your ShareMint campaign:

1. That referrals are being captured by ShareMint
2. That blockchain transactions (or API events) are being recognized by ShareMint

### 1. Check referrals are being captured by ShareMint

You can check that a referral has been made by visiting the admin dashboard and clicking on the Referees tab. This page contains all the members that have been invited to the ShareMint project. To view who has invited a specific user, you can check the "Invited By" column to see which affiliate referred the user.

If a user has joined the project but you don't see an affiliate in the "Invited By" column you likely have a problem with the SDK integration and your developer needs to make sure they're sending the correct data to ShareMint when a user connects their wallet.

### 2. Check blockchain transactions are being recognized by ShareMint

Once a user is registered in the ShareMint dashboard, the next step is to check that purchases by the user are being correctly tracked by us. This can be done by making a test purchase and checking that the ShareMint dashboard picks up the transaction. If the transaction has been correctly recognized, you will see the "Purchased" and "Paid" columns update for the user. You can also check the Activity tab at the top of the page to check changes for your project.

One other thing you can check is whether we're fetching blocks for your project by visiting the bottom of the "Admin" page. You will see "Last block fetched" at the bottom. If no blocks have been fetched there is a misconfiguration with your project. This can happen if you're using a custom EVM and have used a free RPC endpoint with limited fetch capabilities.

If you're having problems with this step there's a limited amount you can do to fix it so please be in touch with our team to see if we can help. It's important step 1 is working properly before trying to fix anything in step 2. We do not track transactions if no referees are in the system.
