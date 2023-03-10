# **MacroScraper**

<div align=right>
    <img src="./images/MacroLogo.png" alt="MacroScraper logo" width="150" height="150" align="right" />
</div>

## **Table of content**

* [**What is MacroScraper?**](#what-is-macroScraper)
* [**Where does it come from?**](#where-does-it-come-from)
* [**How does it work?**](#how-does-it-work)
  * [Saving data](#saving-data)
  * [Directory structure](#directory-structure)
* [**How to use it?**](#how-to--use-it)
  * [Usage](#usage)
* [**Installation**](#installation)
  * [Prerequisites](#prerequisites)
  * [Installation of MacroScraper](#installation-macro)
* [**How to contribute?**](#how-to-contribute)
* [**License**](#license)

---

<div id="what-is-macroScraper">

## **What is MacroScraper?**

MacroScraper is a web Scraper for [Bandcamp](https://bandcamp.com) music. It is a Python script that will download all the free music from a Bandcamp artist page, album after album, in your Music directory.

</div>

---

<div id="where-does-it-come-from">

## **Where does it come from?**

![Macroblank Bandcamp banner](./images/macro-banner.png)

MacroScraper is a project I made for my personal use. I wanted to download all the music from a Bandcamp artist page named [Macroblank](https://macroblank.bandcamp.com/). I didn't want to download the music one by one so I decided to make a script that would do it for me.
That is why the script is named MacroScraper.

<img src='./images/fonctionnement.png' width=100 align=right>

</div>

---

<div id="how-does-it-work">

## **How does it work?**

The script will use the [Selenium](https://www.selenium.dev/) library to open a Chrome browser. It will then navigate to the Bandcamp artist page and click on the "Download" button of each album. The script will then repeat the process for each album.

Each album will be downloaded in a separate folder. The folder will be named after the album name. The album will be downloaded in a ``.zip`` file then extracted in the folder with the same name as the album.

<img src='./images/bases-de-donnees.png' width=75 align=right style="margin:1vw;">
</div>
<div id="saving-data">

### Saving data

It will create a ``.csv`` file with the name of the artist and the name of the album. The file will contain the following information:

* Album name
* Album URL
* Album release date
* Album genre
* Album tracklist

It will also create a ``.txt`` file with the name of the artist and the name of the album. The file will contain the following information:

* Download date
* Album name
* Artist name
* Album tracklist

The project will download the music in yout Music folder. It will create a folder named MacroScraper and then create a folder named after the artist's name. The folder will contain all the albums downloaded as zip files, the ``.csv`` and ``.txt`` files.

> Why do I want to stock data?

I wanted to keep track of the music I downloaded. I also wanted to keep track of the albums I downloaded and the date I downloaded them so I could know if I already downloaded an album or not.

I like data processing so i'd like in the future to make a script that would read the ``.csv`` file and make graphs and statistics about the music I downloaded.

</div>
<div id="directory-structure">

### Directory structure

```shell
Music   
.
|___ MacroScraper
    |___ Artist1
        |___ Album1
        |___ Album2
        |___ ...
        |___ Zips
    |___ Artist2
        |___ Album1
        |___ Album2
        |___ ...
        |___ Zips
    |___ ...
```

</div>

---

<div id="how-to--use-it">

<img src='./images/probleme.png' width=100 align=right>

## **How to use it?**

This script will ask you to enter the artist name's album you want to download.
> It is planned to make a GUI for the script. For now, it is a command line script.

Just let it do the job. It will take a while depending on the number of albums the artist has.

</div>
<div id="usage">

### **Usage**

* Run the script with `python main.py`
* Enter the name of the artist in the terminal.
* Wait for the script to finish.
* Retrieve the music in your Music folder.

</div>

---

<div id="installation">
<img src="./images/docker-logo.png" align='right' width=120>

## **Installation**

<div id="prerequisites">

### **Prerequisites**

You'll need [Docker](https://docs.docker.com/get-docker/) to be installed. Go to theiur website to download Docker. Then verify Docker has been correctly installed by running the following command in your terminal:

```bash
docker --version
```

If you get an error, it means **Docker is not installed**. If you get a version of Docker, it means you are **ready** to continue.

Thanks to Docker, you won't need to install Python on your machine. You'll just have to follow the next steps.

</div>
<div id="installation-macro">

### **Installation of MacroScraper**

1. Download the project archive on the [GitHub repository](https://github.com/LOISGALLAUD/MacroScraper)
2. Unzip the archive
3. Open a terminal in the unzipped folder
4. Run the following commands:

    ```bash
    docker build -t macro .
    docker run -it macro
    ```

>What do these commands do?

* `docker build -t macro .` : Build the Docker image from the `Dockerfile` present in the current folder. The `-t` option allows to give a name to the Docker image. Here, we give the name `macro` to the image.
* `docker run -it macro` : Run a container from the `macro` image. The `-it` option allows to run the container in interactive mode. This allows to see the application logs in the terminal. This command executes the `main.py` file which launches the application.

For more information about Docker, you can consult the [official documentation](https://docs.docker.com/) of Docker.

</div>
</div>

---

<div id="how-to-contribute">

<img src='./images/resolution-de-probleme.png' width=75 align=right>

## **How to contribute?**

I develop the MacroScraper alone: you can check more of my stuff [here](https://github.com/LOISGALLAUD). I welcome both pull requests and issues on [GitHub](https://github.com/LOISGALLAUD/MacroScraper). I will review your pull request as soon as possible.

Thank you for your interest in MacroScraper!

</div>

---

<img src='./images/licence.png' width=75 align=right>

## **License**

MacroScraper is licensed under the [Apashe 2.0 License].
