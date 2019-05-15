# PLM-ALM-with-GitLab
Creates a simple PLM-ALM integration using GitLab as ALM. The goal is to provide an integration which will allow the project managers to capture a specific tag/release/version in a product structure, controlled with the CMII change management process. It leaves the developper the possibility to mainly work with GitLab which could be their preferred data management environment.
#### How it works
With this project, Aras has a few federated object which are querying Gitlab through its REST webservice interface.

## History

Project | Aras
--------|------
[v2.0.0](https://github.com/ArasLabs/PLM-ALM-with-Gitlab/releases/tag/v2.0.0) | Updated for HTTPS usage and typeahead logic. Tested on Internet Explorer, Edge, Firefox 60 ESR, Chrome
[v1.0.0](https://github.com/ArasLabs/PLM-ALM-with-Gitlab/releases/tag/v1.0.0) | First Release. Tested on Firefox ESR 38, Chrome

### Supported Aras Versions

Project | Aras
--------|------
[v2.0.0](https://github.com/ArasLabs/PLM-ALM-with-Gitlab/releases/tag/v2.0.0) | 11.0 SP12+, 11.0 SP15
[v1.0.0](https://github.com/ArasLabs/PLM-ALM-with-Gitlab/releases/tag/v1.0.0) | 11.0 SP9


## Installation

#### Important!
**Always back up your code tree and database before applying an import package or code tree patch!**

### Pre-requisites

1. Aras Innovator installed (version 11.0 SPx preferred)
2. Aras Package Import tool

### Install Steps

1. Backup your database and store the BAK file in a safe place.
2. Open up the Aras Package Import tool.
3. Enter your login credentials and click **Login**
  * _Note: You must login as root for the package import to succeed!_
4. Enter the package name in the TargetRelease field.
  * Optional: Enter a description in the Description field.
5. Enter the path to your local `..\PLM-ALM-with-GitLab\Import\imports.mf` file in the Manifest File field.
6. Select **aras.labs.gitlab** in the Available for Import field.
7. Select Type = **Merge** and Mode = **Thorough Mode**.
8. Click **Import** in the top left corner.
9. Close the Aras Package Import tool.
10. Copy `..\PLM-ALM-with-GitLab\Innovator` in your install folder. **WARNING** The method-config.xml file has been modified. If you have made some changes yourself make sure to do a merge (using tools like winmerge for example)
  * _Note: by default c:/Program Files/Aras/Innovator/
11. Edit the following variables with connection information for you GitLab platform.
   1. **SFT_gitlabToken** 

* you will find this information in your gitlab instance
  * to create an access token, navigate to Profile >> Settings >> Access Tokens
  * Name your token, set the expiration date (as needed), check off all scopes, press the create token button
  * Copy your token somewhere safe (if you leave or refresh the page you cannot retrieve it!) and/or copy the token into the variable listed and save 

   2. **SFT_gitLabUrl**

* this is your gitlab instance URL
  * if you do not have a specific gitlab instance, use the base https://gitlab.com/ that is the default.
You are now ready to login to Aras and try out PLM-ALM-with-GitLab

## Usage

1. Log in to Aras as admin.

2. Navigate to **Administration/Respositories** in the table of contents (TOC).

3. Click the **create new** button
  * Ignore the error that pops up concerning an Object variable. you will set it in the next step

4. Enter your Project ID in the Getlabid field, save the record  

5. Save and close the record

6. List the repositories by searching the grid

   ​

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

For more information on contributing to this project, another Aras Labs project, or any Aras Community project, shoot us an email at araslabs@aras.com.

## Credits

Original Aras community project written by Yoann Maingon at Aras Corp.

Documented and published by Yoann Maingon at Aras Labs. @YoannArasLab

## License

Aras Labs projects are published to Github under the MIT license. See the [LICENSE file](./LICENSE.md) for license rights and limitations.