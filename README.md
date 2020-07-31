# HAPS
Installation locally

Please download the compressed package here: 

On Windows system

Make sure that your R is installed in 'c:\program files'

Install Rtools in 'c:\program files'

Add R and Rtools to the Path Variable on the Environment Variables panel, including

c:\program files\Rtools\bin

c:\program files\Rtools\gcc-4.6.3\bin

c:\program files\R\R.3.x.x\bin\i386

c:\program files\R\R.3.x.x\bin\x64

Run the following code in R

install.packages('HAPS.tar.gz', repos = NULL, type='source')

On Linux and Mac systems
Just run the following code in R

install.packages('HAPS.tar.gz', repos = NULL, type='source')
