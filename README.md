# css-mashlib
CSS with mashlib recipe and NSS like templates/pod.

This is a `http://localhost:3000` server for mashlib test purpose. The repo is integrated with the [mashlib](https://github.com/SolidOS) stack build.

### config
- package.json contains 2 dependencies :
  - CSS version.
 
    **Each major version is linked to a different /config/**
  - mashlib version.
    
- config files are located in `config` folder
  - `http-mashlib-suffix-file.json` has been created with mashlib-recipe configuration generator https://communitysolidserver.github.io/configuration-generator/v7/ [CSS mashlib recipe](https://github.com/communitySolidServer/recipe/mashlib).
    	    
    - **The file must be replaced for each new CSS mashlib recipe version - at least for the context version**

  - `..//css-mashlib/templates/pod` replaces default CSS `@css:/templates/pod`
    
    see https://github.com/CommunitySolidServer/CommunitySolidServer/issues/1510

- `css-mashlib/templates/pod` is structured to produce default CSS pod that is fully compatible with NSS pods.
  - WebID document : card$.ttl
  - pod structure
    - inbox
    - profile
    - public
    - settings

### start CSS
- Data is stored in the `css-mashlib/data` folder
- To start CSS. There are 2 possibilities :
  - `npm run start` (keep existing data - if any)
  - `npm run start:clean` (reset CSS)

### Other available configuration
- https configuation are available to be used on real server (not localhost)
  - `https-mashlib-suffix-file.json`
  - `https-mashlib-subdomain-file.json`

  The command line to run these server can be :
  `npx community-solid-server -c ./config/https-mashlib-suffix-file.json -f ./data --httpsKey ../privkey.pem --httpsCert ../fullchain.pem -b https://yourserver:3000`

    - replace certificates by real one
    - replace ./data by real storage
    - replace `https://yourserver:3000` by the real one (example https://solidcommunity.net:3000)
