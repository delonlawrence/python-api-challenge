# python-api-challenge

this code to generate northern hemishere regressions came from chat
mport matplotlib.pyplot as plt
from scipy.stats import linregress

# Define a function for creating scatter plots and linear regression
def plot_scatter(x_values, y_values, x_label, y_label, title):
    plt.scatter(x_values, y_values)
    plt.xlabel(x_label)
    plt.ylabel(y_label)
    plt.title(title)
    plt.grid(True)
    
    # Perform linear regression
    (slope, intercept, rvalue, pvalue, stderr) = linregress(x_values, y_values)
    
    # Calculate regression values
    x_array = np.array(x_values)
    regress_values = x_array * slope + intercept
    line_eq = "y = " + str(round(slope,2)) + "x + " + str(round(intercept,2))
    
    
    # Plot regression line
    plt.plot(x_values,regress_values,"r-")
    
    # Add equation to plot
    plt.annotate(line_eq,(min(x_values),max(y_values)-20),fontsize=15,color="red")
    
    # Print r value
    print(f"The r-value is: {rvalue}")
    
    # Show plot
    plt.show()
