# Frenzy API

![frenzy-api](https://img.shields.io/npm/v/revolt-api)

This package contains typings for objects in the [Frenzy API](https://github.com/frenzycoms/backend) and a fully typed API request builder.

### Example Usage

If you just need access to types:

```typescript
import type { User } from 'frenzy-api';
```

If you want to send requests:

```typescript
import { API } from 'frenzy-api';

// Initialise a new API client:
const client = new API();

// or with authentication:
const client = new API({ authentication: { revolt: 'bot-token' } });

// Make requests with ease:
client.get('/users/@me')
    // Fully typed responses!
    .then(user => user.username);

// No need to worry about the details:
let channel_id = "some channel id";
client.post(`/channels/${channel_id}/messages`, {
    // Parameters given are fully typed as well!
    content: "some content"
});
```

For more details on how this works, see the [README of @insertish/oapi](https://github.com/insertish/oapi#example).
