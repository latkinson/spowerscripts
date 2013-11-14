sPowerScripts | StatusPH power scripts to help map data

StatusPh.net is an online map and database that maps data real-time based on user and system input. We do not have any data unless it is added by users or systems.
We created an API, which is extremely easy to use.

Please make scripts that grab data from excel sheets, websites, whatever data source you can think of, and input it in our API so that people in need can search for the data they need.

To call our API, simply GET request to http://statusph.net:8000/input?[INFO_TYPE,LatLng(X,Y),NAME,HEADS,CONTACT_INFORMATION,MORE_INFORMATION]

@param INFO_TYPE = The type of information you are giving us. 
@info Since this is what the filter uses, try to be as descriptive as can be. For example, INFO_TYPE "tweet about somebody that needs rescued" will be filtered with both "tweet", "somebody", "rescued", and all the other words in the sentence.
@input URL ENCODED STRING

@param LatLng(X,Y) = The geodata information, LatLng keeps it clear what to put first, so your insert would be for example LatLng(10.00,100.00)
@info In case of duplicate locations, the newest one will override.
@input LatLng(FLOAT,FLOAT)

@param NAME = The name you are giving this input, such as the city name, a person name
@info please do not get confused with info type. This is basically the name of your type.
@input URL ENCODED STRING

@param HEADS = The amount of heads on your location. 
@info We can later let authorities filter by heads
@input REGULAR INTEGER MAX LENGTH 6 (so 999.999)

@param CONTACT_INFO = the contact information of the location, think about a telephone number, an address, a twitter account, a facebook account
@info /
@input URL ENCODED STRING

@param MORE_INFO = Any other information that you would like to share. 

@info MAX LENGTH 2505

@input URL ENCODED STRING


Example input
INFO_TYPE: BROKEN HOSPITAL (BROKEN%20HOSPITAL)
NAME: I AM A NAME (I%20AM%20A%20NAME)
HEADS: 100
CONTACT_INFO: HOSPITAL ROAD A (HOSPITAL%20ROAD%20A)
MORE_INFO: THIS HOSPITAL IS BROKE DOWN BECAUSE OF THE STORM (THIS%20HOSPITAL%BROKE%DOWN%BECAUSE%OF%THE%STORM)


http://statusph.net:8000/input?[BROKEN%20HOSPITAL,LatLng(10.000,100.000),I%20AM%20A%20NAME,100,HOSPITAL%20ROAD%20A,THIS%20HOSPITAL%BROKE%DOWN%BECAUSE%OF%THE%STORM]

Please commit all your scripts to this git and add a README.md to your directory so we know what you are working on.
