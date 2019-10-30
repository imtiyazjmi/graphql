1. Signup Payload: 
   mutation {
	  signup(
		name: "XYZ"
		email: "xyz@prisma.io"
		password: "xyz"
	  ) {
		token
		user {
		  id
		}
	  }
	} 
	
2. Login payload:

   mutation {
  login(
    email: "xyz@prisma.io"
    password: ""
  ) {
    token
    user {
      email
      links {
        url
        description
      }
    }
  }
}

3. Adding data into database POST
   mutation {
  post(
    url: "www.graphqlweekly2.com"
    description: "Curated2 GraphQL content coming to your email inbox every Friday"
  ) {
    id
  }
}

4. Subscription of data to listen message
   subscription {
  newLink {
      id
      url
      description
      postedBy {
        id
        name
        email
      }
  }
}

5. pagination
   query {
  feed (skip:0, first: 2){
    count
    links {
      id
      description
      url
    }
  }
}
 
6. Sorting
   query {
  feed(orderBy: createdAt_ASC) {
    id
    description
    url
  }
} 
