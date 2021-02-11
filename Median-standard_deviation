# calculating standard deviation and median without buili-in functions
import pandas as pd
df = pd.read_csv("Sensor_readings.csv")
locations = set(df['location'])
locations = list(locations)
#locations

# function to get median of a list of numbers
# median is the value in the middle of a sorted list, in odd number od values it is avarage of the two middle values
def median_(listi):
    listi.sort() # return a sorted list
    rows = len(listi)
    if rows %2 == 0: # check if the number length of list is even
        median_listi = listi[rows//2] # the middle value in a list with even number of values
    else:
         median_listi = (listi[rows//2] + listi[rows//2+1])/2 #the avarage of two middle values in a list with odd number of values
            
    return median_listi
    
# function to get standard deviation of a list of numbers
def standard_deviation(listi):
    mean_listi = sum(listi)/len(listi)
    square_diff = [(element- mean_listi)**2 for element in listi]
    sdv = pow(sum(square_diff), 1/2)/len(listi)
    return sdv
    
"""to get median and standard deviation for differnt locations and for each columns of:
'temp_max', 'temp_min','temp_avg','light_max','light_min', 'light_avg','humidity_min','humidity_max'  """
columns = ['temp_max', 'temp_min','temp_avg','light_max','light_min', 'light_avg','humidity_min','humidity_max']
df_median = pd.DataFrame(index = locations, columns = columns) # dataframe of all the asked columns to have median
df_standard_deviation = pd.DataFrame(index = locations, columns = columns) 


for locs in locations:
    for cols in columns: 
        df_median.loc[locs,cols] = median_(list(df[df['location']== locs][cols]))
        df_standard_deviation = standard_deviation(list(df[df['location']== locs][cols]))
