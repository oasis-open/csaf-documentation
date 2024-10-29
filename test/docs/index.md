# OASIS Common Security Advisory Framework (CSAF)

## What is CSAF?
Common Security Advisory Framework (CSAF) is a language to exchange Security Advisories. It plays a crucial role in the cybersecurity arena since it allows stakeholders to automate the creation and consumption of security vulnerability information and remediation.

Access our [CSAF GitHub Repository](https://github.com/oasis-tcs/csaf) and get involved in the development of the standard. Learn about the standard by reading the [CSAF Version 2.0 Specification](https://docs.oasis-open.org/csaf/csaf/v2.0/csaf-v2.0.html). Access the [CSAF Schemas](https://docs.oasis-open.org/csaf/csaf/v2.0/os/schemas/) and our [FAQs](https://github.com/oasis-tcs/csaf/blob/master/csaf_2.0/guidance/faq.md). Learn from our [CSAF Presentations](https://oasis-open.github.io/csaf-documentation/presentations.html).

----



## Open Source Tools

* [Secvisogram](https://secvisogram.github.io/) - Secvisogram is a tool for creating and editing advisories in CSAF format.
* [CSAF Visualizer](https://json.csaf.io/) - CSAF Visualizer is a tool for visualizing CSAF documents.
* [CSAF Provider](https://github.com/csaf-poc/csaf_distribution/blob/main/docs/csaf_provider.md) - An implementation of the role CSAF Trusted Provider, also offering a simple HTTPS based management service.
* [CSAF Uploader](https://github.com/csaf-poc/csaf_distribution/blob/main/docs/csaf_uploader.md) - A command line tool that uploads CSAF documents to the CSAF Provider.
* [CSAF Aggregator](https://github.com/csaf-poc/csaf_distribution/blob/main/docs/csaf_aggregator.md) - An implementation of the role CSAF Aggregator.
* [CSAF Checker](https://github.com/csaf-poc/csaf_distribution/blob/main/docs/csaf_checker.md) - A tool for testing a CSAF Trusted Provider according to Section 7 of the CSAF standard.
* [CSAF Downloader](https://github.com/csaf-poc/csaf_distribution/blob/main/docs/csaf_downloader.md) - A tool to download CSAF content from a specific domain / CSAF provider.
* [CSAF Validator Library](https://github.com/secvisogram/csaf-validator-lib) - A JavaScript library is intended to include logic that can be shared across application working with CSAF.
* [CSAF Validator Service](https://github.com/secvisogram/csaf-validator-service) - A service to validate documents against the CSAF standard. It uses the csaf-validator-lib "under-the-hood".
* [BSI CSAF Secvisogram Backend](https://github.com/secvisogram/csaf-cms-backend) - The CSAF Content Management System (CMS) Secvisogram backend code and documentation.
* [paikalta](https://pypi.org/project/paikalta/) - CSAF file testing tool available in [Pypi](https://pypi.org/project/paikalta/).
* [CSAF Walker](https://github.com/ctron/csaf-walker) - A Rust library and command line tool for consuming and analyzing CSAF documents.
* [Clouditor](https://github.com/clouditor/clouditor?tab=readme-ov-file#using-the-extra-discoverers-eg-csaf) - Clouditor is a tool for the continuous assurance of cloud and other backend services. It supports the conformance check of CSAF (trusted) providers as part of vulnerability management controls.
* [SecObserve](https://github.com/MaibornWolff/SecObserve) - An open source vulnerability management system that can produce and consume CSAF VEX documents.
* [Trivy](https://aquasecurity.github.io/trivy/) - A comprehensive and versatile security scanner that look for security issues.
* [Trustification](https://github.com/trustification/trustification) - A collection of software that allow you to store bill of materials (SBOM), vulnerability information (VEX) for your organization and use that information to learn impact of vulnerabilities and dependency changes.
* [CSAF Perl Tookit](https://metacpan.org/dist/CSAF) - A Perl distribution (with modules and command-line tools) for create, validate, convert (in HTML), publish and download CSAF documents.

## Quick Introduction to CSAF

<div class="video-wrapper">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/vQ_xY3lmZOc" frameborder="0" allowfullscreen></iframe>
</div>