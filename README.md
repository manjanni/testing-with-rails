# Testing with Rails

Resources: [rails documentation](https://guides.rubyonrails.org/testing.html "rails documenation")

Example App: a blog with different articles

### Unit Testing

A testing method where individual units / compoments are tested.

Example:

* Validation for model, e.g. each blog article should have a title

1. Write test case in /test/models folder
2. Run it with `rails test:models`
3. Write actual code to pass test



### System Testing

[documenation system test](https://guides.rubyonrails.org/testing.html#implementing-a-system-test)

A method to test user interactions within the application, running tests in a real or headless browser.

#### 1. Write test case in /test/system folder



```
  test "creating an article" do
    visit articles_path

    click_on "New Article"

    fill_in "Title", with: "Creating an Article"
    fill_in "Body", with: "Created this article successfully!"

    click_on "Create Article"

    assert_text "Creating an Article"
  end

```

#### 2. Run it with `rails test:system`


In case the test fails the error message is directly visible in the terminal. 
![image](https://user-images.githubusercontent.com/59453084/123876535-ccf77780-d93b-11eb-8b64-72c37fd978fd.png)


