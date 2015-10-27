# pathfinder
Pathfinder v1501 (2015-10-26) by Mauro Pagano

Pathfinder is a "free to use" tool to perform brute-force analysis of execution plans
for a SQL statement. 
It executes the SQL hundeds on times with different CBO environments. 
Pathfinder installs nothing. Make sure to connecte as SYS.
Depending on how long the SQL takes to execute, Pathfinder can take hours to complete.
It's recommended to use Pathfinder in test, use it in production only after careful tests
and if you understand the risks. 
Output ZIP file can be large (several MBs), so you may want to execute Pathfinder 
from a system directory with at least 1 GB of free space. 

Steps
~~~~~
1. Unzip pathfinder-master.zip, navigate to the root pathfinder directory, and connect as SYS:

   $ unzip pathfinder-master.zip
   $ cd pathfinder-master
   $ sqlplus / as sysdba

2. Open SQL script file script.sql and add your SQL in there. Make sure to add the mandatory
   comment /* ^^pathfinder_testid */

2. Execute pathfinder.sql, the single input parameter is the connect string to the user
   that is supposed to execute the SQL. Assume the user is scott with pwd tiger in database
   ORCL then the connect string will be scott/tiger@orcl

   SQL> @pathfinder.sql 
   
3. Unzip output pathfinder_<dbname>_<date>.zip into a directory on your PC

4. Review main html file 00001_pathfinder_<dbname>_<date>_index.html

****************************************************************************************
   
    Pathfinder - Plan finder
    Copyright (C) 2015  Mauro Pagano

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.
