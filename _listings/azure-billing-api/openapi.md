swagger: "2.0"
x-collection-name: Azure Billing API
x-complete: 1
info:
  title: ConsumptionManagementClient
  description: consumption-management-client-provides-access-to-consumption-resources-for-azure-webdirect-subscriptions--other-subscription-types-which-were-not-purchased-directly-through-the-azure-web-portal-are-not-supported-through-this-preview-api-
  version: 1.0.0
host: management.azure.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /subscriptions/{subscriptionId}/providers/Microsoft.Billing/invoices:
    get:
      summary: Invoices List
      description: Lists the available invoices for a subscription in reverse chronological
        order beginning with the most recent invoice. In preview, invoices are available
        via this API only for invoice periods which end December 1, 2016 or later.
      operationId: Invoices_List
      x-api-path-slug: subscriptionssubscriptionidprovidersmicrosoft-billinginvoices-get
      parameters:
      - in: query
        name: $expand
        description: May be used to expand the downloadUrl property within a list
          of invoices
      - in: query
        name: $filter
        description: May be used to filter invoices by invoicePeriodEndDate
      - in: query
        name: $skiptoken
        description: Skiptoken is only used if a previous operation returned a partial
          result
      - in: query
        name: $top
        description: May be used to limit the number of results to the most recent
          N invoices
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Invoice
  /subscriptions/{subscriptionId}/providers/Microsoft.Billing/invoices/{invoiceName}:
    get:
      summary: Invoices Get
      description: Gets a named invoice resource. When getting a single invoice, the
        downloadUrl property is expanded automatically.
      operationId: Invoices_Get
      x-api-path-slug: subscriptionssubscriptionidprovidersmicrosoft-billinginvoicesinvoicename-get
      parameters:
      - in: path
        name: invoiceName
        description: The name of an invoice resource
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Invoice
  /subscriptions/{subscriptionId}/providers/Microsoft.Billing/invoices/latest:
    get:
      summary: Invoices Get Latest
      description: Gets the most recent invoice. When getting a single invoice, the
        downloadUrl property is expanded automatically.
      operationId: Invoices_GetLatest
      x-api-path-slug: subscriptionssubscriptionidprovidersmicrosoft-billinginvoiceslatest-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Invoice