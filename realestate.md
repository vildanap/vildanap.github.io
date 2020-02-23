# Real-estate app

**Project description:** The created application aims to improve the way of searching, posting ads and communication of users with real estate agencies, e.g. individuals who publish real estate ads.
Some of the benefits to users are: 
- reducing the time spent searching for the right property
- making it easier to contact, 
- facilitating a better deal by combining real estate with multiple agencies and individuals, 
- making it easier for agencies and individuals to find a buyer,
- reducing the time that the property will be rented or for sale. 

![Real estate](/images/real_estate_combined.jpg)

**Project goal**: The focus of the project was on user interaction design and mobile design patterns.

Retrofit 2 library was used for creating HTTP request and for processing HTTP response from a REST API.

![Real estate](/images/retrofit.png)

**Functionalities**:
The activities that the application should support are:
- user registration / login,
- publish and view existing ads,
- editing and deleting created ads,
- adding a property to your favorites and reviewing it later,
- real estate search by different parameters,
- an abbreviation for facilitating contacting the owner via email / phone,
- editing and deleting user account account

**Mobile design patterns**
- **Navigation (mobile apps): Global navigation at the bottom**
> With the help of global navigation at the bottom, the user has an overview of possible functionalities, only one touch away. To make it easier to navigate, the user always knows where he is (the title section and highlighting the section where the user is in color).
- **Content organization: Vertical stack (mobile applications)**
> Content is organized into a vertical column. Although the results or number of properties will be larger than the screen dimensions, it counts for scrolling speed. This way, the screen is not overloaded with side elements.
- **Generous Spaces (Mobile Apps): Wizard**
> The user was guided through the ad creation process step by step. First, the necessary information about the property is entered, after which the next step is to upload one or more pictures. The reason for using this step is, first and foremost, transparency, since it is a mobile application and scrolling across the screen is not the solution, it is better to separate these two tasks on two screens, with the possibility of returning to the step before in case change.
- **Organization of the site: Cards**
> Within the Home screen, the content is divided into tabs. It is not important for the user to immediately see all the ads, for example, only those that are for rent or for sale. This makes it easier to organize the space on the small screen.
- **Commands and actions: Output button highlighted, Progress indicator**
> Green letters were used for confirmation, while canceling / canceling was indicated in blue. This avoids the user clicking on a link or message by mistake, and clearly indicates that the action is completed.
- **Data entry: Good default values**
> In the case of a real estate search, the user should be exempted from entering all required fields. So the price slider is set to include all possible values, or by default all cities (All within the drop-down list) and all settlements are enabled in the search. This allows the user to change only the search parameters that are most important to him, without causing an error.

Reference: [Mobile Design Pattern Gallery, O'Reilly Media](http://shop.oreilly.com/product/0636920029311.do)

__Additional confirmation for DELETE action required__

    ![Real estate](/images/additional confirmation.PNG) 

__During image loading used progress indicator__

    ![Real estate](/images/progress indicator.PNG)

---
More implementation details on:

[FE GitHub project](https://github.com/vildanap/real_estate)

[BE GitHub project](https://github.com/vildanap/realestateBE)
