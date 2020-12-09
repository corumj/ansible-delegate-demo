# Ansible Delegate Demo

Need to check to see how to use delegate_to within a playbook triggered from Ansible Tower's API and passing in extra_vars that will be used to narrow down which servers we act on.

Setup a test group in Ansible Tower 
Using Postman (or some other API tool) setup basic authentication with your username and password.  Setup a POST call to your API endpoint for the job template something like this:
`https://ansibletowerserver/api/v2/job_templates/24/launch/`
in the body of the POST:
```
{
    "extra_vars": {
        "object_name": "test"
    }     
}
```

When you post it, this example will run and limit it to the test group (or any group you pass in as object_name but the group has to exist first)