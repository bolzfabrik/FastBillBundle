FastBillBundle
==============

Symfony 2 Bundle that registers the [DVelopment/FastBill](https://github.com/dVelopment/fastbill) library as a service.

## Installation

Install the bundle using composer (see [http://getcomposer.org/](http://getcomposer.org/) for more information about composer)

    composer require dvelopment/fastbill-bundle dev-master
    
or add the package directly to your `composer.json` file and run `composer update`.

Then just add the bundle to your `AppKernel.php` file:

    // in AppKernel::registerBundles()
    $bundles = array(
        // ...
        new DVelopment\FastBillBundle\DVelopmentFastBillBundle(),
        // ...
    );

## Configuration

You need to configure your FastBill API credentials in `config.yml` (you can find the API Key inside the Settings area of your account settings on [my.fastbill.com](https://my.fastbill.com))

    d_velopment_fast_bill:
    	# the username is your e-mail address
    	# used to sign up to FastBill
        username: %fast_bill_username% 
        apiKey:   %fast_bill_api_key%
        
        
## Usage

The API wrapper is available as `d_velopment_fast_bill.api` service:

    $api = $container->get('d_velopment_fast_bill.api');
    $customers = $api->getCustomers();