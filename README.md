# SQL-Data-Cleaning
The provided code focuses on cleaning and standardizing data in the "NashvilleHousing" table using SQL queries. Here is an overview of the different sections of the code:

Standardizing date format:

The code selects all columns from the "NashvilleHousing" table to view the data.
It then converts the "SaleDate" column to a standardized date format using the CONVERT function.
Populating property address data:

The code selects the columns "ParcelID," "PropertyAddress," and "UniqueID" from the "NashvilleHousing" table to identify records with missing property addresses.
It performs a self-join on the "ParcelID" column and excludes matching records with the same "UniqueID" to avoid duplicates.
The query updates the missing property addresses with non-null values from the joined records.
Breaking out address into individual columns:

The code selects the "PropertyAddress" column to split it into separate address and city columns.
It uses the SUBSTRING and CHARINDEX functions to extract the address and city from the "PropertyAddress" column and stores them in new columns.
Breaking out owner address into individual columns:

The code selects the "OwnerAddress" column and uses the PARSENAME function to split it into separate address, city, and state columns.
The address, city, and state values are stored in new columns.
Changing "Y" and "N" values to "Yes" and "No":

The code selects the distinct values of the "SoldAsVacant" column and their respective counts.
It uses a CASE statement to replace "Y" with "Yes" and "N" with "No" in the "SoldAsVacant" column.
Removing duplicates:

The code uses a Common Table Expression (CTE) named "RowNumCTE" to assign row numbers to each record based on specific columns.
It selects all columns from the "RowNumCTE" where the row number is greater than 1, indicating duplicate records.
The duplicated records are ordered by the "PropertyAddress" column.
Deleting unused columns:

The code selects all columns from the "NashvilleHousing" table to view the data.
It then removes the "OwnerAddress," "TaxDistrict," "PropertyAddress," and "SaleDate" columns from the table.
Overall, the code demonstrates various SQL operations and functions to clean and transform data, including standardizing date formats, populating missing values, splitting addresses into individual columns, changing values, removing duplicates, and deleting unnecessary columns.
