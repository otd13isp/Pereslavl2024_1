# Presentation of sensitive data in aggregated form using SVG vector format, R and Rust languages
## Free Software (free software)

The application is free software.

## Functions
- Creation of an API interface for the R language on the Internet
- Generate graphical information from R in SVG format
- Presentation of graphical information in the browser

 
## Requirements:
- [R](https://www.r-project.org) - for statistical research
- [Rust](https://www.rust-lang.org) - to create applications 
- [Actix Web](https://actix.rs) -  Web framework for Rust
- [JavaScript](https://www.ecma-international.org/publications-and-standards/standards/ecma-262) - for website frontend and backend
- [Node.js](https://nodejs.org) - for npm usage
- [npm](https://www.npmjs.com) - Node.js package manager
 
 The application is also open source with code on Github

## Installation
Installation on Linux (Fedora) is performed with administrator rights.
Run the commands to install openssl:

\# dnf install openssl

\# dnf install pkg-config perl-FindBin openssl-devel

To run the project you need to install Rust.
Installing Rust:
\# dnf install rust cargo

To install dependencies correctly, you need to edit the Cargo.toml file:
[dependencies]
actix-web = "4"
serde = { version = "1.0", features = ["derive"] }
openssl-sys = "0.9.92"
openssl = "0.10.57"
request = "0.9.24"
base64 = "0.21.3"

The text of the Rust program is contained in the file **src/main.rs**.

Create a subdirectory **public** in the project directory. Create a subdirectory **html** in it.
The file **plot.html** (server start page) is located in the **public/html** subdirectory and is intended for visualization.

Installing R under Fedora is standard:
\# dnf install R
Installing the RStudio graphical development environment:
\# dnf install rstudio-desktop
\# dnf install rstudio-server

Installing the necessary packages in RStudio
\> install.packages("plumber")
\> install.packages("ggplot2")
\> install.packages("png")

Uploadoading the **plot.R** file
Enter the command in RStudio console:
\> r <- plumb("/home/… /plot.R")
If the command throws an error an error, try to upload plumber manually
\> library(plumber)
If this does not help, then install the packages in Fedora
\#dnf install libcurl-devel
\# dnf install libsodium
\# dnf install libsodium-devel
and try again
\> r <- plumb("/home/… /plot.R")
The file **plot.R** will be uploaded
Start the R server using port 8000.
\> r$run(port=8000)

Install Node.js by running the command
\#dnf install nodejs
Install the npm package manager if the previous command did not install it
\# dnf install npm
Install the pm2 process manager:
\# npm install pm2 -g

## Usage
R is started from the **R** subdirectory using the **R/start.sh** file with the command
\$ ./start.sh
Rust is started from the project directory using the command
\$ cargo run
Open your browser. Enter the address: localhost:8080. Click the "Start" button.
The screen will present the data obtained from R.


## License
MIT
