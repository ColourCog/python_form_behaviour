# Python Form Behaviours

The aim of this project is create a set of form and form widget behaviour rules that a project could inherit to garantee homogeneous model->form conversion.

## Expected behaviour

### Forms

1. receive a model or model instance
2. create appropriate widgets for each attribute
3. collect values/errors for each widget
4. return a structured response (an instance of the model, if you will)

This is the kind of response we expect from a form

```python
response = {
  username: 'alladin',
  email: 'alladin@aghraba.ar'
  password: 'yasmine',
}

### Widgets

1. receive an attribute
2. set initial value
3. update value
4. run validations on value
5. return a structured response

This is what I expect from a widget

```python
response = {
  name: "password",
  value: "yasmine",
  errors: ["too short", "no special chars"],
  meta: {
    ranking: 0.2
  }
}

### Validators

1. receive a value
2. run a set of validations (policies) on this value
3. return a structured response

I've been thinking about the kind of response I expect from a validator. I think this is the kind of things I want to see, for a password validation response, for instance

```python
response = {
  value: "yasmine",
  errors: ["too short", "no numbers", "no special chars"],
  meta: {
    ranking: 0.2,
  },
}
```
