# stripe-membership-automation

## What it does
When a customer completes a payment on Stripe, this automation:

1. Fetches the customer's details from Stripe API
2. Fetches their subscription to identify which plan they purchased
3. Routes them based on plan type — Annual or Monthly
4. Sends a personalised welcome email via Gmail
5. Logs the subscriber to Airtable with plan type, amount, and status

## The problem it solves
Businesses taking Stripe payments treat every customer the same 
regardless of what they bought. Annual customers who have committed 
for a full year deserve a different experience to monthly customers 
who need nurturing toward an upgrade. This automation delivers the 
right message to the right customer automatically.

## Tools used
- Stripe — payment trigger and customer/subscription data via API
- Make.com — automation layer
- Gmail — personalised welcome emails
- Airtable — subscriber database and reporting

## Flow
Stripe payment received → HTTP fetch customer email → HTTP fetch 
subscription Price ID → Router splits Annual vs Monthly → 
personalised Gmail sent → Airtable record created

## Conditional logic
- Annual plan → premium welcome email + Airtable tagged Annual
- Monthly plan → standard welcome email + upgrade nudge + Airtable tagged Monthly

## Status
✅ Complete and tested in Stripe test mode
