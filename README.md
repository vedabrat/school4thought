# README

This README would normally document whatever steps are necessary to get the
application up and running.
Things you may want to cover:
* Ruby version
* System dependencies
* Configuration
* Database creation
* Database initialization
* How to run the test suite
* Services (job queues, cache servers, search engines, etc.)
* Deployment instructions
* ...


Assuming this is the user flow ->

user - 1st time mentor
  I fill my profile out |resume/github/onlineTrackRecord/CredentialsMediaUpload | age| location| phone | home | experience |
  I describe an example of my mentorship ability and the length of time I am willing to take on a mentee
  I set up the pay structures (upfront costs like venues/mentee-accomodation, budget) and let this be viewed on my profile.
  (infographic to illustrate the payments over time). I detail what things I am willing to do and not willing to do.
  (suggestion of letting me have an easy route to lay out my mentorship program),
  I detail HOW the mentee will be billed. (upfront costs, pay as you go costs, variable payment costs, sessions, weekly, lump).
  ~ timespan break ~
  I await an app or email notification for mentees who have bid on me.
  I review the mentee's profile and whether I can successfully mentor them.
  A chat with the mentee ensues where the billing of the mentee is approved or changed and then reapproved
  I deny or approve. This transfers the money (either on a payment plan or a initial lump sum) as well.
    ---Approval path -
      Money is deposited as per payment plan. My mentee count rises by 1.
      Review forms to be filled out after every #{session} or #{meetingdate}, which creates the mentee's rating - viewable to me.
      {### suggestion### Freezing/Pausing mentorship can be initiated - will trigger a series of payment pauses and delaying of program completion}
      Last session payment is received after Mentee reviews
      i approve progress bar for how close my mentee is to completeing the program.
      Upon 100%, relationship is terminated (??? unless time isnt completed for relationship ???). mentee count reduced to 0.
    ---Deny path -
      Bid is voided.  


user - 1st time mentee
  I fill my profile out |resume/github/onlineTrackRecord/CredentialsMediaUpload | age| location| phone | home | experience |
  I get to use a search to see what mentors exist, requirements, what programs they offer, pay structures and for how long they choose to mentor (their profile essentially),
  I click their "bid/pay now" which triggers a notification to be sent to the mentor, and reserves the money upon denial or approval of the mentor.
   If this approval doesnt happen within 1.5 months, then the money is returned minus processing fees.  
  I await the mentor's messaging, and after some conversation, approval, change or denial.
    ---Approval path -
      Money is withdrawn as per payment plan. mentor count rises by 1.
      Review forms to be filled out after every #{session} or #{meetingdate}, which creates a mentor rating - viewable to mentees.
      Upon completion of program, mentorship is registered on the profile, mentor count reduced to 0.
    ---Deny path -
      Money is returned minus a fee.

  Backend notes
  set.
  current_user is_mentor?
                          resume/github/onlineTrackRecord/CredentialsMediaUpload |
                          name
                          age
                          location
                          phone
                          home
                          email
                          Experience
                          Start date: =today
                          Rating : TBD
                          Age : Num
                          Description:
                          Availability Calendar:
                          Mentorship Timespan:
                          Program:
                                  description
                                  events
                                  purchases_for_students                                  
                                  completion_certificate
                                  Price: [Payment_plan][All-at-once] {cost_types: upfront, pay as you go, variable payment, sessions, weekly, lump}
                          current_mentee_count:
                          former_mentees:<public><private> (eg, Brad Pitt, Vedabrat Etwaru & 2 others)
                          profile_photo
                          external_links
                                        twitter
                                        facebook
                                        instagram
                                        snapchat
                          antiquated_accounts
                          program_id: (create unique page for program x userid x time)
                                     surveys[1-total_surveys_in_program]
                                     current_time
                                     current_progress
                                     estimated_completion_date
                                     payment_dates_and_times
                                     payment_record
                           quiz_score_results
                           mentee_match_algorithm:
                                                  parameters
                                                  codescore
                           mail
                           conversations

current_user  is_mentee?
                        resume/github/onlineTrackRecord/CredentialsMediaUpload |
                        name
                        age
                        location
                        phone
                        home
                        email
                        Experience
                        Start date: =today
                        Rating : TBD
                        Age : Num
                        Description:
                        Availability Calendar:
                        quiz_score_results
                        mentor_match_algorithm:
                                               parameters
                                               codescore
                        bank_account
                        money_in_lieu
                        mail
                        conversations
                        current_mentor_count:
                        former_mentors:<public><private> (eg, Brad Pitt, Vedabrat Etwaru & 2 others)
                        profile_photo
                        external_links
                                      twitter
                                      facebook
                                      instagram
                                      snapchat
                        antiquated_accounts
                        program_id: (create unique page for program x userid x time)
                                   surveys[1-total_surveys_in_program]
                                   current_time
                                   current_progress
                                   estimated_completion_date
                                   payment_dates_and_times
                                   payment_record
