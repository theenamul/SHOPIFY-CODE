# SHOPIFY-CODE
--------------
--------------


1. SHOPIFY PRODUCT PAGE > QUANTITY SELECTOR < DESIGN CODE:
------------------------------------------------------

[NOTE : Search {% if section.settings.show_quantity_selector %}  under this line put HTML CODE]
# HTML CODE START (put product 'custom template page'):

<div class="qtydiv">
  <label for="Quantity" class="quantity-selector">Quantity</label>
  <div class="qtybox">
    <span class="btnqty qtyminus icon icon-minus">-</span>
    <input type="text" id="quantity" name="quantity" value="1" min="1" class="quantity-selector quantity-input" readonly="">
    <span class="btnqty qtyplus icon icon-plus">+</span>
  </div>
</div>

# HTML CODE END
------------
------------

# CSS CODE START( Put Asset > Theme.css Page):

.qtydiv label{display: block;margin-bottom: 12px;letter-spacing: 2.8px;color: #747a7b;}
.qtybox{border: 1px solid #ccc;padding: 0 7px;margin-bottom: 8px;}
.qtydiv .btnqty{display: inline-block;cursor: pointer;user-select: none;font-size: 25px;padding: 5px;line-height: 5px;}
.qtydiv .btnqty.qtyminus{margin-right: 8px;}
.qtydiv .btnqty.qtyplus{margin-left: 8px;}
.qtydiv .quantity-input{border: none;border: none;padding: 8px;text-align: center;width: 50px;outline: none;display: inline-block;}
.qtydiv {display: inline-block;padding-right: 15px;padding-top: 10px;}

# CSS CODE END
---------------
---------------

# JS CODE START:

$('.qtybox .btnqty').on('click', function(){
  var qty = parseInt($(this).parent('.qtybox').find('.quantity-input').val());
  if($(this).hasClass('qtyplus')) {
    qty++;
  }else {
    if(qty > 1) {
      qty--;
    }
  }
  qty = (isNaN(qty))?1:qty;
  $(this).parent('.qtybox').find('.quantity-input').val(qty);
}); 


# JS CODE END








































