# Change Log

**Thursday, July 12 2018**

* Insert `notes` attribute to transaction object [transaction object](#transaction-object)
* Insert `notes` attribute to user object [user object](#user-object)

**Thursday, July 05 2018**

* Create [Verify Email](#verify-email) endpoint.
* Remove token param in [Verify Phone Number](#verify-phone-number) endpoint.
* Change response's structure in transaction's [callback](#callback).

**Tuesday, July 03 2018**

* Add account_name & account_number field to [Get Bank Detail](#get-bank-detail) reponse.
* Add unique_code field to [transaction object](#transaction-object).
* Change [create transaction](#create-transaction) response to return [transaction object](#transaction-object) instead.
* Add `WRONG_ACCOUNT_NUMBER` at `status` attribute on transaction object data
* Add `notes`  attribute on transaction object data

**Thursday, June 07 2018**

* Create [Get All Registered Users](#get-all-registered-user) and [Get All Created Transactions](#get-all-created-transaction) endpoints.
* Update [Error Codes](#error-codes).

**Thursday, May 31 2018**

* Create [Logout](#logout) endpoint.

**Tuesday, May 29 2018**

* Change [Update User](#update-user) endpoint. This endpoint cannot upload identity images anymore. See [Upload User Identity Image](#upload-user-identity-image).
* Create [Upload User Identity Image](#upload-user-identity-image) endpoint.

**Wednesday, April 25 2018**

* Initial Commit.