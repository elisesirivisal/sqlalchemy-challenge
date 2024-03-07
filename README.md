# sqlalchemy-challenge


<div>
<h2>Before You Begin</h2>
  <ol>
    <li>Create a new repository for this project called  `sqlalchemy-challenge`.  **Do not add this assignment to an existing repository**.</li>
    <li>Clone the new repository to your computer.</li>
    <li>1.  Inside your local Git repository, create a directory for this Challenge. Use a folder name that corresponds to the Challenge, such as  `SurfsUp`.</li>
    <li>1.  Add your Jupyter notebook and  `app.py`  to this folder. They’ll contain the main scripts to run for analysis. Also add the  `Resources`  folder, which contains the data files you will be using for this challenge.</li>
    <li>Push the above changes to GitHub.</li>
  </ol>
</div>

<div>
  <h2>Files</h2>
  <p>Download the following files to help you get started: <a href="https://static.bc-edx.com/data/dl-1-2/m10/lms/starter/Starter_Code.zip</a></p>
</div>

<div>
  <h2>Instructions</h2>
  <p>Congratulations! You've decided to treat yourself to a long holiday vacation in Honolulu, Hawaii. To help with your trip planning, you decide to do a climate analysis about the area. The following sections outline the steps that you need to take to accomplish this task.</p>
</div>

<div>
	<h2>Part 1: Analyze and Explore the Climate Data</h2>
	<p>In this section, you’ll use Python and SQLAlchemy to do a basic climate analysis and data exploration of your climate database. Specifically, you’ll use SQLAlchemy ORM queries, Pandas, and Matplotlib. To do so, complete the following steps:</p>
	<ol>
		<li>Note that you’ll use the provided files (`climate_starter.ipynb`  and  `hawaii.sqlite`) to complete your climate analysis and data exploration.</li>
		<li>Use the SQLAlchemy  `create_engine()`  function to connect to your SQLite database.</li>
		<li>Use the SQLAlchemy  `automap_base()`  function to reflect your tables into classes, and then save references to the classes named  `station`  and  `measurement`.</li>
		<li>Link Python to the database by creating a SQLAlchemy session.</li>
	<li>Perform a precipitation analysis and then a station analysis by completing the steps in the following two subsections.</li>
	</ol>
	<p>
	<h3>Precipitation Analysis</h3>
	<ol>
		<li>Find the most recent date in the dataset.</li>
		<li>Using that date, get the previous 12 months of precipitation data by querying the previous 12 months of data.</li>
		(Hint: Don’t pass the date as a variable to your query.)
		<li>Select only the "date" and "prcp" values.</li>
		<li> Load the query results into a Pandas DataFrame. Explicitly set the column names.</li>
		<li>Sort the DataFrame values by "date".</li>
		<li>Plot the results by using the DataFrame  `plot`  method, as the following image shows:</li>
		<img src="Images/precipitation.jpg">
		<li>Use Pandas to print the summary statistics for the precipitation data.</li>
	</p>
	<p>
	<h3>Station Analysis</h3>
	<ol>
		<li>Design a query to calculate the total number of stations in the dataset.</li>
		<li>Design a query to find the most-active stations (that is, the stations that have the most rows). To do so, complete the following steps:</li>
	    <ul>
		    <li>List the stations and observation counts in descending order.</li>
		(Hint: Don’t pass the date as a variable to your query.)
		<li>Answer the following question: which station id has the greatest number of observations?</li>
	    </ul>
		<li> Design a query that calculates the lowest, highest, and average temperatures that filters on the most-active station id found in the previous query.</li>
	(Hint: You’ll need to use functions such as `func.min`, `func.max`, and `func.avg` in your query.)
		<li>Design a query to get the previous 12 months of temperature observation (TOBS) data. To do so, complete the following steps:</li>
	    <ul>
		    <li>Filter by the station that has the greatest number of observations.</li>
		    <li>Query the previous 12 months of TOBS data for that station.</li>
		    <li>Plot the results as a histogram with  `bins=12`, as the following image shows:</li>
	    </ul>	
		<img src="Images/station-histogram.jpg">
		<li>Close your session.</li>
	</p>
</div>

<div>
	<h2>Part 2: Design Your Climate App</h2>
	<p>Now that you’ve completed your initial analysis, you’ll design a Flask API based on the queries that you just developed. To do so, use Flask to create your routes as follows:</p>
	<ol>
		<li>`/`</li>
			<ul>
				<li>Start at the homepage.</li>
		        <li>List all the available routes.</li>
			</ul>
		<li> `/api/v1.0/precipitation`
		    <ul>
				<li>Convert the query results from your precipitation analysis (i.e. retrieve only the last 12 months of data) to a dictionary using  `date`  as the key and  `prcp`  as the value.</li>
		        <li>Return the JSON representation of your dictionary.</li>
			</ul>
	  <li>`/api/v1.0/stations`</li>
			<ul>
				<li>Return a JSON list of stations from the dataset.</li>
			</ul>
	  <li>`/api/v1.0/tobs`</li>
		    <ul>
				<li>Query the dates and temperature observations of the most-active station for the previous year of data.</li>
				<li>Return a JSON list of temperature observations for the previous year.</li>
			</ul>
	<li>`/api/v1.0/<start>` and `/api/v1.0/<start>/<end>`</li>
		    <ul>
				<li>Return a JSON list of the minimum temperature, the average temperature, and the maximum temperature for a specified start or start-end range.</li>
			    <li>For a specified start, calculate  `TMIN`,  `TAVG`, and  `TMAX`  for all the dates greater than or equal to the start date.</li>
			    <li>For a specified start date and end date, calculate  `TMIN`,  `TAVG`, and  `TMAX`  for the dates from the start date to the end date, inclusive.</li>
			</ul>
	</ol>
	<p><h3>Hints</h3>
	<ul>
		<li>Join the station and measurement tables for some of the queries.</li>
	    <li>Use the Flask  `jsonify`  function to convert your API data to a valid JSON response object.</li>
	</ul>
	</p>
</div>
<div>
	<h2>Requirements</h2>
		<h3>Jupyter Notebook Database Connection (10 points)</h3>
		To receive all points, you must
		<ul>
			<li>Use the SQLAlchemy  `create_engine()`  function to connect to your SQLite database (1 point)</li>
			<li>Use the SQLAlchemy  `automap_base()`  function to reflect your tables into classes (3 points)</li>
			<li>Save references to the classes named  `station`  and  `measurement`  (4 points)</li>
			<li>Link Python to the database by creating a SQLAlchemy session (1 point)</li>
			<li>Close your session at the end of your notebook (1 point)</li>
		</ul>
		<h3>Precipitation Analysis (16 points)</h3>
To receive all points, you must
<ul>
    <li>Create a query that finds the most recent date in the dataset (8/23/2017) (2 points)</li>
    <li>Create a query that collects only the `date` and `precipitation` for the last year of data without passing the date as a variable (4 points)</li>
    <li>Save the query results to a Pandas DataFrame to create `date` and `precipitation` columns (2 points)</li>
    <li>Sort the DataFrame by `date` (2 points)</li>
    <li>Plot the results by using the DataFrame `plot` method with `date` as the x and `precipitation` as the y variables (4 points)</li>
    <li>Use Pandas to print the summary statistics for the precipitation data (2 points)</li>
</ul>
<h3>Station Analysis (16 points)</h3>
To receive all points, you must
<ul>
    <li>Design a query that correctly finds the number of stations in the dataset (9) (2 points)</li>
    <li>Design a query that correctly lists the stations and observation counts in descending order and finds the most active station (USC00519281) (2 points)</li>
    <li>Design a query that correctly finds the min, max, and average temperatures for the most active station (USC00519281) (3 points)</li>
    <li>Design a query to get the previous 12 months of temperature observation (TOBS) data that filters by the station that has the greatest number of observations (3 points)</li>
    <li>Save the query results to a Pandas DataFrame (2 points)</li>
    <li>Correctly plot a histogram with `bins=12` for the last year of data using `tobs` as the column to count. (4 points)</li>
</ul>
<h4>API SQLite Connection & Landing Page (10 points)</h4>
<p>To receive all points, your Flask application must</p>
<ul>
    <li>Correctly generate the engine to the correct sqlite file (2 points)</li>
    <li>Use `automap_base()` and reflect the database schema (2 points)</li>
    <li>Correctly save references to the tables in the sqlite file (`measurement` and `station`) (2 points)</li>
    <li>Correctly create and bind the session between the python app and database (2 points)</li>
    <li>Display the available routes on the landing page (2 points)</li>
</ul>
<h4>API Static Routes (15 points)</h4>
<p>To receive all points, your Flask application must include</p>
<ul>
    <li>A precipitation route that:
        <ul>
            <li>Returns json with the date as the key and the value as the precipitation (3 points)</li>
            <li>Only returns the jsonified precipitation data for the last year in the database (3 points)</li>
        </ul>
    </li>
    <li>A stations route that:
        <ul>
            <li>Returns jsonified data of all of the stations in the database (3 points)</li>
        </ul>
    </li>
    <li>A tobs route that:
        <ul>
            <li>Returns jsonified data for the most active station (USC00519281) (3 points)</li>
            <li>Only returns the jsonified data for the last year of data (3 points)</li>
        </ul>
    </li>
</ul>

<h4>API Dynamic Route (15 points)</h4>
<p>To receive all points, your Flask application must include</p>
<ul>
    <li>A start route that:
        <ul>
            <li>Accepts the start date as a parameter from the URL (2 points)</li>
            <li>Returns the min, max, and average temperatures calculated from the given start date to the end of the dataset (4 points)</li>
        </ul>
    </li>
    <li>A start/end route that:
        <ul>
            <li>Accepts the start and end dates as parameters from the URL (3 points)</li>
            <li>Returns the min, max, and average temperatures calculated from the given start date to the given end date (6 points)</li>
        </ul>
    </li>
</ul>
<h4>Coding Conventions and Formatting (8 points)</h4>
<p>To receive all points, your code must</p>
<ul>
    <li>Place imports at the top of the file, just after any module comments and docstrings, and before module globals and constants. (2 points)</li>
    <li>Name functions and variables with lowercase characters, with words separated by underscores. (2 points)</li>
    <li>Follow DRY (Don't Repeat Yourself) principles, creating maintainable and reusable code. (2 points)</li>
    <li>Use concise logic and creative engineering where possible. (2 points)</li>
</ul>
<h4>Deployment and Submission (6 points)</h4>
<p>To receive all points, you must</p>
<ul>
    <li>Submit a link to a GitHub repository that’s cloned to your local machine and contains your files. (2 points)</li>
    <li>Use the command line to add your files to the repository. (2 points)</li>
    <li>Include appropriate commit messages in your files. (2 points)</li>
</ul>

<h4>Comments (4 points)</h4>
<p>To receive all points, your code must</p>
<ul>
    <li>Be well commented with concise, relevant notes that other developers can understand. (4 points)</li>
</ul>
<h4>References</h4>
<p>Menne, M.J., I. Durre, R.S. Vose, B.E. Gleason, and T.G. Houston, 2012: An overview of the Global Historical Climatology Network-Daily Database. Journal of Atmospheric and Oceanic Technology, 29, 897-910, <a href="https://journals.ametsoc.org/view/journals/atot/29/7/jtech-d-11-00103_1.xml" target="_blank">https://journals.ametsoc.org/view/journals/atot/29/7/jtech-d-11-00103_1.xml</a></p>
