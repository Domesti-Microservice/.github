# ✨Domesti ✨ - A complete home affair platform
 
Creating a personal finance project can be a valuable learning experience and can also help you better manage your finances. Here's a step-by-step guide to help you plan and develop your personal finance project:

**Step 1: Define Your Project Goals and Objectives**
Before you start, you need to clarify your goals and objectives for this project. What do you want to achieve with this personal finance project? Common objectives might include:

- **Budgeting**: Creating and sticking to a budget.
- **Tracking Expenses**: Monitoring your spending habits.
- **Savings Goals**: Saving for specific goals like a vacation, emergency fund, or retirement.
- **Debt Reduction**: Paying off debts more efficiently.
- **Investing**: Learning about and managing investments.
- **Financial Education**: Gaining a better understanding of personal finance concepts.

**Step 2: Choose the Development Platform**
Decide whether you want to develop a physical or digital personal finance tool. Digital tools are more flexible and convenient. Here are some options:

- **Spreadsheets**: Use Excel or Google Sheets to create custom budget templates.
- **Mobile Apps**: Develop a mobile app for iOS and Android.
- **Web App**: Create a web-based tool accessible from any device.
- **Pen and Paper**: If you prefer analog methods, you can use a physical notebook.

**Step 3: Plan Your Features and Functionality**
Based on your objectives, list the features your personal finance tool will need. Common features include:

- Expense tracking
- Budget creation and management
- Debt tracking and payoff calculators
- Savings goal trackers
- Investment portfolio management
- Reports and analytics
- Reminders and notifications
- User authentication and security

**Step 4: Design the User Interface (UI)**
Design a user-friendly interface that is easy to navigate. Use wireframes or mockups to plan the layout and appearance of your application. Tools like Figma, Adobe XD, or even simple pen and paper can be helpful for this step.

**Step 5: Development**
Depending on your chosen platform, you'll need to develop the application. Here's a simplified breakdown:

- **Spreadsheets**: Create your budget templates and formulas.
- **Mobile/Web Apps**: If you have coding skills, you can use languages like Python (Django/Flask), JavaScript (React, Angular, or Vue.js), or even low-code/no-code platforms like Bubble or Adalo.
- **Security**: Ensure your application is secure, especially if it involves sensitive financial data. Implement user authentication and data encryption.

**Step 6: Data Integration**
If you want to automate expense tracking, consider integrating with bank APIs or popular expense tracking apps like Mint or YNAB. This can save you time and improve accuracy.

**Step 7: Testing**
Thoroughly test your application to identify and fix bugs. Invite friends or family to test it as well to get feedback on usability and functionality.

**Step 8: Launch and Promotion**
Once you're satisfied with your personal finance tool, launch it. Create a marketing plan to promote it, such as creating a website, social media accounts, and possibly even paid advertising.

**Step 9: Maintenance and Updates**
Regularly update your application to fix bugs, improve security, and add new features based on user feedback and changing financial needs.

**Step 10: Educate Yourself**
Continuously educate yourself about personal finance to stay up-to-date with best practices and to improve your tool over time.

Remember that this is a significant project, and it may take time to develop a comprehensive personal finance tool. Start with the core features and gradually add more functionalities as you become more proficient. Additionally, consider the privacy and security of user data, especially if you plan to make your tool publicly available.


### Frontend Application
- [Core UI](https://github.com/Domesti-Microservice/core-ui) - UI Repo

### Sidecar Services
- [Reference Data Micro Service](https://github.com/Domesti-Microservice/user-svc) - Hold meta data objects for sharing accross services
- [User Service](https://github.com/Domesti-Microservice/scripts-svc ) - User Microservices Repo
- [User Service](https://github.com/Domesti-Microservice/user-svc) - User Microservices Repo
- [Workflow](https://github.com/Domesti-Microservice/ph-workflow) - User Microservices Repo
- [Kong API Gateway](https://github.com/Domesti-Microservice/kong-api-gateway ) - User Microservices Repo
- [Data Migration](https://github.com/Domesti-Microservice/data-migration) - User Microservices Repo

### Feature Microservices
- [Finance Service](https://github.com/Domesti-Microservice/finance-svc) - Finance Microservices Repo
- [User Service](https://github.com/Domesti-Microservice/user-svc) - User Microservices Repo
- [Profile Service](https://github.com/Domesti-Microservice/profile-svc) - Profile Microservices Repo
- [Contact Service](https://github.com/Domesti-Microservice/contact-svc) - Contact Microservices Repo
- [Asset Manager Service](https://github.com/Domesti-Microservice/asset-manager-svc) - Asset Microservices Repo
- [Organizer Service](https://github.com/Domesti-Microservice/organizer-svc) - Organizer Microservices Repo
- [Messaging Service](https://github.com/Domesti-Microservice/messaging-svc) - Messaging Microservices Repo


And of course Dillinger itself is open source with a [public repository][dill]
 on GitHub.

## Installation

Dillinger requires [Node.js](https://nodejs.org/) v10+ to run.

Install the dependencies and devDependencies and start the server.

```sh
cd dillinger
npm i
node app
```

For production environments...

```sh
npm install --production
NODE_ENV=production node app
```

## Plugins

Dillinger is currently extended with the following plugins.
Instructions on how to use them in your own application are linked below.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Development

Want to contribute? Great!

Dillinger uses Gulp + Webpack for fast developing.
Make a change in your file and instantaneously see your updates!

Open your favorite Terminal and run these commands.

First Tab:

```sh
node app
```

Second Tab:

```sh
gulp watch
```

(optional) Third:

```sh
karma test
```

#### Building for source

For production release:

```sh
gulp build --prod
```

Generating pre-built zip archives for distribution:

```sh
gulp build dist --prod
```

## Docker

Dillinger is very easy to install and deploy in a Docker container.

By default, the Docker will expose port 8080, so change this within the
Dockerfile if necessary. When ready, simply use the Dockerfile to
build the image.

```sh
cd dillinger
docker build -t <youruser>/dillinger:${package.json.version} .
```

This will create the dillinger image and pull in the necessary dependencies.
Be sure to swap out `${package.json.version}` with the actual
version of Dillinger.

Once done, run the Docker image and map the port to whatever you wish on
your host. In this example, we simply map port 8000 of the host to
port 8080 of the Docker (or whatever port was exposed in the Dockerfile):

```sh
docker run -d -p 8000:8080 --restart=always --cap-add=SYS_ADMIN --name=dillinger <youruser>/dillinger:${package.json.version}
```

> Note: `--capt-add=SYS-ADMIN` is required for PDF rendering.

Verify the deployment by navigating to your server address in
your preferred browser.

```sh
127.0.0.1:8000
```

## License

MIT

**Free Software, Hell Yeah!**

[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

   [dill]: <https://github.com/joemccann/dillinger>
   [git-repo-url]: <https://github.com/joemccann/dillinger.git>
   [john gruber]: <http://daringfireball.net>
   [df1]: <http://daringfireball.net/projects/markdown/>
   [markdown-it]: <https://github.com/markdown-it/markdown-it>
   [Ace Editor]: <http://ace.ajax.org>
   [node.js]: <http://nodejs.org>
   [Twitter Bootstrap]: <http://twitter.github.com/bootstrap/>
   [jQuery]: <http://jquery.com>
   [@tjholowaychuk]: <http://twitter.com/tjholowaychuk>
   [express]: <http://expressjs.com>
   [AngularJS]: <http://angularjs.org>
   [Gulp]: <http://gulpjs.com>

   [PlDb]: <https://github.com/joemccann/dillinger/tree/master/plugins/dropbox/README.md>
   [PlGh]: <https://github.com/joemccann/dillinger/tree/master/plugins/github/README.md>
   [PlGd]: <https://github.com/joemccann/dillinger/tree/master/plugins/googledrive/README.md>
   [PlOd]: <https://github.com/joemccann/dillinger/tree/master/plugins/onedrive/README.md>
   [PlMe]: <https://github.com/joemccann/dillinger/tree/master/plugins/medium/README.md>
   [PlGa]: <https://github.com/RahulHP/dillinger/blob/master/plugins/googleanalytics/README.md>
