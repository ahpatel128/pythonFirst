# Create and setup in local machine.
### To setup and develop this project in local-machine:

<ol>
  <li>
    Front-end installation:
  <ul>
  <li>
  NVM: Node Version Manager
  <a href="https://github.com/nvm-sh/nvm#installation-and-update"> Installation and update NVM </a>
  </li>
  <li>
  Node version 8:
  use following code to install version 8 in nvm:
  <b> nvm install 8</b>
  </li>
  <li>
  Angular version 6.0.8
  use following code:
  <b>
  nvm use 8
  npm install -g @angular/cli@6.0.8
  </b>
  </li>
  <li>
  Make storage folder:
  use following command:
  <b>
  mkdir storage/framework storage/framework/cache storage/framework/views storage/framework/sessions storage/fonts storage/logs
  </b>
  </li>
    <li>
      Make file in src/environment/envirnment.ts add following code in  that file:
      <blockquote>
        export const environment = {
        production: true,
     API_URL: 'https://mydd-api.deakindigital.com/api/v1',
  BASE_URL: 'https://mydd-api.deakindigital.com',
    S3_URL: 'https://s3-ap-southeast-2.amazonaws.com/',
    GREENID_CONFIG_JS_URL:'https://simpleui-test-au.vixverify.com/df/javascripts/greenidConfig.js',
  GREENID_CSS_URL:'https://simpleui-test-au.vixverify.com/df/assets/stylesheets/greenid.css',
  GREENID_UI_JS_URL:'https://simpleui-test-au.vixverify.com/df/javascripts/greenidui.min.js',
  GREENID_ACCOUNT_ID:'deakinco',
  GREENID_API_CODE:'MCc-Hfs-hBH-rLw',
  GREENID_ENVIRONMENT: 'test',
  GOOGLE_SITE_KEY: '6Lcis4IUAAAAAJDpQck3hjme-JdpyEGTKLmqAUrL',
  TITLE: 'My micro-credentials',
  PPC: false,
  SSO_LINK: '',
  PPC_URL: '',
  HOTJAR_TRACKING_ID : '1284853'
  };
      </blockquote>
    </li>
    <li>
      Run Following command to create link and add ppc components:
      <b>
        ln -sfn mmc-components angular-components
      </b>
      <br>
      <b>
       ln -sfn ppc-components angular-components 
      </b>
      <br>
      <b>
        ng build --output-path="./build-$TIMESTAMP" --build-optimizer --aot --vendor-chunk=false --source-map=false --named-chunks=false --optimization --output-hashing=all
      </b>
    </li>
    <li>
      Run the project.
      use following code:
      <br>
      <b>ng serve</b>
    </li>
  </ul>
  </li>
  <li>
    Back-End/cp-API installation:
    <ol>
      <li>
        Run composer install
      </li>
      <li>
        setup .env file, add database details, sendgrid API details (copy all the items from .env.example)
        </li>
      <li>
        php artisan key:generate
        </li>
      <li>
        php artisan storage:link  (create a symlink for storage)
</li>
      <li>
        This command is to setup basic data  
        Run php artisan migrate:refresh --seed
</li>
      <li>
 php artisan setup:sendgrid
        </li>
      <li>
 copy sendgrid templates info to .env file.
</li>
      <li>
php artisan cache:clear
        </li>
      <li>
 php artisan view:clear
        </li>
      <li>
 php artisan config:clear
        </li>
      <li>
 php artisan route:clear
      </li>
            <li>
              Run using:<br>
 php artisan serve
      </li>
      </li>
    </ul>
  </li>
 </ol>
