SqliteODBC
==========

Christian Werner's Sqlite ODC Driver in a MSVC2008 project. With patches.

Added fix for specific problem using this driver with MFC ODBC.
Columns defined as blob in sqlite and consumed as a CByteArray in MFC
tries to read the column data into a NULL CByteArray m_pData pointer.
MFC sets up the pointer by using size info retrieved from the driver.
The driver sets up a column of blob type to SQL_BINARY type which is assigned 
zero size.
