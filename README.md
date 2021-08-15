<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Thanks again! Now go create something AMAZING! :D
***
***
***
*** To avoid retyping too much info. Do a search and replace for the following:
*** github_username, repo_name, twitter_handle, email, project_title, project_description
-->



<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]



<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/github_username/repo_name">
    <img src="images/POSTGRESS.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">Data Modeling with Postgres</h3>

  <p align="center">
    project_description
    <br />
    <a href="https://github.com/github_username/repo_name"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/github_username/repo_name">View Demo</a>
    ·
    <a href="https://github.com/github_username/repo_name/issues">Report Bug</a>
    ·
    <a href="https://github.com/github_username/repo_name/issues">Request Feature</a>
  </p>
</p>



<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary><h2 style="display: inline-block">Table of Contents</h2></summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Metadata</a></li>
      </ul>
      <ul>
        <li><a href="#built-with">Metadata</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
         <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgements">Acknowledgements</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

In this project, I am creating a database schema using a Postgre Relational database. The project tasks need to define fact and dimension tables for a star schema for a particular analytic focus and answer the business questions using PostgreSQL.

![](images/screenshot.jpg)




####  List of Tables 

 |     Name         |     Type      |  Small | Medium |   Big  | Description  |
 |----------------- |---------------|--------|--------|--------|--------------|
 | aircrafts        | table         |  16 kB |  16 kB |  16 kB | Aircraft     |
 | airports         | table         |  48 kB |  48 kB |  48 kB | Airports     |
 | boarding_passes  | table         |  31 MB | 102 MB | 427 MB | Boarding passes|
 | bookings         | table         |  13 MB |  30 MB | 105 MB | Bookings       |
 | flights          | table         |   3 MB |   6 MB |  19 MB | Flights        |
 | flights_v        | view          |   0 kb |   0 kB |   0 kB | Flights        |
 | routes           | mat. view     | 136 kB | 136 kB | 136 kB | Routes         |
 | seats            | table         |  88 kB |  88 kB |  88 kB | Seats          |
 | ticket_flights   | table         |  64 MB | 145 MB | 516 MB | Flight segments|
 | tickets          | table         |  47 MB | 107 MB | 381 MB | Tickets        |


### Metadata
##### Table bookings.aircrafts_data

| Column     |  Type   | Modifiers    |             Description |
|------------|---------|--------------|-------------------------- |
|aircraft_code | char(3) | NOT NULL     | Aircraft code, IATA|
|model         | text    | NOT NULL     | Aircraft model|
|range         | integer | NOT NULL     | Maximal flying distance, km|

##### Table bookings.airports
|  Column     |  Type   | Modifiers    |           Description|
| ------------| --------|--------------|-----------------------------|
|airport_code | char(3) | NOT NULL     | Airport code |
|airport_name | text    | NOT NULL     | Airport name |
|city         | text    | NOT NULL     | City |
|longitude    | float   | NOT NULL     | Airport coordinates: longitude |
|latitude     | float   | NOT NULL     | Airport coordinates: latitude |
|timezone     | text    | NOT NULL     | Airport time zone |

`The coordinates of the longitude and latitude have been transformed to point data type in the table. Here is the function to convert the longitude and latitude to point. `

```sh
--Return point with unknown SRID
SELECT ST_MakePoint(-71.1043443253471, 42.3150676015829);

--Return point marked as WGS 84 long lat
SELECT ST_SetSRID(ST_MakePoint(-71.1043443253471, 42.3150676015829),4326);

result
-------
1.5

For geodetic coordinates, X is longitude and Y is latitude

```
<!-- GETTING STARTED -->
## Getting Started

To get a local copy up and running follow these simple steps.

### Prerequisites

This is an example of how to list things you need to use the software and how to install them.
* npm
  ```sh
  npm install npm@latest -g
  ```

### Installation

1. Install Postgres from here 
    https://www.postgresql.org/download/

2. Clone the repo
   ```sh
   git clone https://github.com/saboye/Data-Modeling-with-Postgres.git
   ```
  
3. Importing the database using `psql` 
   ```sh
   psql -h localhost -d DATABASE -U postgres -f {FILE PATH}booking.sql
   ```

<!-- USAGE EXAMPLES -->
## Usage

Use this space to show useful examples of how a project can be used. Additional screenshots, code examples and demos work well in this space. You may also link to more resources.

_For more examples, please refer to the [Documentation](https://example.com)_



<!-- ROADMAP -->
## Roadmap

See the [open issues](https://github.com/github_username/repo_name/issues) for a list of proposed features (and known issues).



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.



<!-- CONTACT -->
## Contact

Your Name - [@twitter_handle](https://twitter.com/twitter_handle) - email

Project Link: [https://github.com/github_username/repo_name](https://github.com/github_username/repo_name)



<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements

* []()
* []()
* []()





<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/github_username/repo.svg?style=for-the-badge
[contributors-url]: https://github.com/github_username/repo_name/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/github_username/repo.svg?style=for-the-badge
[forks-url]: https://github.com/github_username/repo_name/network/members
[stars-shield]: https://img.shields.io/github/stars/github_username/repo.svg?style=for-the-badge
[stars-url]: https://github.com/github_username/repo_name/stargazers
[issues-shield]: https://img.shields.io/github/issues/github_username/repo.svg?style=for-the-badge
[issues-url]: https://github.com/github_username/repo_name/issues
[license-shield]: https://img.shields.io/github/license/github_username/repo.svg?style=for-the-badge
[license-url]: https://github.com/github_username/repo_name/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/github_username
