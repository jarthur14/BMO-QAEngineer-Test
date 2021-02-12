# BMO-QAEngineer-Test
To execute my tests i've installed Ruby and DevKit
Install Cucumber through CMD
Install IDE RubyMine
Install watir-webdriver through CMD

Feature: Use the website to find restaurants
So that I can order food
As a hungry customer
I want to be able to find restaurants in my area
Scenario: Search for restaurants in an area
Given I want food in "AR51 1AA"
When I search for restaurants
Then I should see some restaurants in "AR51 1AA" 

Answer: 
Step Definition:
Given('I want food in {string}') do |string|
  pending # Write code here that turns the phrase above into concrete actions
end
When('I search for restaurants') do
  pending # Write code here that turns the phrase above into concrete actions
end
Then('I should see some restaurants in {string}') do |string|
  pending # Write code here that turns the phrase above into concrete actions
end
--------------------------------------------------------
Additional scenarios:
-	Invalid postal code
o	Feature: Enter postcode
Scenario: Enter an invalid postcode
Given I am on Just-Eat page
When enter invalid postcode
Then error post code shown

Step Definition:
Given (/^I am on the Just-Eat page $/)do
browser.goto " https://www.just-eat.co.uk/ "
end
When (/^enter invalid post code$/)do
browser.text_field(:name,"postalcode").set(" ")
browser.button(:name,"btnSearch").click
end
Then (/^error postal code shown$/)do
puts " Please enter a full, valid postcode".red
browser.close

---
-	Invalid Login 
o	Feature: Just-Eat login
To login in page we have to enter login details
Scenario: Register On Just-Eat page without email
Given I am on the Just-Eat page
When enter blank details for Register
Then error email shown
Given (/^I am on the Just-Eat page $/)do
browser.goto " https://www.just-eat.co.uk/ "
end
When (/^enter blank details for Register$/)do
browser.text_field(:name,"emailid").set(" ")
browser.button(:name,"btnLogin").click
end
Then (/^error email shown$/)do
puts " Email is Required".red
browser.close

-	Sort by minimum order
o	Feature: Sort by minimum order
Scenario: Select Minimum order
Given I am on results page
When click Sorted by Best match
When click minimum order
Then list of restaurants sorted by minimum order 

Step Definition:
Given (/^I am on the results page $/)do
browser.goto " https://www.just-eat.co.uk/area/ar51-area51"
end
When (/^Sorted by Best match$/)do
browser.button(:name,"sort_item").click
When (/^minimum order$/)do
Browser.button(:name, “sort_item_checkbox”).click
end
Then (/^list of resturants sorted by minimum order$/)
