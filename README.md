# Rbkmoney

TODO: Write a gem description

## Installation

Add this line to your application's Gemfile:

    gem 'rbkmoney'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install rbkmoney

## Usage

1. Add config file - rbkmoney.yml at config directory.
  
2. Creating form:  
   `<%= rbkmoney_form_tag(RBKMoney::purchase_uri, id: "rbk_form") do %>`  
   ` <%= rbkmoney_setup(@rbk_params) %>` #hidden items  
   ` <%= email_field_tag("email")%>` #extra item if require  
   ` <%= text_field_tag("name")%>`  
   `<% end %>`   

  in controller setup params for form,  
    for example:
    
      @order = Order.new( summa: total_summa)
      @order.save

      @rbk_params = { amount: total_summa, success_url: cart_order_url, 
          fail_url: root_url, order_id: @order.id}
    

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
