# Introduction
fastAPI micro-service demo for LevelHome	**AI-Spaces** revolutionizes web app development by seamlessly integrating React's modern JavaScript capabilities with Redux Toolkit for robust state management and FastAPI's efficient Python backend. This innovative platform empowers users to interact with the advanced ChatGPT AI model, providing an intuitive experience where users can input questions and upload documents. AI-Spaces intelligently scans the uploaded documents for relevant information, generating precise summaries based on the user's queries. By combining the power of React and Redux for a dynamic frontend and FastAPI for a high-performance backend, AI-Spaces delivers a streamlined solution for AI-driven content analysis. Whether you're a seasoned developer or new to AI technologies, AI-Spaces offers a sophisticated yet user-friendly environment to create cutting-edge web applications.


## :ledger: Index

- [About](#beginner-about)
- [Usage](#zap-usage)
  - [Installation](#electric_plug-installation)
  - [Commands](#package-commands)
- [Development](#wrench-development)
  - [Pre-Requisites](#notebook-pre-requisites)
  - [Development Environment](#nut_and_bolt-development-environment)
  - [API-EndPoints](#file_folder-file-structure)
  - [File Structure](#file_folder-file-structure)
  - [Build](#hammer-build)  
  - [Deployment](#rocket-deployment)  
- [Community](#cherry_blossom-community)
  - [Contribution](#fire-contribution)
  - [Branches](#cactus-branches)
  - [Guideline](#exclamation-guideline)
- [FAQ](#question-faq)

##  :beginner: About
Welcome to AI-Spaces! Whether you're new to coding or a seasoned developer, this project is designed to offer a smooth introduction to modern web development. AI-Spaces leverages the power of React for a dynamic frontend, Redux Toolkit for efficient state management, and FastAPI for a powerful backend. Our primary goal is to provide a user-friendly structure for building advanced web applications with AI capabilities. Here, you'll learn how to integrate the ChatGPT AI model, allowing users to input questions and upload documents for intelligent analysis and summary generation. Join us as we explore the exciting possibilities of AI-enhanced web development with AI-Spaces, empowering you to create innovative web experiences. Let's dive into the world of React, Redux, and FastAPI together!

## :zap: Usage
This repository leverages React for a dynamic frontend, Redux Toolkit for efficient state management, and FastAPI for a robust backend. Follow the steps below to get started with AI-Spaces:
###  :electric_plug: Installation 
Clone the repository and install dependencies for all packages:

```sh
git clone <repository-url>
cd <repository-directory>
```

```sh
npx create-next-app@latest
```

###  :package: Commands
- For front-end web
```sh
cd front
npm run start
```
- For the backend Strapi
```sh
uvicorn api:app --reload
```

##  :wrench: Development
If you want other people to contribute to this project, this is the section, make sure you always add this.

### :notebook: Pre-Requisites

Ensure you have the following tools installed:

- Node.js (>= 18.x)
- npm (>= 8.x) or Yarn (>= 1.x)

Additionally, this Turborepo has some additional tools already set up for you:

- [ESLint](https://eslint.org/) for code linting
- [Prettier](https://prettier.io) for code formatting

###  :nut_and_bolt: Development Environment

Setting up the development environment for this monorepo is straightforward. Follow these steps to get your project up and running.

#### 1. Clone the Repository

First, download the project by cloning the repository to your local machine:

```sh
git clone <repository-url>
cd <repository-directory>
npm install
```
###  :file_folder: API-EndPoints
    Here is the following endpoints that are used in this project.
**Post prompt for the user (Account Setting's)**
    curl -X POST "https://documentai-bki-webapp-dev.azurewebsites.net/api/prompt/bulk" -H "Content-Type: application/json" -H "Authorization: Bearer token" -d '{"questions": [{"question_id": 0, "doc_type":1, "question":"What is the purpose of the document?"}], "system_prompt": "What is the purpose of the document?","system_prompt_two",""}'

**Delete prompt for the user**
    curl -X GET "https://documentai-bki-webapp-dev.azurewebsites.net/prompt/{question_id}" -H "Content-Type: application/json" -H "Authorization: Bearer token"

**Upload Document**
    curl -X GET "https://documentai-bki-webapp-dev.azurewebsites.net/api/upload/{request_id}" -H "Content-Type: application/json" -H "Authorization: Bearer token"

**Get summary of the uploaded files**
    curl -X GET "https://documentai-bki-webapp-dev.azurewebsites.net/api/summary?request_id=cea32526-b948-4da8-87e5-8635efaaf6dc&document_type=1&language=de" -H "Content-Type: application/json" -H "Authorization: Bearer token"

**Microsoft Authentication Entra ID**
    Website can't be able to show pages without authentication. Every API takes token auth token.

**Get prompt for the user (Account Setting's)**
curl -X GET "https://documentai-bki-webapp-dev.azurewebsites.net/api/prompt" -H "Content-Type: application/json" -H "Authorization: Bearer token".

###  :file_folder: File Structure
```
.
├── front
│   ├── public
│   │   ├── assets
│   │   │   └── images
│   │   └── index.html
│   ├── src
│   │   ├── components
│   │   │   ├── api.js
│   │   │   ├── header.js
│   │   │   ├── history.js
│   │   │   ├── home.js
│   │   │   ├── select.js
│   │   │   ├── settings.js
│   │   │   └── upload.js
│   │   ├── slice
│   │   │   ├── chats.js
│   │   │   ├── document.js
│   │   │   └── user.js
│   │   ├── App.css
│   │   ├── App.test.js
│   │   ├── index.css
│   │   ├── index.js
│   │   ├── logo.svg
│   │   ├── reportWebVitals.js
│   │   ├── setupTests.js
│   │   └── store.js
│   ├── package-lock.json
│   └── package.json
├── api.py
├── config.py
├── db.py
├── Dockerfile
├── file_handler.py
├── models.py
├── README.md
├── requirements.txt
└── search.py
```

###  :hammer: Build
- Before going to production make sure to make the production ready build with this following commond.
```sh
npm run build
```

### :rocket: Deployment
- To deploy the application, follow these steps:
- Ensure the build step is complete.
- Upload the build artifacts to your server or hosting service.
- Configure your server to serve the built files.
- Refer to the deployment documentation specific to your hosting provider for detailed instructions.


##  :cherry_blossom: Community

###  :fire: Contribution

Your contributions are always welcome and appreciated. Here are ways you can contribute:

1. **Report a bug** <br>
If you think you have encountered a bug, and I should know about it, feel free to report it [here]() and I will take care of it.

2. **Request a feature** <br>
You can also request for a feature [here](), and if it will viable, it will be picked for development.  

3. **Create a pull request** <br>
It can't get better then this, your pull request will be appreciated by the community. You can get started by picking up any open issues from [here]() and make a pull request.

> If you are new to open-source, make sure to check read more about it [here](https://www.digitalocean.com/community/tutorial_series/an-introduction-to-open-source) and learn more about creating a pull request [here](https://www.digitalocean.com/community/tutorials/how-to-create-a-pull-request-on-github).

### :cactus: Branches

I use an agile continuous integration methodology, so the version is frequently updated and development is really fast.

1. **`staging`** is the development branch.

2. **`production`** is the production branch.

3. No other permanent branches should be created in the main repository, you can create feature branches but they should get merged with the master.

**Steps to work with feature branch**

1. To start working on a new feature, create a new branch github username and prefixed with `feat` and followed by feature name. (ie. `username/feat-FEATURE-NAME`)
2. Once you are done with your changes, you can raise PR.
**Steps to work with issue branch**

1. To start working on a issue, create a new branch github username and prefixed with `issue` and followed by issue name. (ie. `username/issue#Number`)
2. Once you are done with your changes, you can raise PR.

**Steps to create a pull request**

1. Make a PR to `staging` branch.
2. Comply with the best practices and guidelines e.g. where the PR concerns visual elements it should have an image showing the effect.
3. It must pass all continuous integration checks and get positive reviews.

After this, changes will be merged.


### :exclamation: Guideline
coding guidelines or other things you want people to follow should follow.

**Consistent Naming Conventions**
   - Use meaningful and descriptive names for variables, functions, and classes.
   - Follow camelCase for variables and functions, PascalCase for classes, and SCREAMING_SNAKE_CASE for constants.

**Code Formatting**
   - Use a consistent code style for indentation, spacing, and braces. Configure your IDE to use the project's `.editorconfig` or `.prettierrc`.
   - Run a code formatter like Prettier before committing your code.

**Comments and Documentation**
   - Write clear and concise comments for complex logic and important sections of the code.
   - Use JSDoc or similar tools for documenting functions, parameters, and return values.
   - Keep the documentation up-to-date with code changes.

**Modular Code**
   - Break down large functions and classes into smaller, reusable modules.
   - Use design patterns where appropriate to improve code organization and readability.

**Error Handling**
   - Implement proper error handling using try-catch blocks or error-first callbacks.
   - Provide informative error messages and log them appropriately.

**Testing**
   - Write unit tests for all critical functions and modules using testing frameworks like Jest or Mocha.
   - Ensure that your code has good test coverage and that tests are run regularly.

**Version Control**
   - Commit code frequently with clear and descriptive commit messages.
   - Use feature branches for new features or significant changes, and merge them into `staging` or `production` through pull requests.

**Code Reviews**
   - Participate in code reviews to ensure code quality and share knowledge.
   - Be open to feedback and constructive criticism to improve the codebase.

**Prototyping**
   - Create prototypes for complex features before full implementation to validate ideas and approaches.
   - Use tools like Figma for UI/UX prototyping and flow diagrams.

**Code Refactoring**
   - Regularly refactor code to improve readability, reduce complexity, and eliminate technical debt.
   - Follow the "Boy Scout Rule": Always leave the code better than you found it.

**Performance Optimization**
   - Profile and optimize critical code paths to enhance performance.
   - Use efficient algorithms and data structures to reduce computational overhead.

**Single Responsibility Principle**
   - Ensure that each function or class has a single responsibility and adheres to the SRP.

**DRY (Don't Repeat Yourself)**
   - Avoid code duplication by creating reusable functions, modules, and components.

**KISS (Keep It Simple, Stupid)**
   - Write simple and straightforward code. Avoid unnecessary complexity.

**YAGNI (You Aren't Gonna Need It)**
   - Do not add functionality until it is necessary. Focus on the current requirements.

### Additional Resources

- [Clean Code by Robert C. Martin](https://www.goodreads.com/book/show/3735293-clean-code)
- [Design Patterns: Elements of Reusable Object-Oriented Software](https://www.goodreads.com/book/show/85009.Design_Patterns)
- [You Don't Know JS (book series)](https://github.com/getify/You-Dont-Know-JS)

   By following these guidelines and best practices, we can maintain a high-quality codebase that is easy to understand, maintain, and extend.


## :question: FAQ

**What is React JS?**
   React JS is a popular JavaScript library for building user interfaces, particularly for single-page applications where you can create reusable UI components. It allows developers to build web applications that can update and render efficiently in response to data changes.

**What is FastAPI?**
   FastAPI is a modern, fast (high-performance), web framework for building APIs with Python 3.6+ based on standard Python-type hints. It is designed to be easy to use and to provide fast development of robust APIs, taking advantage of automatic interactive API documentation.

**How do I run the backend and frontend applications simultaneously?**
   To run both the backend and frontend applications, you can use these commands to start all services concurrently:
**For Backend**
   ```sh
   uvicorn api:app --reload
   ```
**For Front End**
   ```sh
   cd front
   npm start
   ```
   By running these commands in separate terminal windows, you can develop and test the frontend and backend simultaneously.