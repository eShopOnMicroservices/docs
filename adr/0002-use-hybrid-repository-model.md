# 2. Use hybrid-repository model

Date: 2024-05-30

Status: Accepted

## Context

MVP architecture of the project involves the following domain parts:

- Backend system
- Single Page Web Application

In the long term, the architecture may includes these parts as well:

- iOS Mobile Application
- Android Mobile Application

## Decision

Monorepo per frontend platform with standalone `api`, `docs`, `backend` and
`testing` reposotories.

::: mermaid

graph TD;
web-->api;
backend-->api;
android-->api;
ios-->api;
docs-->api;
testing-->web
testing-->backend
testing-->android
testing-->ios

:::

## Rationale

1. **Convenient versioning**: No overhead for versioning backend inter service
   communication api. On the other hand, versioning of the external api is done
   explicitly as it lives in a separate repository.

2. **Constant number of repositories**: The number of repositories is
   independent of the number of services, so we won't encounter polyrepo-model
   problems that would require additional tooling.

## Implications

_TBD_.
