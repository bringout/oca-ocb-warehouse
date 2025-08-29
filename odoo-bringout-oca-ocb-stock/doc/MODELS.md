# Models

Detected core models and extensions in stock.

```mermaid
classDiagram
    class procurement_group
    class product_removal
    class stock_location
    class stock_lot
    class stock_move
    class stock_move_line
    class stock_package_level
    class stock_package_type
    class stock_picking
    class stock_picking_type
    class stock_putaway_rule
    class stock_quant
    class stock_quant_package
    class stock_route
    class stock_rule
    class stock_scrap
    class stock_storage_category
    class stock_storage_category_capacity
    class stock_warehouse
    class stock_warehouse_orderpoint
    class barcode_rule
    class product_category
    class product_packaging
    class product_product
    class product_template
    class res_company
    class res_config_settings
    class res_partner
    class uom_uom
    class res_company
    stock_package_type --> res_company : company_id (Many2one)
    class stock_storage_category_capacity
    stock_package_type --> stock_storage_category_capacity : storage_category_capacity_ids (One2many)
    class product_product
    stock_putaway_rule --> product_product : product_id (Many2one)
    class product_category
    stock_putaway_rule --> product_category : category_id (Many2one)
    class stock_location
    stock_putaway_rule --> stock_location : location_in_id (Many2one)
    class stock_location
    stock_putaway_rule --> stock_location : location_out_id (Many2one)
    class res_company
    stock_putaway_rule --> res_company : company_id (Many2one)
    class stock_package_type
    stock_putaway_rule --> stock_package_type : package_type_ids (Many2many)
    class stock_storage_category
    stock_putaway_rule --> stock_storage_category : storage_category_id (Many2one)
    class product_product
    stock_quant --> product_product : product_id (Many2one)
    class product_template
    stock_quant --> product_template : product_tmpl_id (Many2one)
    class uom_uom
    stock_quant --> uom_uom : product_uom_id (Many2one)
    class stock_location
    stock_quant --> stock_location : location_id (Many2one)
    class stock_warehouse
    stock_quant --> stock_warehouse : warehouse_id (Many2one)
    class stock_lot
    stock_quant --> stock_lot : lot_id (Many2one)
    class stock_quant_package
    stock_quant --> stock_quant_package : package_id (Many2one)
    class res_partner
    stock_quant --> res_partner : owner_id (Many2one)
    class res_users
    stock_quant --> res_users : user_id (Many2one)
    class stock_quant
    stock_quant_package --> stock_quant : quant_ids (One2many)
    class stock_package_type
    stock_quant_package --> stock_package_type : package_type_id (Many2one)
    class stock_location
    stock_quant_package --> stock_location : location_id (Many2one)
    class res_company
    stock_quant_package --> res_company : company_id (Many2one)
    class res_partner
    stock_quant_package --> res_partner : owner_id (Many2one)
    class res_company
    stock_scrap --> res_company : company_id (Many2one)
    class product_product
    stock_scrap --> product_product : product_id (Many2one)
    class uom_uom
    stock_scrap --> uom_uom : product_uom_id (Many2one)
    class stock_lot
    stock_scrap --> stock_lot : lot_id (Many2one)
    class stock_quant_package
    stock_scrap --> stock_quant_package : package_id (Many2one)
    class res_partner
    stock_scrap --> res_partner : owner_id (Many2one)
    class stock_move
    stock_scrap --> stock_move : move_id (Many2one)
    class stock_picking
    stock_scrap --> stock_picking : picking_id (Many2one)
    class stock_location
    stock_scrap --> stock_location : location_id (Many2one)
    class stock_location
    stock_scrap --> stock_location : scrap_location_id (Many2one)
    class res_company
    stock_warehouse --> res_company : company_id (Many2one)
    class res_partner
    stock_warehouse --> res_partner : partner_id (Many2one)
    class stock_location
    stock_warehouse --> stock_location : view_location_id (Many2one)
    class stock_location
    stock_warehouse --> stock_location : lot_stock_id (Many2one)
    class stock_route
    stock_warehouse --> stock_route : route_ids (Many2many)
    class stock_location
    stock_warehouse --> stock_location : wh_input_stock_loc_id (Many2one)
    class stock_location
    stock_warehouse --> stock_location : wh_qc_stock_loc_id (Many2one)
    class stock_location
    stock_warehouse --> stock_location : wh_output_stock_loc_id (Many2one)
    class stock_location
    stock_warehouse --> stock_location : wh_pack_stock_loc_id (Many2one)
    class stock_rule
    stock_warehouse --> stock_rule : mto_pull_id (Many2one)
    class stock_picking_type
    stock_warehouse --> stock_picking_type : pick_type_id (Many2one)
    class stock_picking_type
    stock_warehouse --> stock_picking_type : pack_type_id (Many2one)
    class stock_picking_type
    stock_warehouse --> stock_picking_type : out_type_id (Many2one)
    class stock_picking_type
    stock_warehouse --> stock_picking_type : in_type_id (Many2one)
    class stock_picking_type
    stock_warehouse --> stock_picking_type : int_type_id (Many2one)
    class stock_picking_type
    stock_warehouse --> stock_picking_type : return_type_id (Many2one)
    class stock_route
    stock_warehouse --> stock_route : crossdock_route_id (Many2one)
    class stock_route
    stock_warehouse --> stock_route : reception_route_id (Many2one)
    class stock_route
    stock_warehouse --> stock_route : delivery_route_id (Many2one)
    class stock_warehouse
    stock_warehouse --> stock_warehouse : resupply_wh_ids (Many2many)
    class stock_route
    stock_warehouse --> stock_route : resupply_route_ids (One2many)
    class stock_location
    res_partner --> stock_location : property_stock_customer (Many2one)
    class stock_location
    res_partner --> stock_location : property_stock_supplier (Many2one)
    class res_company
    stock_move --> res_company : company_id (Many2one)
    class product_product
    stock_move --> product_product : product_id (Many2one)
    class uom_uom
    stock_move --> uom_uom : product_uom (Many2one)
    class product_template
    stock_move --> product_template : product_tmpl_id (Many2one)
    class stock_location
    stock_move --> stock_location : location_id (Many2one)
    class stock_location
    stock_move --> stock_location : location_dest_id (Many2one)
    class res_partner
    stock_move --> res_partner : partner_id (Many2one)
    class stock_move
    stock_move --> stock_move : move_dest_ids (Many2many)
    class stock_move
    stock_move --> stock_move : move_orig_ids (Many2many)
    class stock_picking
    stock_move --> stock_picking : picking_id (Many2one)
    class stock_scrap
    stock_move --> stock_scrap : scrap_ids (One2many)
    class procurement_group
    stock_move --> procurement_group : group_id (Many2one)
    class stock_rule
    stock_move --> stock_rule : rule_id (Many2one)
    class stock_picking_type
    stock_move --> stock_picking_type : picking_type_id (Many2one)
    class stock_move_line
    stock_move --> stock_move_line : move_line_ids (One2many)
    class stock_move_line
    stock_move --> stock_move_line : move_line_nosuggest_ids (One2many)
    class stock_move
    stock_move --> stock_move : origin_returned_move_id (Many2one)
    class stock_move
    stock_move --> stock_move : returned_move_ids (One2many)
    class res_partner
    stock_move --> res_partner : restrict_partner_id (Many2one)
    class stock_route
    stock_move --> stock_route : route_ids (Many2many)
    class stock_warehouse
    stock_move --> stock_warehouse : warehouse_id (Many2one)
    class stock_package_level
    stock_move --> stock_package_level : package_level_id (Many2one)
    class stock_warehouse_orderpoint
    stock_move --> stock_warehouse_orderpoint : orderpoint_id (Many2one)
    class stock_lot
    stock_move --> stock_lot : lot_ids (Many2many)
    class product_packaging
    stock_move --> product_packaging : product_packaging_id (Many2one)
    class stock_quant
    product_product --> stock_quant : stock_quant_ids (One2many)
    class stock_move
    product_product --> stock_move : stock_move_ids (One2many)
    class stock_warehouse_orderpoint
    product_product --> stock_warehouse_orderpoint : orderpoint_ids (One2many)
    class stock_putaway_rule
    product_product --> stock_putaway_rule : putaway_rule_ids (One2many)
    class stock_storage_category_capacity
    product_product --> stock_storage_category_capacity : storage_category_capacity_ids (One2many)
    class res_users
    product_template --> res_users : responsible_id (Many2one)
    class stock_location
    product_template --> stock_location : property_stock_production (Many2one)
    class stock_location
    product_template --> stock_location : property_stock_inventory (Many2one)
    class stock_location
    product_template --> stock_location : location_id (Many2one)
    class stock_warehouse
    product_template --> stock_warehouse : warehouse_id (Many2one)
    class stock_route
    product_template --> stock_route : route_ids (Many2many)
    class stock_route
    product_category --> stock_route : route_ids (Many2many)
    class product_removal
    product_category --> product_removal : removal_strategy_id (Many2one)
    class stock_route
    product_category --> stock_route : total_route_ids (Many2many)
    class stock_putaway_rule
    product_category --> stock_putaway_rule : putaway_rule_ids (One2many)
    class stock_package_type
    product_packaging --> stock_package_type : package_type_id (Many2one)
    class stock_route
    product_packaging --> stock_route : route_ids (Many2many)
    class procurement_group
    stock_rule --> procurement_group : group_id (Many2one)
    class res_company
    stock_rule --> res_company : company_id (Many2one)
    class stock_location
    stock_rule --> stock_location : location_dest_id (Many2one)
    class stock_location
    stock_rule --> stock_location : location_src_id (Many2one)
    class stock_route
    stock_rule --> stock_route : route_id (Many2one)
    class stock_picking_type
    stock_rule --> stock_picking_type : picking_type_id (Many2one)
    class res_partner
    stock_rule --> res_partner : partner_address_id (Many2one)
    class stock_warehouse
    stock_rule --> stock_warehouse : warehouse_id (Many2one)
    class stock_warehouse
    stock_rule --> stock_warehouse : propagate_warehouse_id (Many2one)
    class res_partner
    procurement_group --> res_partner : partner_id (Many2one)
    class stock_move
    procurement_group --> stock_move : stock_move_ids (One2many)
    class stock_storage_category_capacity
    stock_storage_category --> stock_storage_category_capacity : capacity_ids (One2many)
    class stock_storage_category_capacity
    stock_storage_category --> stock_storage_category_capacity : product_capacity_ids (One2many)
    class stock_storage_category_capacity
    stock_storage_category --> stock_storage_category_capacity : package_capacity_ids (One2many)
    class stock_location
    stock_storage_category --> stock_location : location_ids (One2many)
    class res_company
    stock_storage_category --> res_company : company_id (Many2one)
    class stock_storage_category
    stock_storage_category_capacity --> stock_storage_category : storage_category_id (Many2one)
    class product_product
    stock_storage_category_capacity --> product_product : product_id (Many2one)
    class stock_package_type
    stock_storage_category_capacity --> stock_package_type : package_type_id (Many2one)
    class res_company
    stock_storage_category_capacity --> res_company : company_id (Many2one)
    class ir_sequence
    stock_picking_type --> ir_sequence : sequence_id (Many2one)
    class stock_location
    stock_picking_type --> stock_location : default_location_src_id (Many2one)
    class stock_location
    stock_picking_type --> stock_location : default_location_dest_id (Many2one)
    class stock_picking_type
    stock_picking_type --> stock_picking_type : return_picking_type_id (Many2one)
    class stock_warehouse
    stock_picking_type --> stock_warehouse : warehouse_id (Many2one)
    class res_company
    stock_picking_type --> res_company : company_id (Many2one)
    class stock_picking
    stock_picking --> stock_picking : backorder_id (Many2one)
    class stock_picking
    stock_picking --> stock_picking : backorder_ids (One2many)
    class procurement_group
    stock_picking --> procurement_group : group_id (Many2one)
    class stock_location
    stock_picking --> stock_location : location_id (Many2one)
    class stock_location
    stock_picking --> stock_location : location_dest_id (Many2one)
    class stock_move
    stock_picking --> stock_move : move_ids (One2many)
    class stock_move
    stock_picking --> stock_move : move_ids_without_package (One2many)
    class stock_picking_type
    stock_picking --> stock_picking_type : picking_type_id (Many2one)
    class res_partner
    stock_picking --> res_partner : partner_id (Many2one)
    class res_company
    stock_picking --> res_company : company_id (Many2one)
    class res_users
    stock_picking --> res_users : user_id (Many2one)
    class stock_move_line
    stock_picking --> stock_move_line : move_line_ids (One2many)
    class stock_move_line
    stock_picking --> stock_move_line : move_line_ids_without_package (One2many)
    class stock_move_line
    stock_picking --> stock_move_line : move_line_nosuggest_ids (One2many)
    class res_partner
    stock_picking --> res_partner : owner_id (Many2one)
    class product_product
    stock_picking --> product_product : product_id (Many2one)
    class stock_package_level
    stock_picking --> stock_package_level : package_level_ids (One2many)
    class stock_package_level
    stock_picking --> stock_package_level : package_level_ids_details (One2many)
    class stock_location
    res_company --> stock_location : internal_transit_location_id (Many2one)
    class mail_template
    res_company --> mail_template : stock_mail_confirmation_template_id (Many2one)
    class stock_warehouse
    stock_warehouse_orderpoint --> stock_warehouse : warehouse_id (Many2one)
    class stock_location
    stock_warehouse_orderpoint --> stock_location : location_id (Many2one)
    class product_template
    stock_warehouse_orderpoint --> product_template : product_tmpl_id (Many2one)
    class product_product
    stock_warehouse_orderpoint --> product_product : product_id (Many2one)
    class product_category
    stock_warehouse_orderpoint --> product_category : product_category_id (Many2one)
    class uom_uom
    stock_warehouse_orderpoint --> uom_uom : product_uom (Many2one)
    class procurement_group
    stock_warehouse_orderpoint --> procurement_group : group_id (Many2one)
    class res_company
    stock_warehouse_orderpoint --> res_company : company_id (Many2one)
    class stock_location
    stock_warehouse_orderpoint --> stock_location : allowed_location_ids (One2many)
    class stock_rule
    stock_warehouse_orderpoint --> stock_rule : rule_ids (Many2many)
    class stock_route
    stock_warehouse_orderpoint --> stock_route : route_id (Many2one)
    class stock_picking
    stock_move_line --> stock_picking : picking_id (Many2one)
    class stock_move
    stock_move_line --> stock_move : move_id (Many2one)
    class res_company
    stock_move_line --> res_company : company_id (Many2one)
    class product_product
    stock_move_line --> product_product : product_id (Many2one)
    class uom_uom
    stock_move_line --> uom_uom : product_uom_id (Many2one)
    class stock_quant_package
    stock_move_line --> stock_quant_package : package_id (Many2one)
    class stock_package_level
    stock_move_line --> stock_package_level : package_level_id (Many2one)
    class stock_lot
    stock_move_line --> stock_lot : lot_id (Many2one)
    class stock_quant_package
    stock_move_line --> stock_quant_package : result_package_id (Many2one)
    class res_partner
    stock_move_line --> res_partner : owner_id (Many2one)
    class stock_location
    stock_move_line --> stock_location : location_id (Many2one)
    class stock_location
    stock_move_line --> stock_location : location_dest_id (Many2one)
    class stock_picking_type
    stock_move_line --> stock_picking_type : picking_type_id (Many2one)
    class stock_move_line
    stock_move_line --> stock_move_line : consume_line_ids (Many2many)
    class stock_move_line
    stock_move_line --> stock_move_line : produce_line_ids (Many2many)
    class stock_quant_package
    stock_package_level --> stock_quant_package : package_id (Many2one)
    class stock_picking
    stock_package_level --> stock_picking : picking_id (Many2one)
    class stock_move
    stock_package_level --> stock_move : move_ids (One2many)
    class stock_move_line
    stock_package_level --> stock_move_line : move_line_ids (One2many)
    class stock_location
    stock_package_level --> stock_location : location_id (Many2one)
    class stock_location
    stock_package_level --> stock_location : location_dest_id (Many2one)
    class res_company
    stock_package_level --> res_company : company_id (Many2one)
    class stock_location
    stock_location --> stock_location : location_id (Many2one)
    class stock_location
    stock_location --> stock_location : child_ids (One2many)
    class stock_location
    stock_location --> stock_location : child_internal_location_ids (Many2many)
    class res_company
    stock_location --> res_company : company_id (Many2one)
    class product_removal
    stock_location --> product_removal : removal_strategy_id (Many2one)
    class stock_putaway_rule
    stock_location --> stock_putaway_rule : putaway_rule_ids (One2many)
    class stock_quant
    stock_location --> stock_quant : quant_ids (One2many)
    class stock_warehouse
    stock_location --> stock_warehouse : warehouse_view_ids (One2many)
    class stock_warehouse
    stock_location --> stock_warehouse : warehouse_id (Many2one)
    class stock_storage_category
    stock_location --> stock_storage_category : storage_category_id (Many2one)
    class stock_move_line
    stock_location --> stock_move_line : outgoing_move_line_ids (One2many)
    class stock_move_line
    stock_location --> stock_move_line : incoming_move_line_ids (One2many)
    class stock_rule
    stock_route --> stock_rule : rule_ids (One2many)
    class stock_warehouse
    stock_route --> stock_warehouse : supplied_wh_id (Many2one)
    class stock_warehouse
    stock_route --> stock_warehouse : supplier_wh_id (Many2one)
    class res_company
    stock_route --> res_company : company_id (Many2one)
    class product_template
    stock_route --> product_template : product_ids (Many2many)
    class product_category
    stock_route --> product_category : categ_ids (Many2many)
    class product_packaging
    stock_route --> product_packaging : packaging_ids (Many2many)
    class stock_warehouse
    stock_route --> stock_warehouse : warehouse_domain_ids (One2many)
    class stock_warehouse
    stock_route --> stock_warehouse : warehouse_ids (Many2many)
    class product_product
    stock_lot --> product_product : product_id (Many2one)
    class uom_uom
    stock_lot --> uom_uom : product_uom_id (Many2one)
    class stock_quant
    stock_lot --> stock_quant : quant_ids (One2many)
    class res_company
    stock_lot --> res_company : company_id (Many2one)
    class stock_picking
    stock_lot --> stock_picking : delivery_ids (Many2many)
    class res_partner
    stock_lot --> res_partner : last_delivery_partner_id (Many2one)
```

Notes
- Classes show model technical names; fields omitted for brevity.
- Items listed under _inherit are extensions of existing models.
