# python12
from calendar import monthrange
from datetime import datetime

def DateDifference(udate):
    """A function for calculating the difference between a user input date
    and the current computer date. The function also finds the number of
    days of the user's input month.
    
    Arguments:
        udate {datetime} -- The user's input date.
    """
    # Printing dates
    print ("User's date: {}".format(udate))
    computer_date = datetime.today()
    print ("Current date: {}".format(computer_date))
    diff = udate - computer_date

    # Getting time in seconds and converting seconds to days, hours, mins and seconds 
    total_secs = diff.total_seconds()
    mins, secs = divmod(total_secs, 60)
    hours, mins = divmod(mins, 60)
    days, hours = divmod(hours, 24)
    # Printing the results
    print ("Date difference is {} days, {} hours, {} minutes and {} seconds.".format(int(days), int(hours), int(mins), int(secs))) 

    # Finding the number of days of the given month with calendar.monthrange
    month = udate.month
    year = udate.year
    number = monthrange(year, month)[1]

    print ("The number of days of {}/{} are {}.".format(year, month, number))

if __name__ == "__main__":
    
    # User provides date
    user_date = input("Insert a date in DD/MM/YYYY format: ")
    # Spliting date to numbers
    day, month, year = map(int, user_date.split("/"))
    # Creating a daytime object
