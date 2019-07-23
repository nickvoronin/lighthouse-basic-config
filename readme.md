

## What this example does

This example shows how to write a custom Lighthouse audit

## The Audit, Gatherer, and Config

- [searchable-gatherer.js](searchable-gatherer.js) - a [Gatherer](https://github.com/GoogleChrome/lighthouse/blob/master/docs/architecture.md#components--terminology) that collects `window.myLoadMetrics.searchableTime`
from the context of the page.

- [searchable-audit.js](searchable-audit.js) - an [Audit](https://github.com/GoogleChrome/lighthouse/blob/master/docs/architecture.md#components--terminology) that tests whether or not `window.myLoadMetrics.searchableTime`
stays below a 4000ms threshold. In other words, Lighthouse will consider the audit "passing"
in the report if the search box initializes within 4s.

- [custom-config.js](custom-config.js) - this file tells Lighthouse where to
find the gatherer and audit files, when to run them, and how to incorporate their
output into the Lighthouse report. This example extends [Lighthouse's
default configuration](https://github.com/GoogleChrome/lighthouse/blob/master/lighthouse-core/config/default-config.js).

**Note**: when extending the default configuration file, passes with the same name are merged together, all other arrays will be concatenated, and primitive values will override the defaults.

## Run the configuration

Run Lighthouse with the custom audit in terminal

```sh
npm run audit
```

## Basic Custom Audit Recipe

> See [Lighthouse Architecture](../../../docs/architecture.md) for information
on terminology and architecture.
