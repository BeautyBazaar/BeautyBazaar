BeautyBazaar Project
--------------------

Overview
--

OpenBazaar is a decentralized ecommerce platform.

We are an established ecommerce seller looking to add OB as a sales channel and integrate it into our current inventory and order management software, which is centered around WebGility.

WebGility has CSV functionality for manual import and export, which is an easy place to start for adding this new channel.

Note: OB currently does not offer support for a quantity field, but it is on the high level roadmap for the next feature release.  In the workflow below, active/inactive will be replaced with proper updating of the quantity field for the listing.

SKU creation workflow
--
1. An OB contract listing is generated for every SKU using modified OB-etsy-import script with qty set to 0 (inactive)

Inventory management workflow
--
1. wg-inventory.csv is exported from WebGility containing SKU and quantity for all items.
2. inventory-update script is ran to update OB listing quantity (make listings active) based on provided SKU AND set quantity to 0 (inactive) any OB listing that is not mentioned or has a quantity of 0.

Order management workflow
--
1. Use Export CSV feature in OB to export orders that are ready to ship.
2. ob-orders-date.csv is imported into WebGility using the manual order import function.
