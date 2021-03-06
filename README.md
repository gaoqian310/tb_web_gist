# tb-web-gist

# Docker
Download and install Docker. Once installed, run it:
<br>**docker compose build**

Once Docker is running:
<br>**docker compose up -d**
-d will discount terminal/command propomt with docker, you can run docker up command without -d.

This will take some time the first time it runs. It builds the custom PHP image, as well as downloads the other ones needed for this to work (MariaDB/Redis/Mailcatcher).

You can take down the container with following command:
<br>**docker compose down**

# PHP artisan
1. Open CLI from docker to bring up the terminal;
2. Type **cd ..** and enter;
3. Type **pwd** and enter. You should see /var/www;
4. Type **php artisan** and enter;
5. Type **php artisan migrate:fresh** and enter;
6. Go to your web browser and type 127.0.0.1  -  you should see "Prototype Test Project"
7. Go to http://127.0.0.1/nova  - you should see login page

- $ php artisan migrate:fresh --seed

- $ php artisan make:migration create_locations_table

/vendor
- $ php artisan make:model Commerce\ \Vendor -mf
- $ php artisan make:model Marketing\ \****
- modelVendor

- $ php artisan tinker
- vendor()

- $ php artisan nova:rsource Commerce\ \Vendor --model=Commerce\ \Vendor
responsialbe to create fields
ID::make(_%_('ID'), 'id')->sortable(),
**delete % from the line above**
Text::make('Name'),
Text::make('Mailing Address'),

php artisan migrate:fresh --seed

php artisan make:migration add_json_option_to_user


/scr  
**php artisan make:model Commerce\ \Vendor -mf**  
-mf is table migration and create factory 
php artisan make:model Marketing\ \Frontpage

**php artisan nova:resource Commerce\ \Vendor --model=Commerce\ \Vendor**  

namespace App\Nova\Commerce

**(add)**  
use Laravel\Nova\Http\Requests\NovaRequest;  

use App\Nova\Resource;  

use Laravel\Nova\Fields\Text;  

use Laravel\Nova\Fields\Select;  





ID::make(__('ID'), 'id')->sortable(),
Text::make('Location Name'),

Select::make('Type')->options([
                    'business' => "Business",
                    'warehouse' => "Warehouse",
                    'booth' => "Booth",
                    'residential' => "Residential"
                    ]),

php artisan tinker

Vendor::find(0)

exit
quit()
cl


## User nova filed connection with Customer (one to one) and Role (many ot many)

### nova/user
						HasOne::make(__('Customer Profile'), 'customer', Customer::class),

						BelongsToMany::make(__('Roles'), 'roles', Role::class),  
            
### nova/customer
            Select::make('Gender:')->options([
						  BelongsTo::make(__('User'), 'user', User::class),  
              
### nova/role
public function fields(Request $request)
    {
        return [
            ID::make(_ _('ID'), 'id')->sortable(),
						Text::make(_ _('Name')),
						BelongsToMany::make(_ _('User'), 'users', User::class),
        ];
    }

### Models/User
		public function customer()
		{
			return $this->hasOne(Customer::class);
		}

		public function roles()
		{
			return $this->belongsToMany(Role::class);
		}

### Models/Roles
{
    use HasFactory;

		public function users()
		{
			return $this->belongsToMany(User::class);
		}
}

### Models/Customer
    {
        return $this->hasMany(Reviews::class);
    }

		public function user()
		{
			return $this->belongsTo(User::class);
		}
}

# After build the models and Nova Resource, will build API  
API resource: https://laravel.com/docs/9.x/eloquent-resources  


# Git
set up upstream
- $ git pull --set-upstream origin main  
leave commit comment  
- $ git commit --am "message"  
**git commit -a automatically stage all tracked, modified files before the commit** If you think the git add stage of the workflow is too cumbersome, Git allows you to skip that part with the -a option. This basically tells Git to run git add on any file that is "tracked" - that is, any file that was in your last commit and has been modified. This allows you to do a more Subversion style workflow if you want, simply editing files and then running git commit -a when you want to snapshot everything that has been changed. You still need to run git add to start tracking new files, though, just like Subversion.  
Using the option -am allows you to add and create a message for the commit in one command.

- $ git branch feature/kim_migration
- $ git checkout feature/kim_migration
- $ git add .
- $ git commit -am "messege"
- $ git checkout main
- $ git merge feature/kim_migration
- $ git pull
- $ git commit -am "messege"
- $ git push


# CLI
- $ cd .. Navigate to parent directory
- $ ls List directory contents
- $ ls -la List detailed directory contents, including hidden files
- $ mkdir directory Create new directory named directory
- $ clear clear the command line window
- $ rm file delete file
- $ rm -r directory delete directory
- $ rm -f file force-delete file
- $ mv file-old file-new Rename file-old to file-new
- $ mv file directory Move file to directory
- $ cp file directory Copy file to directory
- $ cp -r directory1 directory2 Copy directory1 and its contents to directory2

- $ bash
- $ zsh

# VS Code
- Text::make('Vendor Name', 'vendors_name')
- $ table->string('booth_plan')->nullable()
