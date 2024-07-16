# Pricing-page

#### Issue #1: Apply Discount Code
 API method to apply a discount code to a subscription.
- **Endpoint**: `/api/pricing/discount`
- **Method**: POST
- **Parameters**
  ```
 {
  "discount_code": "string"
}
```
- **Responses**:
```
{
  "message": "Discount successfully applied"
}
```
  - Status 404: Discount code not valid.
```
{
  "error": "Discount code not valid"
}
```

#### Issue #2: Fetch Payment Methods
 API method to retrieve a list of available payment methods for subscriptions.
- **Endpoint**: `/api/pricing/payment-methods`
- **Method**: GET
- **Responses**:
  - Status 200: List of supported payment methods.
```
{
  "payment_methods": [
    "Debit/Credit Card",
    "Paypal",
    "Other"
  ]
}
```

#### Issue #3: Retrieve Pricing Plans
 API method to retrieve a list of all available pricing plans.
- **Endpoint**: `/api/pricing/plans`
- **Method**: GET
- **Responses**:
  - Status 200: A list of pricing plans.

#### Issue #4: Subscribe to a Plan
API method to initiate a subscription to a selected plan.
- **Endpoint**: `/api/pricing/plans`
- **Method**: POST
- **Parameters**:
  - `plan_id` (integer) - ID of the plan to subscribe to.
  - `payment_method` (string) - Payment method used for the subscription.
  - `user_id` (integer) - ID of the user subscribing.
- **Responses**:
  - Status 200: Successful subscription initiation.

#### Issue #5: Cancel Subscription
API method to cancel a subscription by its ID.
- **Endpoint**: `/api/pricing/subscribe/{subscriptionId}`
- **Method**: DELETE
- **Path parameters**:
  - `subscriptionId` (integer) - ID of the subscription to cancel.
- **Responses**:
  - Status 204: Subscription successfully canceled.
  - Status 404: Subscription ID not found.

#### Issue #6: Fetch Subscription Details
 API method to retrieve details of a specific subscription by ID.
- **Endpoint**: `/api/pricing/subscribe/{subscriptionId}`
- **Method**: GET
- **Path parameters**:
  - `subscriptionId` (integer) - ID of the subscription to retrieve details for.
- **Responses**:
  - Status 200: Subscription details successfully retrieved.
  - Status 404: Subscription ID not found.

#### Issue #7: Update Subscription
API method to update the details of an existing subscription.
- **Endpoint**: `/api/pricing/subscribe/{subscriptionId}`
- **Method**: PUT
- **Path parameters**:
  - `subscriptionId` (integer) - ID of the subscription to update.
- **Parameters**:
  - `payment_method` (string) - Updated payment method for the subscription.
- **Responses**:
  - Status 200: Subscription successfully updated.
  - Status 404: Subscription ID not found.

#### Issue #8: List User Subscriptions
API method to retrieve a list of subscriptions associated with a specific user.
- **Endpoint**: `/api/pricing/user/{userId}/subscriptions`
- **Method**: GET
- **Path parameters**:
  - `userId` (integer) - ID of the user to retrieve subscriptions for.
- **Responses**:
  - Status 200: List of subscriptions for the user.
  - Status 404: User ID not found.

---
