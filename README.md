# eventlama-graphiql
[GraphiQL](https://github.com/graphql/graphiql) for [https://eventlama.com/](https://eventlama.com/) GraphQL public API.

# Usage
```
npm install

python -m SimpleHTTPServer 8000
```

# Examples

## Queries


## Mutations

Mutation parameters:

- ref: Is the ticket's ref.

- proposalId: Is proposal's id.

**Vote to a proposal:**

- vote: Is the total vote count, between 0 to 5.

```
mutation {
	voteProposal(ref:"N0QA-2", proposalId:1, vote:3) {
		id
	}
}
```

**Comment to a proposal:**

- comment: Is the comment text.


```
mutation {
	commentProposal(ref: "JAPI-1", proposalId: 1, comment: "cool comment") {
		id
		title
		description
		speakers {
			id
			name
			bio
		}
	}
}
```

**Send a Message**

- message: Is the message text.

- recieverId: Is the user's id which receives the message.

```
mutation {
	sendMessage(ref: "JAPI-1", receiverId: 690, message: "an awesome message") {
		id
		message
		createdAt
	}
}
```

**Create a Post**

- text: Is the post text.

```
mutation {
	createPost(ref: "JAPI-1", proposalId: 1, text: "awesome post!") {
		id
		text
		createdAt
	}
}
```

**Like a Post**

- postId: Is the post's id which the like is for.

```
mutation {
	likePost(ref: "JAPI-1", postId: 1) {
		id
		createdAt
	}
}

```

**Like a Post**

- postId: Is the post's ids which the comment is for.

- text: Is the comment text.

```
mutation {
	commentPost(ref: "JAPI", postId: 1, text: "an awesome comment") {
		id
		text
		createdAt
	}
}
```

## Subscriptions

See: [https://github.com/chris-ramon/el-graphql-subscriptions](https://github.com/chris-ramon/el-graphql-subscriptions)

visit: [http://localhost:8000/](http://localhost:8000/)
