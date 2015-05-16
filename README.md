# runnable-hostname
util for generating an instance's elastic or direct hostname

# Usage
```js
var hostname = require('runnable-hostname');

hostname.elastic({
  shortHash: 'abcdef',
  instanceName: 'instanceName',
  branch: 'branch',
  ownerUsername: 'ownerUsername',
  masterPod: 'masterPod',
  userContentDomain: 'runnableapp.com'
});
// instanceName-staging-ownerUsername.runnableapp.com

hostname.direct({
  shortHash: 'abcdef',
  // non-masterPod instance has branch in name
  instanceName: 'branch-instanceName',
  branch: 'branch',
  ownerUsername: 'ownerUsername',
  masterPod: false,
  userContentDomain: 'runnableapp.com'
});
// abcdef-instanceName-staging-ownerUsername.runnableapp.com

hostname.direct({
  shortHash: 'abcdef',
  // masterPod instance has does NOT have branch in name
  instanceName: 'instanceName',
  branch: 'branch',
  ownerUsername: 'ownerUsername',
  masterPod: true,
  userContentDomain: 'runnableapp.com'
});
// abcdef-instanceName-staging-ownerUsername.runnableapp.com
```