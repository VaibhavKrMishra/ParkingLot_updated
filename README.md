# ParkingLot_updated
Updated Parking Lot project

This project was made by me for making a parking lot bill generated.
There are following assupmtions made in this project(which are not specifically mentioned):
1: There is a flat charging per time period, i.e. , for any time period, the bill will not be rate * hours, just rate.
2: There is a requirement of 2 more API's : 1 for fetching result by ID(see below for specification) and on for all the entries.
3: The date format used to send and recieve timestamps for the entry and exit times is in format "yyyy-MM-dd HH:mm", where HH:mm specifies time in 24hrs format

Here are the relevent details:

There is a use of embedded database(H2), so the data stored will be deleted at restart/stop of the server
the post used for the server is : 8080

Here you will find the following API's :

>/ParkingLot/GetBills -
  Post API, Request body- {
                            "entryTime" : "yyyy-mm-dd HH:mm",
                            "exitTime" : "yyyy-mm-dd HH:mm"
                          }
                          
 This API is to insert a bill into DB and return the anount to FE in given format:
 {
      "id" : long,
      "startTime" : "yyyy-mm-dd HH:mm",
      "endTime":"yyyy-mm-dd HH:mm",
      "generatedAt" : "yyyy-mm-dd HH:mm",
      "amount" : int
 }
 
 > /ParkingLot/GetAllBills
 GET API,
 This api returns a list of Objects(which are similar to as in previous API)
 
 >/ParkingLot/BillById 
 Post API , Request Body = {
                              "id" : long
                            }
 This APi returns a bill for a specific ID;
 
 Thanks for checking out the code. 
 Stay well.
 
 ********************************************************************************************************************************************************************************
