# CVRF 1.2 Examples
The following are examples of CVRF advisories in XML format in accordance to the CVRF version 1.2 specification: http://docs.oasis-open.org/csaf/csaf-cvrf/v1.2/cs01/csaf-cvrf-v1.2-cs01.html

## Example 1 
Security advisory from the year 2017:
```
?xml version="1.0" encoding="UTF-8"?>
<cvrfdoc 
  xmlns:cpe="http://cpe.mitre.org/language/2.0"
  xmlns:cvrf="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/cvrf"
  xmlns:cvrf-common="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/common"
  xmlns:cvssv2="http://scap.nist.gov/schema/cvss-v2/1.0"
  xmlns:cvssv3="https://www.first.org/cvss/cvss-v3.0.xsd"
  xmlns:dc="http://purl.org/dc/elements/1.2/"
  xmlns:ns0="http://purl.org/dc/elements/1.1/"
  xmlns:prod="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/prod"
  xmlns:scap-core="http://scap.nist.gov/schema/scap-core/1.0"
  xmlns:sch="http://purl.oclc.org/dsdl/schematron"
  xmlns:vuln="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/vuln"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance
  xmlns="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/cvrf"
  >
  <!-- Document wide context information -->
  <DocumentTitle>AppY Stream Control Transmission Protocol</DocumentTitle>
  <DocumentType>Security Advisory</DocumentType>
  <DocumentPublisher Type="Vendor">
      <ContactDetails>Emergency Support: ...</ContactDetails>
      <IssuingAuthority>... Team (PSIRT)....</IssuingAuthority>
  </DocumentPublisher>
  <DocumentTracking>
    <Identification>
      <ID>vendorix-sa-20170301-abc</ID>
    </Identification>
    <Status>Final</Status>
    <Version>1.0</Version>
    <RevisionHistory>
      <Revision>
        <Number>1.0</Number>
        <Date>2017-03-01T14:58:48</Date>
        <Description>Initial public release.</Description>
      </Revision>
    </RevisionHistory>
    <InitialReleaseDate>2017-03-01T16:00:00</InitialReleaseDate>
    <CurrentReleaseDate>2017-03-01T14:58:48</CurrentReleaseDate>
    <Generator>
      <Engine>TVCE</Engine>
    </Generator>
  </DocumentTracking>
  <DocumentNotes>
    <Note Title="Summary" Type="General" Ordinal="1">A vulnerability...</Note>
    <Note Title="CVSS 3.0 Notice" Type="Other" Ordinal="2">... </Note>
  </DocumentNotes>
  <DocumentReferences>
    <Reference Type="Self">
      <URL>https://example.com/sec/vendorix-sa-20170301-abc</cvrf:URL>
      <Description>Vendorix Foo AppY...</Description>
    </Reference>
  </DocumentReferences>
  <!-- Product tree section -->
  <prod:ProductTree xmlns="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/prod">
    <Branch Name="Vendorix" Type="Vendor">
      <Branch Name="... Appliances" Type="Product Name">
        <Branch Name="1.0" Type="Product Version">
          <Branch Name=".0" Type="Service Pack">
                <FullProductName ProductID="CVRFPID-223152">...
                  AppY 1.0.0</FullProductName>
          </Branch>
          <Branch Name="(2)" Type="Service Pack">
                <FullProductName ProductID="CVRFPID-223153">... 
                  AppY 1.0(2)</FullProductName>
          </Branch>
        </Branch>
        <Branch Name="1.1" Type="Product Version">
          <Branch Name=".0" Type="Service Pack">
                <FullProductName ProductID="CVRFPID-223155">... 
                  AppY 1.1.0</FullProductName>
          </Branch>
              <Branch Name="(1)" Type="Service Pack">
                <FullProductName ProductID="CVRFPID-223156">... 
                  AppY 1.1(1)</FullProductName>
              </Branch>
        </Branch>
      </Branch>
    </Branch>
  </ProductTree>
  <!-- Vulnerability section -->
  <vuln:Vulnerability Ordinal="1" 
   xmlns="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/vuln">
    <Title>... Transmission Protocol  ...</Title>
    <ID SystemName="Vendorix Bug ID">VDXvc83320</ID>
    <Notes>
      <Note Title="Summary" Type="Summary" Ordinal="1">A vuln ...</Note>
      <Note Title="Vendorix Bug IDs" Type="Other" Ordinal="3">
        VDXvc83320</Note>
    </Notes>
    <CVE>CVE-2017-3826</CVE>
    <ProductStatuses>
      <Status Type="Known Affected">
        <ProductID>CVRFPID-223152</ProductID>
        <ProductID>CVRFPID-223153</ProductID>
        <ProductID>CVRFPID-223155</ProductID>
        <ProductID>CVRFPID-223156</ProductID>
      </Status>
    </ProductStatuses>
    <CVSSScoreSets>
      <ScoreSetV3>
        <BaseScoreV3>7.5</BaseScoreV3>
        <VectorV3>CVSS:3.0/AV:N/AC:L/PR:N/UI:N/S:U/C:N/I:N/A:H</VectorV3>
         </ScoreSetV3>
      </CVSSScoreSets>
    <Remediations>
      <Remediation Type="Workaround">
        <Description>There are no workarounds that ...</vuln:Description>
          </Remediation>
        </Remediations>
    <References>
      <Reference Type="Self">
        <URL>https://example.com/sec/vendorix-sa-20170301-abc</URL>
        <Description>... AppY Stream ...</Description>
      </Reference>
    </References>
  </Vulnerability>
  <!-- No more elements to follow -->
</cvrfdoc>
```

## Example 2
Another security advisory from the year 2017 as issued by Red Hat and migrated to CSAF CVRF 1.2 from the source CVRF 1.1 by simply updating the namespaces and prefixing all elements with the corresponding namespace of either `cvrf`, `prod`, or `vuln`. Additionally, 4 comments were added, to visually separate the three semantic top level elements `Document Context`, `Product Tree`, and `Vulnerability`):

```
<?xml version="1.0" encoding="utf-8"?>
<cvrfdoc xmlns:cpe="http://cpe.mitre.org/language/2.0"
  xmlns:cvrf="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/cvrf"
  xmlns:cvrf-common="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/common"
  xmlns:cvssv2="http://scap.nist.gov/schema/cvss-v2/1.0"
  xmlns:cvssv3="https://www.first.org/cvss/cvss-v3.0.xsd"
  xmlns:dc="http://purl.org/dc/elements/1.1/"
  xmlns:prod="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/prod"
  xmlns:scap-core="http://scap.nist.gov/schema/scap-core/1.0"
  xmlns:sch="http://purl.oclc.org/dsdl/schematron"
  xmlns:vuln="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/vuln"
  xmlns:xsi=http://www.w3.org/2001/XMLSchema-instance
  xmlns="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/cvrf"
  >
  <!-- Document wide context information -->
  <DocumentTitle xml:lang="en">Red Hat Security Advisory: python-oslo-middleware security update</DocumentTitle>
  <DocumentType>Security Advisory</DocumentType>
  <DocumentPublisher Type="Vendor">
    <ContactDetails>secalert@redhat.com</ContactDetails>
    <IssuingAuthority>Red Hat Product Security</IssuingAuthority>
  </DocumentPublisher>
  <DocumentTracking>
    <Identification>
      <ID>RHSA-2017:0435</ID>
    </Identification>
    <Status>Final</Status>
    <Version>1</Version>
    <RevisionHistory>
      <Revision>
        <Number>1</Number>
        <Date>2017-03-02T21:13:00Z</Date>
        <Description>Current version</Description>
      </Revision>
    </RevisionHistory>
    <InitialReleaseDate>2017-03-02T21:13:00Z</InitialReleaseDate>
    <CurrentReleaseDate>2017-03-02T21:13:00Z</CurrentReleaseDate>
    <Generator>
      <Engine>Red Hat rhsa-to-cvrf 2.0</Engine>
      <Date>2017-03-04T05:06:05Z</Date>
    </Generator>
  </DocumentTracking>
  <DocumentNotes>
    <Note Title="Topic" Type="Summary" Ordinal="1" xml:lang="en">
An update for python-oslo-middleware is now available for Red Hat OpenStack Platform 9.0 (Mitaka).

Red Hat Product Security has rated this update as having a security impact of Moderate. A Common Vulnerability Scoring System (CVSS) base score, which gives a detailed severity rating, is available for each vulnerability from the CVE link(s) in the References section.    </Note>
    <Note Title="Details" Type="General" Ordinal="2" xml:lang="en">
The OpenStack Oslo Middleware library provides components that can be injected into WSGI pipelines to intercept request and response flows. The base class can be enhanced with functionality like adding or updating HTTP headers, or to offer support for limiting size or connections.

Security Fix(es):

* An information-disclosure flaw was found in oslo.middleware. Software using the CatchError class could include sensitive values in a traceback's error message. System users could exploit this flaw to obtain sensitive information from OpenStack component error logs (for example, keystone tokens). (CVE-2017-2592)
Red Hat would like to thank the OpenStack project for reporting this issue. Upstream acknowledges Divya K Konoor (IBM) as the original reporter.    </Note>
    <Note Title="Terms of Use" Ordinal="3" Type="Legal Disclaimer" xml:lang="en">Please see https://www.redhat.com/footer/terms-of-use.html</Note>
  </DocumentNotes>
  <DocumentDistribution xml:lang="en">Copyright © 2017 Red Hat, Inc. All rights reserved.</DocumentDistribution>
  <AggregateSeverity Namespace="https://access.redhat.com/security/updates/classification/">Moderate</AggregateSeverity>
  <DocumentReferences>
    <Reference Type="Self">
      <URL>https://rhn.redhat.com/errata/RHSA-2017-0435.html</URL>
      <Description>https://rhn.redhat.com/errata/RHSA-2017-0435.html</Description>
    </Reference>
    <Reference>
      <URL>https://access.redhat.com/security/updates/classification/#moderate</URL>
      <Description>https://access.redhat.com/security/updates/classification/#moderate</Description>
    </Reference>
  </DocumentReferences>
  <!-- Product tree section -->
  <prod:ProductTree xmlns="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/prod">
    <Branch Type="Product Family" Name="Red Hat Enterprise Linux OpenStack Platform">
      <Branch Type="Product Name" Name="Red Hat OpenStack Platform 9.0">
        <FullProductName ProductID="7Server-RH7-RHOS-9.0">Red Hat OpenStack Platform 9.0</FullProductName>
      </Branch>
    </Branch>
    <Branch Type="Product Version" Name="python-oslo-middleware-3.7.0-2.el7ost">
      <FullProductName ProductID="python-oslo-middleware-3.7.0-2.el7ost">python-oslo-middleware-3.7.0-2.el7ost.src.rpm</prod:FullProductName>
    </Branch>
    <Relationship ProductReference="python-oslo-middleware-3.7.0-2.el7ost"
      RelationType="Default Component Of" RelatesToProductReference="7Server-RH7-RHOS-9.0">
      <FullProductName ProductID="7Server-RH7-RHOS-9.0:python-oslo-middleware-3.7.0-2.el7ost">python-oslo-middleware-3.7.0-2.el7ost as a component of Red Hat OpenStack Platform 9.0</FullProductName>
    </Relationship>
  </ProductTree>
  <!-- Vulnerability section -->
  <vuln:Vulnerability Ordinal="1" 
   xmlns="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/vuln">
    <Notes>
      <Note Title="Vulnerability Description" Type="General" Ordinal="1" xml:lang="en">An information-disclosure flaw was found in oslo.middleware. Software using the CatchError class could include sensitive values in a traceback's error message. System users could exploit this flaw to obtain sensitive information from OpenStack component error logs (for example, keystone tokens). </Note>
    </Notes>
    <DiscoveryDate>2017-01-18T00:00:00Z</DiscoveryDate>
    <ReleaseDate>2017-01-26T00:00:00Z</ReleaseDate>
    <Involvements>
      <Involvement Party="Vendor" Status="Completed"/>
    </Involvements>
    <CVE>CVE-2017-2592</CVE>
    <ProductStatuses>
      <Status Type="Fixed">
        <ProductID>7Server-RH7-RHOS-9.0:python-oslo-middleware-3.7.0-2.el7ost</ProductID>
      </Status>
    </ProductStatuses>
    <Threats>
      <Threat Type="Impact">
        <Description>Moderate</Description>
      </Threat>
    </Threats>
 

    <Remediations>
      <Remediation Type="Vendor Fix">
        <Description xml:lang="en">
For details on how to apply this update, which includes the changes described in this advisory, refer to:

https://access.redhat.com/articles/11258    </Description>
        <URL>https://rhn.redhat.com/errata/RHSA-2017-0435.html</URL>
      </Remediation>
    </Remediations>
    <References>
      <Reference>
        <URL>https://access.redhat.com/security/cve/CVE-2017-2592</URL>
        <Description>CVE-2017-2592</vuln:Description>
      </Reference>
      <Reference>
        <URL>https://bugzilla.redhat.com/show_bug.cgi?id=1414698</URL>
        <Description>bz#1414698: CVE-2017-2592 python-oslo-middleware: CatchErrors leaks sensitive values into error logs</Description>
      </Reference>
    </References>
    <Acknowledgments>
      <Acknowledgment>
        <Description>Red Hat would like to thank the OpenStack project for reporting this issue. Upstream acknowledges Divya K Konoor (IBM) as the original reporter.</Description>
      </Acknowledgment>
    </Acknowledgments>
  </Vulnerability>
  <!-- No more elements to follow -->
</cvrfdoc>
```

## Example 3
Yet another security advisory from the year 2017 as issued by Cisco and migrated to CSAF CVRF 1.2 from the source CVRF 1.1 by simply updating the namespaces and prefixing all elements with the corresponding namespace of either cvrf or vuln. Additionally, 3 comments are added, to visually separate the three semantic top level elements Document Context, and Vulnerability (Note: This advisory has no Product Tree instance!):
```
<?xml version="1.0" encoding="UTF-8"?>
<cvrfdoc xmlns:xsd="http://www.w3.org/2001/XMLSchema"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xmlns:cvrf="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/cvrf"
  xmlns:cvrf-common="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/common"
  xmlns:prod="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/prod"
  xmlns:vuln="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/vuln"
  xmlns=="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/cvrf"
  >
  <!-- Document wide context information -->
  <DocumentTitle>Apache Struts2 Jakarta Multipart Parser File Upload Code Execution Vulnerability Affecting Cisco Products<DocumentTitle>
  <DocumentType>Cisco Security Advisory<DocumentType>
  <DocumentPublisher Type="Vendor">
    <ContactDetails>Emergency Support: 
+1 877 228 7302 (toll-free within North America)
+1 408 525 6532 (International direct-dial)
Non-emergency Support:
Email: psirt@cisco.com
Support requests that are received via e-mail are typically acknowledged within 48 hours.</ContactDetails>
    <IssuingAuthority>Cisco product security incident response is the responsibility of the Cisco Product Security Incident Response Team (PSIRT). The Cisco PSIRT is a dedicated, global team that manages the receipt, investigation, and public reporting of security vulnerability information that is related to Cisco products and networks. The on-call Cisco PSIRT works 24x7 with Cisco customers, independent security researchers, consultants, industry organizations, and other vendors to identify possible security issues with Cisco products and networks.
More information can be found in Cisco Security Vulnerability Policy available at http://www.cisco.com/web/about/security/psirt/security_vulnerability_policy.html</cvrf:IssuingAuthority>
  </DocumentPublisher>
  <DocumentTracking>
    <Identification>
      <ID>cisco-sa-20170310-struts2</ID>
    </Identification>
    <Status>Interim</Status>
    <Version>1.4</Version>
    <RevisionHistory>
      <Revision>
        <Number>1.0</Number>
        <Date>2017-03-10T20:43:55</Date>
        <Description>Initial public release.</Description>
      </Revision>
      <Revision>
        <Number>1.1</Number>
        <Date>2017-03-11T23:37:26</Date>
        <Description>Updated product lists.</Description>
      </Revision>
      <Revision>
        <Number>1.2</Number>
        <Date>2017-03-13T00:06:20</Date>
        <Description>Updated product lists.</Description>
      </Revision>
      <Revision>
        <Number>1.3</Number>
        <Date>2017-03-13T22:24:49</Date>
        <Description>Updated product lists.</Description>
      </Revision>

      <Revision>
        <Number>1.4</Number>
        <Date>2017-03-14T21:03:12</Date>
        <Description>Updated product lists.</Description>
      </Revision>
    </RevisionHistory>
    <InitialReleaseDate>2017-03-10T19:30:00</InitialReleaseDate>
    <CurrentReleaseDate>2017-03-14T21:03:12</CurrentReleaseDate>
    <Generator>
      <Engine>TVCE</Engine>
    </Generator>
  </DocumentTracking>
  <DocumentNotes>
    <Note Title="Summary" Type="General" Ordinal="1">On March 6, 2017, Apache disclosed a vulnerability in the Jakarta multipart parser used in Apache Struts2 that could allow an attacker to execute commands remotely on the targeted system using a crafted Content-Type header value.

This vulnerability has been assigned CVE-ID CVE-2017-5638.

This advisory is available at the following link:
https://tools.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-20170310-struts2 ["https://tools.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-20170310-struts2"]</Note>
    <Note Title="CVSS 3.0 Notice" Type="Other" Ordinal="2">Although CVRF version 1.1 does not support CVSS version 3, the CVSS score in this CVRF file is a CVSSv3 base and temporal score, as Cisco is now scoring vulnerabilities in CVSSv3.</Note>
  </DocumentNotes>
  <DocumentReferences>
    <Reference Type="Self">
      <URL>https://tools.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-20170310-struts2</URL>
      <Description>Apache Struts2 Jakarta Multipart Parser File Upload Code Execution Vulnerability Affecting Cisco Products</Description>
    </Reference>
  </DocumentReferences>
  <!-- Vulnerability section -->
  <Vulnerability Ordinal="1" 
   xmlns="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/vuln">
    <Title>Apache Struts Jakarta Multipart Parser File Upload Code Execution Vulnerability</Title>
    <Notes>
      <Note Title="Summary" Type="Summary" Ordinal="1">A vulnerability in the Jakarta multipart parser of Apache Struts could allow an unauthenticated, remote attacker to execute arbitrary code on an affected system.



The vulnerability is due to improper handling of the Content-Type header value when performing a file upload based on the Jakarta multipart parser of the affected software. An attacker could exploit this vulnerability by persuading a targeted user to upload a malicious file. Once the Jakarta multipart parser of the affected application uploads the file, the attacker could have the ability to execute arbitrary code.</Note>
    </Notes>
    <CVE>CVE-2017-5638</CVE>
    <Remediations>
      <Remediation Type="Workaround">
        <Description>Any workarounds, when available, are documented in the Cisco bugs, which are accessible through the Cisco Bug Search Tool ["https://bst.cloudapps.cisco.com/bugsearch/bug/BUGID"].</Description>
      </Remediation>
    </Remediations>

    <References>
      <Reference Type="Self">
        <vuln:URL>https://tools.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-20170310-struts2</vuln:URL>
        <Description>Apache Struts2 Jakarta Multipart Parser File Upload Code Execution Vulnerability Affecting Cisco Products</Description>
      </Reference>
    </References>
  </Vulnerability>
  <!-- No more elements to follow -->
</cvrfdoc>
```

## Example 4
Minimal valid CSAF CVRF version 1.2 document (neither `Product Tree` nor `Vulnerability` noted, but nevertheless well-formed and valid):
```
<?xml version="1.0" encoding="UTF-8"?>
<cvrfdoc xmlns:cvrf="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/cvrf">
  <DocumentTitle>DocumentTitle0</DocumentTitle>
  <DocumentType>DocumentType0</DocumentType>
  <DocumentPublisher Type="Vendor">
  </DocumentPublisher>
  <DocumentTracking>
    <Identification>
      <ID>ID0</ID>
    </Identification>
    <Status>Draft</Status>
    <Version>1</Version>
    <RevisionHistory>
      <Revision>
        <Number>1.0</Number>
        <Date>2038-05-04T18:13:51.0</Date>
        <Description>Something wrong with some product</Description>
      </Revision>
      <Revision>
        <Number>1.1</Number>
        <Date>2038-05-04T18:13:52.0</Date>
        <Description>We excluded some products, but still in the fog</Description>
      </Revision>
    </RevisionHistory>
    <InitialReleaseDate>2038-05-04T18:13:51.0</InitialReleaseDate>
    <CurrentReleaseDate>2038-05-04T18:13:52.0</CurrentReleaseDate>
  </DocumentTracking>
</cvrfdoc>
```

## Example 5

A “Minimal Viable Product” like fictitious sample valid CSAF CVRF version 1.2 document is given in the following example.
The vendor is assumed to be named ACME Inc., and DNS-wise only hosted on a subdomain of example.com i.e. https://acme.example.com/ and per time zone offset 6 hours “behind” UTC.
A product foo is declared to be available on platforms bar and baz alike and in version 1.9 and 2.1.
The CVE is made up and uses the new format (as it exceeds the historic 9999 limit of early years, in the hope, that in 2017 there will never be a real CVE-2017-99999.
No CWE is given. A CVSS Score is given in CVSSv3 and this is repeated in the human readable portions (maybe because the vendor uses this as accessibility feature).
Some possible combinations of vulnerability and mitigation states are realized i.e.:
·         Product foo is always known to be affected on platform bar.
·         Product foo is always known not to be affected on platform baz.
A remediation page is offered at https://acme.example.com/sa/acme-2017-42-1-1.html an everyone is entitled, but this fact is written in Italian: “Tutte le persone su questo pianeta” (English: “All people on this planet”).
The source of the CSAF CVRF version 1.2 security advisory (XML) is offered at https://acme.example.com/sa/acme-2017-42-1-1.xml and an also fictitious variant (for now vendor private) in JSON at https://acme.example.com/sa/acme-2017-42-1-1.json.
Note also the two revisions (in total), maybe the initial release of the security advisory did not take into account, that the product when installed on the baz platform is unaffected, or there was given the wrong exploit byte value (not the current 0x42 without access to the initial revision, and no explanation in the release notes, the world will never know (only that something has been corrected).
The acknowledgment was maybe chosen by the company lawyers to not list the real name of the external contributor where the below sample content states “Some One (not to be named explicitly)” – and no dummy Organization is added.
The complexity of the Affected/Non-Affected mixture may have forced the publisher to not take the internal usual product IDs but instead append the interesting dimension in a simple serialization as:
 “-on-bar” and “-on-baz” respectively. In a real life advisory, these simple platform names might have become fully fledged product entries themselves with relationship link elements between them.
Albeit speculating here, there might have been some time pressure on the publishing vendor Acme Inc. of the products foo version 1.9 and 2.1, as sending the byte 0x42 to some port seems to be cheap on the attacker side … at least for the effect of it, when the products are hosted on platform baz.

```
<?xml version='1.0' encoding='UTF-8'?>
<cvrfdoc xmlns:cpe="http://cpe.mitre.org/language/2.0"
   xmlns:cvrf="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/cvrf"
   xmlns:cvrf-common="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/common"
   xmlns:cvssv2="http://scap.nist.gov/schema/cvss-v2/1.0"
   xmlns:cvssv3="https://www.first.org/cvss/cvss-v3.0.xsd"
   xmlns:dc="http://purl.org/dc/elements/1.2/"
   xmlns:ns0="http://purl.org/dc/elements/1.1/"
   xmlns:prod="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/prod"
   xmlns:scap-core="http://scap.nist.gov/schema/scap-core/1.0"
   xmlns:sch="http://purl.oclc.org/dsdl/schematron"
   xmlns:vuln="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/vuln"
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
   xmlns="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/cvrf">

   <!-- Document wide context information -->
   <DocumentTitle xml:lang="en">Acme Security Advisory for foo on bar - March 2017 - CSAF CVRF</DocumentTitle>
   <DocumentType xml:lang="en">Acme Security Advisory</DocumentType>
   <DocumentPublisher Type="Vendor"/>
   <DocumentTracking>
      <Identification>
         <ID>acme-2017-42</ID>
      </Identification>
      <Status>Final</Status>
      <Version>1.0</Version>
      <RevisionHistory>
         <Revision>
            <Number>1.0</Number>
            <Date>2017-03-17T12:34:56-06:00</Date>
            <Description>Initial Distribution</Description>
         </Revision>
         <Revision>
            <Number>1.1</Number>
            <Date>2017-03-18T01:23:45-06:00</Date>
            <Description>Corrected Distribution</Description>
         </Revision>
      </RevisionHistory>
      <InitialReleaseDate>2017-01-17T12:34:56-06:00</InitialReleaseDate>
      <CurrentReleaseDate>2017-01-18T01:23:34-06:00</CurrentReleaseDate>
   </DocumentTracking>
   <DocumentNotes>
      <Note Audience="All" Ordinal="1" Title="Summary" Type="Summary" xml:lang="en">
         This document contains descriptions of Acme product security vulnerabilities with details on impacted and non-impacted platform product combinations.
         Additional information regarding these vulnerabilities including fix distribution information can be found at the Acme sites referenced in this document.</Note>
   </DocumentNotes>
   <DocumentDistribution>This document is published at: https://acme.example.com/sa/acme-2017-42-1-1.xml</DocumentDistribution>
   <DocumentReferences>
      <Reference Type="External">
         <URL>https://acme.example.com/sa/acme-2017-42-1-1.json</URL>
         <Description>URL to JSON version of Advisory</Description>
      </Reference>
   </DocumentReferences>
   <Acknowledgments>
      <Acknowledgment>
         <Name>Some One (not to be named explicitly)</Name>
      </Acknowledgment>
      <Acknowledgment>
         <Name>Jane Employee</Name>
         <Organization>Acme Inc.</Organization>
      </Acknowledgment>
   </Acknowledgments>

   <!-- Product tree section -->
   <ProductTree xmlns="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/prod">
      <Branch Name="Acme" Type="Vendor">
         <Branch Name="Acme Things" Type="Product Family">
            <Branch Name="Things On bar" Type="Product Name">
               <Branch Name="1.9" Type="Product Version">
                  <FullProductName ProductID="AC-FOO-1.9-on-bar">Foo 1.9 on bar</FullProductName>
               </Branch>
               <Branch Name="2.1" Type="Product Version">
                  <FullProductName ProductID="AC-FOO-2.1-on-bar">Foo 2.1 on bar</FullProductName>
               </Branch>
            </Branch>
            <Branch Name="Things On baz" Type="Product Name">
               <Branch Name="1.9" Type="Product Version">
                  <FullProductName ProductID="AC-FOO-1.9-on-baz">Foo 1.9 on baz</FullProductName>
               </Branch>
               <Branch Name="2.1" Type="Product Version">
                  <FullProductName ProductID="AC-FOO-2.1-on-baz">Foo 2.1 on baz</FullProductName>
               </Branch>
            </Branch>
         </Branch>
       </Branch>
   </ProductTree>

   <!-- Vulnerability sections -->
   <Vulnerability Ordinal="1" xmlns="http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/vuln">
      <Title>Vulnerability in the TCP component of Acme foo (CVE-2017-99999)</Title>
      <Notes>
         <Note Audience="All" Ordinal="1" Title="Details" Type="Details">
            Vulnerability in the TCP component of Acme foo.  
            Supported versions that are affected are 1.9, and 2.0 when installed on bar but not affected when on baz. 
            Easily exploitable vulnerability allows unauthenticated attacker with network access via a single 0x42 value payload byte to compromise Acme foo.
            Successful attacks of this vulnerability can result in unauthorized read access to a subset of Acme foo accessible data and unauthorized ability to cause a complete denial of service (DOS) of Acme foo. 
            CVSS 3.0 Base Score 9.8 (Confidentiality and Availability impacts). 
            CVSS Vector: CVSS:3.0/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H).</Note>
      </Notes>
      <Involvements>
         <Involvement Party="Vendor" Status="Completed">
            <Description>Fix has been released</Description>
         </Involvement>
      </Involvements>
      <CVE>CVE-2017-99999</CVE>
      <ProductStatuses>
         <Status Type="Known Affected">
            <ProductID>AC-FOO-1.9-on-bar</ProductID>
            <ProductID>AC-FOO-2.1-on-bar</ProductID>
         </Status>
         <Status Type="Known Not Affected">
            <ProductID>AC-FOO-1.9-on-baz</ProductID>
            <ProductID>AC-FOO-2.1-on-baz</ProductID>
         </Status>
      </ProductStatuses>
      <CVSSScoreSets>
         <ScoreSetV3>
            <BaseScoreV3>9.8</BaseScoreV3>
            <VectorV3>CVSS:3.0/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H</VectorV3>
         </ScoreSetV3>
      </CVSSScoreSets>
      <Remediations>
         <Remediation Type="Vendor Fix">
            <Description>acme-2017-42</Description>
            <Entitlement xml:lang="it">Tutte le persone su questo pianeta</Entitlement>
            <URL>https://acme.example.com/sa/acme-2017-42-1-1.html</URL>
            <ProductID>AC-FOO-1.9-on-bar</ProductID>
            <ProductID>AC-FOO-2.1-on-bar</ProductID>
         </Remediation>
      </Remediations>
   </Vulnerability>
   <!-- No more elements to follow -->
</cvrfdoc>
```

All of these examples can be downloaded as individual files at:




