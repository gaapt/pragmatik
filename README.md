#pragmatik
*Building blocks for agile, manageable and deployable apps*

###Main used gems:
*Devise
*Cancan
*Rolify
*rails_admin

### Basic tutorial:

1)Install Ruby on Rails environment

2)In your terminal, use `git clone https://github.com/gaapt/pragmatik.git YOURAPPNAME`

3)Go to the app's directory with `cd YOURAPPNAME`

4)At **config/database.yml** change it with your information

5) At **config/initializers/devise.rb** uncomment **config.secret_key= ** and change it with your own secret_key

6) In your terminal, use `rake db:create`(creates a database) and then `rake db:migrate`(migrates it)

7) `rails s` to start your server

### Consideration:
* Pragmatik has a built-in admin system [http://localhost:3000/admin], but not setup with authorizations, so any user can access it. To change this:
     * Create an user
     * Go to [http://localhost:3000/admin/role/new] and create a role named 'admin' and then select your user.
     * In **models/ability.rb** add:
             ```ruby
        if user.has_role? :admin
          can :manage, :all
        else
          can :read, :all
        end
        ```
        
    
        
