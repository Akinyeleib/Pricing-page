# Pricing-page

#### Issue #1: Apply Discount Code
 API method to apply a discount code to a subscription.
- **Endpoint**: `/api/pricing/discount`
- **Method**: POST
- **Parameters**:
  
```
{
  "discount_code": "string"
}
```
- **Responses**:
  - Status 200
```
{
  "message": "Discount successfully applied"
}

```
  - Status 404
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
  - Status 200
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
 ```
{
  "plans": [
    {
      "plan_id": 1,
      "name": "Basic",
      "description": "The essentials to provide your best work for clients.",
      "monthly_price": 800,
      "annual_price": 500,
      "features": {
        "projects": 2,
        "subscribers": 100,
        "analytics": "Basic",
        "support_response_time": "24-hour",
        "marketing_advisor": false,
        "custom_integration": false
      }
    },
    {
      "plan_id": 2,
      "name": "Premium",
      "description": "Advanced features for scaling your business.",
      "monthly_price": 3000,
      "annual_price": 2000,
      "features": {
        "projects": 25,
        "subscribers": 10000,
        "analytics": "Advanced",
        "support_response_time": "24-hour",
        "marketing_advisor": true,
        "custom_integration": true
      }
    }
  ]
}
```

#### Issue #4: Subscribe to a Plan
API method to initiate a subscription to a selected plan.
- **Endpoint**: `/api/pricing/plans`
- **Method**: POST
- **Parameters**:
```
{
  "plan_id": 1,
  "payment_method": "Debit/Credit Card",
  "user_id": 123
}
```
  - Status 200
```
{
  "message": "Subscription successfully initiated"
}
```

#### Issue #5: Cancel Subscription
API method to cancel a subscription by its ID.
- **Endpoint**: `/api/pricing/subscribe/{subscriptionId}`
- **Method**: DELETE
  - Status 204
```
{
  "message": "Subscription successfully canceled"
}
```
  - Status 404
```
{
  "error": "Subscription ID not found"
}
```
    

#### Issue #6: Fetch Subscription Details
 API method to retrieve details of a specific subscription by ID.
- **Endpoint**: `/api/pricing/subscribe/{subscriptionId}`
- **Method**: GET
- **Path parameters**:
```
{
  "subscription_id": 123,
  "plan_id": 1,
  "payment_method": "Debit/Credit Card",
  "user_id": 123,
  "status": "active",
  "start_date": "2024-07-25",
  "end_date": "2024-08-25"
}
```
  - Status 404
```
{
  "error": "Subscription ID not found"
}
```

#### Issue #7: Update Subscription
API method to update the details of an existing subscription.
- **Endpoint**: `/api/pricing/subscribe/{subscriptionId}`
- **Method**: PUT
- **Parameters**:
```
{
  "payment_method": "Paypal"
}
```
Status 200
```
{
  "message": "Subscription successfully updated"
}
```
  - Status 404
```
{
  "error": "Subscription ID not found"
}
```

#### Issue #8: List User Subscriptions
API method to retrieve a list of subscriptions associated with a specific user.
- **Endpoint**: `/api/pricing/user/{userId}/subscriptions`
- **Method**: GET
- **Parameters**:
```
{
  "user_id": 123,
  "subscriptions": [
    {
      "subscription_id": 1,
      "plan_id": 1,
      "payment_method": "Debit/Credit Card",
      "status": "active",
      "start_date": "2024-07-25",
      "end_date": "2024-08-25"
    },
    {
      "subscription_id": 2,
      "plan_id": 2,
      "payment_method": "Paypal",
      "status": "active",
      "start_date": "2024-07-25",
      "end_date": "2024-08-25"
    }
  ]
}
```

  - Status 404: User ID not found.
```
  {
    "error": "User ID not found"
  }
```
