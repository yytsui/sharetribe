1. Install the specific version of Ruby on Rails:
   % rbenv install 2.3.4
   % rbenv local 2.3.4
   % RBENV_VERSION=2.3.4 rbenv exec gem install rails --version 5.1.1

2. Install nvm, then install specific versions of node and npm:
   %  curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
   %  nvm install 7.8
   and there is .nvmrc in local dev directory
   % node -v 
   % npm -v    # make sure node and npm are the right version before run 'npm install'

3. To fix the Payment settings does not appear issue:
   % bin/rails console -e development
   Loading development environment (Rails 5.1.1)
   irb(main):001:0> TransactionService::API::Api.processes.create(community_id: 1, process: :preauthorize, author_is_seller: true)
   irb(main):002:0> TransactionService::API::Api.settings.provision(community_id: 1, payment_gateway: :stripe, payment_process: :preauthorize, active: true)
 
4. In dev environment, make sure rails dev server start at port 3000:
   % PORT=3000 foreman start -f Procfile.static
   

5. [What is lvh.me?](https://www.quora.com/What-is-lvh-me)
   The domain http://lvh.me is really useful for testing web apps locally. It resolves itself and all its subdomains 
   to 127.0.0.1. So you can easily test virtual subdomains as xxx.lvh.me without setting up your own DNS 
   or touching /etc/hosts.
   
   From Google search Use lvh.me for local subdomain testing (Example)
    