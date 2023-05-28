# Swyger Client JS

## Get Started
Swyger Client is used for Swyger Server as consumer Rest API.
Visit the master branch: https://github.com/coorise/swyger-js-client.git

Download  the library from ``dist/``
then create a config variable for your remote/local server
```
<script type="module">
        let config={
            //Configure the offline DB
            OFFLINE_DB_NAME:'swyger_database',

            //Configure the server
            HOST_SERVER:{
                AUTH:'http://localhost:4100',
                DATABASE:'http://localhost:4400',
                STORAGE:'http://localhost:4500',
                MAIL:'http://localhost:4200',
            },
            API_VERSION:{
                AUTH:'/api/v1',
                DATABASE:'/api/v1',
                STORAGE:'/api/v1',
                MAIL:'/api/v1',
            },
            AUTO_REFRESH_TOKEN_TIMEOUT:1500000, //in millisecond= 25 minutes
            // A Unique Api key for all your servers
            API_KEY:your_api_key
        }

 </script>
```
then import SwygerClient library
```
<script type="module">
        import SwygerClient from './src/index.js'
        
        let client =SwygerClient.init(config)
        //now you can do authentication
        let auth= client.auth
        auth.register({email,password},callback)
        ...
        
        //or crud for database
        let database=client.database.ref('/my_path_reference') //like firebase database realtime
        database.create({object},callback)
        ...
        
        //also for storage
        let storage=client.storage.ref('/my_path_reference')
        database.upload({object},callback)

 </script>
```
Note 1: For more details about to use our API Consumer, visit the ``DOC`` : https://github.com/coorise/swyger-js-client/tree/master/doc/swyger/api.

Note 2: If you want to modify the entire api (eg:children route,...), you have to work with the main project (installing Node JS with the project dependencies ``npm i``) then locate the ``./src/api/api-route.js``,
once you are done just build it with ``npm run build``, to get your new library in dist folder.

# Todo
- Removing/Reduce some unusual dependencies,functions, refactoring paths/files...
- Making good and easy documentation with tutorials (videos, webpage...)
- Code Cleaning/ Making a suitable project structure with modulable pattern

# Join US
If you have any suggestion, feature to add ...etc
- Discord(Support Team, FAQ, Chat): https://discord.gg/PPTZY5qFdC

# Contributors
- Agglomy Team :
    - Ivan Joel Sobgui
# Licence

MIT: You can use it for educational/personal/business purpose!