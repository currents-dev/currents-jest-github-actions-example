# Currents + Jest on GitHub Actions Example

## About

This repository demonstrates how to report test results generated by Jest to [Currents](https://currents.dev) - - a cloud platform for debugging, troubleshooting and analysing CI tests.

This example runs Jest tests in [parallel](https://jestjs.io/docs/cli#--shard) using GitHub actions matrix with 2 machines.

## How to reproduce

Follow the steps to reproduce this example:

- Create an account at https://app.currents.dev and obtain Project Id and Record Key
- Save the Record Key as [Repository Secret](https://docs.github.com/en/actions/security-guides/using-secrets-in-github-actions) `CURRENTS_RECORD_KEY`
- Add `@currents/cmd` and `@currents/jest` as a dependency
- Add `@currents/jest` as Jest reporter (see `./jest.config.js`)
- Configure GitHub actions [workflow](.github/workflows/test.yml):
  - run the tests: `npm run test`
  - upload the test results to Currents: `npx currents upload ...`

## Resources

- 📖 [Currents documentation](https://docs.currents.dev)
- [`@currents/cmd`](https://docs.currents.dev/resources/reporters/currents-cmd)
- [`@currents/jest`](https://docs.currents.dev/resources/reporters/currents-jest)
