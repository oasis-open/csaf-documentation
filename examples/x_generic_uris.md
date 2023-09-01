# Using X_Generic_URIs
The [Common Security Advisory Framework (CSAF) "Full Product Name Type - Product Identification Helper"](https://docs.oasis-open.org/csaf/csaf/v2.0/os/csaf-v2.0-os.html#3133-full-product-name-type---product-identification-helper) is a construct within CSAF that helps to identify a product more precisely.

The `product_identification_helper` is an object that contains one or more properties that can be used to identify a product. The idea is to offer a variety of ways to identify a product so that it can be correlated with data in an asset management system, vulnerability management system, or any other relevant system.

Here are the eight properties you can include in the `product_identification_helper`:

1. **CPE**: Common Platform Enumeration string
2. **Hashes**: Hash values (e.g., SHA-256) representing the product
3. **Model Numbers**: List of model numbers for the product
4. **PURL**: Package URL, often used in software composition analysis
5. **SBOM URLs**: URLs to the Software Bill of Materials
6. **Serial Numbers**: List of serial numbers for physical products
7. **SKUs**: Stock Keeping Units
8. **X_Generic_URIs**: Any other custom URIs to identify the product


The `X_Generic_URIs` field serves as a catch-all container for any URI that does not fit into the predefined categories within the `product_identification_helper` object in the Common Security Advisory Framework (CSAF). This field can be particularly useful for organizations that have their own proprietary or internal ways of identifying products, especially those that may not be covered by the other more standard identifiers like CPE, hashes, or SKUs.



### Example

In JSON format as per the CSAF standard, the `X_Generic_URIs` might look something like this:

```json
    "x_generic_uris": [
        {
          "namespace": "https://example.com/explain-your-erp-system-ids",
          "uri": "urn:private:erp-system:<erp-number>"
        }
      ]
```

By using `X_Generic_URIs`, you offer yet another flexible mechanism for parties receiving the security advisory to identify products accurately within their own systems, leveraging their existing asset identification mechanisms. A real-world example:

```json
    "x_generic_uris": [
        {
          "namespace": "https://bosch.com/I-made-this-url-up/explain-your-erp-system-ids",
          "uri": "urn:private:sap:F.01U.381.159"
        }
      ]
```

In the example above, the `x_generic_uris` field contains an array with a single object that includes two properties: `namespace` and `uri`.

1. **Namespace**: The `namespace` field contains a URL that serves as a kind of contextual label or category for the `uri`. In this case, it points to a fictitious URL at Bosch’s domain, which could serve as a reference for understanding what the following URI represents. By adding a `namespace`, the organization sending out the advisory provides additional context or explanation for where or how this custom URI is used. For example, the URL may point to documentation that describes the system of IDs being used ("erp-system-ids").

2. **URI**: The `uri` field contains the actual unique resource identifier for the asset or product. Here, "urn:private:sap:F.01U.381.159" is a URN (Uniform Resource Name), a form of URI that identifies resources by name in a particular namespace. It is designated as "private", suggesting that it's an internal or proprietary naming scheme, and it looks like it may be referring to a product ID in an SAP ERP system.

### How it works:

When a CSAF document is distributed with this `x_generic_uris` field, the consumer of the document would look at the URI and the namespace to determine which asset or product is affected by the security advisory. The `namespace` provides a clue about what system the URI pertains to, or how to interpret the URI. In this case, it suggests that the identifier is meaningful within the context of SAP ERP system IDs. The consumer could then use the URN ("F.01U.381.159") to locate the specific asset in their own SAP ERP system or any system where this ID is relevant.

By using a custom namespace and URI in this manner, organizations can provide a lot of flexibility and context in identifying assets, especially in complex environments where off-the-shelf identifiers like CPEs or hashes may not be applicable.