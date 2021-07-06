# DHIS2 webapps development - MSF training - Session 4

-   We are going to practice unit testing using Jest.
-   We are going to practice UI testing using Cypress

## Requirements

### Prepare your working branch
According to branch to make the exercise

#### From your own session 3 solution
 - If you will make the exercise in own branch from your solution in session 3
 - You will must make changes to prepare branch as in this [commit](https://github.com/EyeSeeTea/MSF-training-DHIS2-webapps-development/commit/b97aea22dd00777f87c5acde9ab43bcfd13a8a73)
- remember execute `yarn install` because we have added the cypress testing library dependency
#### From session 4 branch
 - Checkout the session_4 branch
 - if you fork repository has not the session_4 branch then [add this repository as upstream](https://docs.github.com/en/github/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork) and checkout the session_4 branch

### Repository secret
- If you are working in a fork, then to add a new repository secret with auth credentials for Cypress tests
- secret name: CYPRESS_DHIS2_AUTH
- secret value: username:password


https://user-images.githubusercontent.com/5593590/124573810-2aaf2680-de4a-11eb-8b19-3db6318c5a7a.mp4


## Tasks 

### unit test
Create a new User.spec.ts file in the src/domain/entities/__tests__/ path
- Create an unit test to validate prop isAdmin given a user data with ALL authority
- Create an unit test to validate prop isAdmin given a user data without ALL authority

### UI tests
The tests to create will be added in the training-page.spec.js file under cypress/integrations/training-page.spec.js file.
- Create a test to validate when to click on a strikethrough org unit then in the detail panel should appear the text 'The selected organisation unit is disabled'
- Create a Cypress tests to validate edit action in a level 4 org unit

## Considerations
- Try use Cypress Testing Library commands
- Modify if you need the form elements to convert it to accesible

https://material-ui.com/es/components/text-fields/#accessibility

## Browser

Avoid use chrome to avoid security bugs

- in the cypress ui select other browser
- in console use `yarn cy:e2e:run --browser firefox`

## Execute unit tests

```
yarn test
```

## Execute cypress tests

```
export CYPRESS_DHIS2_AUTH=user:password
export CYPRESS_EXTERNAL_API=http://ec2-54-195-131-72.eu-west-1.compute.amazonaws.com
export CYPRESS_ROOT_URL=http://localhost:8081

yarn cy:e2e:run --browser firefox
```

