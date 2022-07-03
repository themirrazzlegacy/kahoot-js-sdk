# kahoot-js-sdk
A simple JavaScript SDK for interacting with Kahoot's API.
Work-in-progress


## Development Progress

Current state: creating initial SDK files
Note: The SDK is still being developed. Once the initial release is complete, a "Support Features" section will appear.

## The Enabled Services API
This sees what features a Kahoot creator has. The SDK will return values as follows:
* `create_kahoot` - The user is allowed to create a Kahoot.
* `theme_packs` - The user can change the theme pack on a Kahoot
* `bitmoji` - The user can use Bitmoji as their profile or in the lobby.
* `lobby_music` - The user is allowed to change the Lobby Music when hosting a game.
* `question_points` - The user is allowed to change the amount of points a question is worth.
* `vimeo` - The user is allowed to include Vimeo media in their Kahoots.
* `youtube_search` - The user is allowed to include Youtube media in their Kahoots.
* `getty_stock` - The user is allowed to include Getty Stock Image media in their kahoots.
* `question_bank` - The user is allowed to get all the types of questions in the Kahoot! Question Bank.

## The Kahoot Library API
This gets a list of all the folders in a creator's library, and the Kahoots in them.
Folders are returned by the SDK in the following format:

`const creationDate: Date` The date the folder was created.

`const quizes: KahootQuiz|KahootCourse[]` An array of all the Kahoots in the folder.

`const name:string` The name of the folder.


`event load():FolderLoadEvent` Fired when the folder info is loaded.


## The User API
A `User` object represents a user of `create.kahoot.it`.

`const emailAddress: string` The user's email address

`const acceptedTerms: boolean` Wether the user has accepted the terms and conditions

`const library: UserLibrary` The user's library.

`const creationDate: Date` The date when the account was created

`const language: KahootLocale` The language the user is using.

`const birthday: UserBirthDate` The birthdate of the user

`const pfpUrl: string` The URL of the user's profile picture

`const name: string` The user's username.
 
`const enabledServices: KahootService[]` The user's enabled services.

`const quizes: KahootQuiz[]` The user's quizzes

`const courses: KahootCourse[]` The user's courses

`const profile: UserProfile` The user's profile

## UserProfile

`const birthMonth: KahootMonthName` The user's birth month

`const birthYear: number` The user's birth year

`const birthDate: number` The user's birth date

`const username: string` The user's username

`const name: string` The user's name
 
`const profileIconURL: string` the URL of the user's profile picture

`const isAdult: boolean` wether the user is an adult

`const locale: KahootLocale` the user's language

`const emailAddress: string` The user's email address

`async setName(name: string)` changes the user's name

`async setEmail(email: string)` changes the user's email address

`async setPfpUrl(imageUrl: string)` changes the user's profile picture

`async setLocale(locale: KahootLocale)` changes the user's language

## UserBirthDate 

`getMonth():number` returns the month the user was born

`getYear():number` returns the year the user was born

`getDate():number` returns the date the user was born on

`getAge():number` returns the user's age based on the current date

`getTime():number` returns the amount of milliseconds from the UNIX epoch from the user's birthday at 12:00 AM UTC

`getDateObject():Date` returns a Date object represent the user's birthdate

`getMonthName(): KahootMonthName` gets the human-readable month name

`isAdult(): boolean` return true if the result of getAge is 18 or older.

`isOnHoliday():boolean` wether the user was born on a holiday

`isChristmas():boolean` Wether the user was born on Christmas

`isHalloween():boolean` Wether the user was born on Halloween

`isValentinesDay():boolean` Wether the user was born on Valentine's Day.

## KahootMonthName

`enum "January" | "February" | "March" | "April" | "May" | "June" | "July" | "August" | "September" | "October" | "November" | "December"`

## KahootLocale

`enum "en-US" | "uk-US" | "au-US" | "es" | "fr" | "jp" | "hw`
