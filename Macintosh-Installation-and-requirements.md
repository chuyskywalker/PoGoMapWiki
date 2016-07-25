In order to run the project, you will need Python, pip and the project dependencies.
Version 2.7 is what we usually test against. You can use 3.x but no support will be given. 

### PokemonGo-Map: Macintosh Installation

---

#### Prerequisites for this guide
- [ ] Mac OSX 10.9+
- [ ] [Homebrew for Mac](http://brew.sh/)

---

### Step 1: Install Homebrew
Open up Terminal
1. Click on the rocket ship 
2. In the search, type in `Terminal`
3. Type `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
`

### Step 2: Install Requirements

1. `brew install git python python protobuf`

### Step 3: Clone PokemonGo-Map

For this guide we'll be using the Documents folder.

While still in the Terminal
1. Navigate to the user home folder. `cd ~/Documents`
2. Clone the repository. `git clone https://github.com/AHAAAAAAA/PokemonGo-Map.git`

Now we have all PokemonGo-Map files inside our Documents folder. Git clone automatically creates a folder called PokemonGo-Map

### Step 4: Get your own Google Maps API Key

Go to [this page](https://console.developers.google.com/flows/enableapi?apiid=maps_backend,geocoding_backend,directions_backend,distance_matrix_backend,elevation_backend,places_backend&keyType=CLIENT_SIDE&reusekey=true) to get your own Google Maps API Key. If you do not get your own API Key, you'll very likely run into an error telling you that you reached the daily request limit.

If you got your own API Key, open the *credentials.json* file inside the *PokemonGo-Map* folder. You can edit that file with Mac's built in text editor. Now replace the API Key in line 6 with the one you got from that Google website.

![API Key](http://i.imgur.com/IjD509D.png)

### Step 6: Setup PokemonGo-Map

While still in the Terminal:
1. Navigate into PokemonGo-Map folder. `cd ~/Documents/PokemonGo-Map`
2. Install specific python requirements `pip install --upgrade -r requirements.txt`

### Step 7: Start PokemonGo-Map

Now we are ready to start the map.

A full list of parameters you can use with the map and what they mean can be found [here](https://github.com/AHAAAAAAA/PokemonGo-Map#usage). This guide will only cover the important ones:

-a: Use either `ptc` or `google` for the login  
-u: Your Username  
-p: Your Password  
-l: The location you want to scan for Pokémon. You can try something like `La tour Eiffel, Paris`, your street or exact coordinates in this format: `47.6062100 -122.3320700`  
-st: The amount of steps to take (5 steps is approximately a 1.2km radius according to [this list](https://github.com/AHAAAAAAA/PokemonGo-Map#usage))  
-ar: Auto refresh interval (in seconds), so you don't have to refresh the map all the time  

> **Note**: It's recommended that you create a dummy account to use this Map with in order to prevent your real account from getting (soft)banned.

The final command should look like this:

`python example.py -a ptc -u johndoe -p ilovemama -l "400 Broad St, Seattle, WA 98109, USA" -st 5 -ar 10`

![Final command](https://i.imgur.com/axKgvEI.png)

Hit enter and view your map in all it's glory at http://127.0.0.1:5000/. Done!

![Map](http://i.imgur.com/EBkRhvZ.png)

---

### Bonus: How to update PokemonGo-Map
Since PokemonGo-Map is under active development and gets a lot of updates, you probably want to get all the latest features and bug fixes. You can see the latest updates (called commits) [here](https://github.com/AHAAAAAAA/PokemonGo-Map/commits/master). To update your copy, *Git Bash here* from the PokemonGo-Map folder, paste this command and hit enter:

`git pull origin master`

Now repeat Step 7 to restart your map.

## Credentials and Downloading

Create a Pokemon Club account [on their official website] to be used by the program to search for Pokemon. This generally shouldn't be the same as your main Trainer account you personally use. As of 7/21/2016 this page is unavailable most of the time, refresh the page every 5-10 minutes and it should allow signups eventually.

Then, download one of the following branches below:

- [Download master](https://github.com/AHAAAAAAA/PokemonGo-Map/archive/master.zip) (Stable builds)
- [Download dev branch](https://github.com/AHAAAAAAA/PokemonGo-Map/archive/develop.zip) (Active development)

The dev branch will have latest features from the development team, however it may be unstable at some times.

Extract this zip file to any location.

## Install Dependencies

Now, open a Terminal/Command Line (`Win`+`R` and `cmd` on Windows) and `cd` to the folder you extracted the zip file to.

```
cd some/directory/
```

In Windows you can also right click within the folder and select "Open Command Window Here."

Then enter the following:

```
pip install -r requirements.txt
```

## Running

To start the server, run the following command:

```
python example.py -a ptc -u [USERNAME] -p [PASSWORD] -l "[LOCATION]" -st 10
```

Replaing [USERNAME] and [PASSWORD] with the Pokemon Club credentials you created previously, and [LOCATION] with any location, for example `Washington, D.C` or latitude and longitude coordinates, such as `38.9072 77.0369`.

Additionally, you can change the `10` after `-st` to any number. This number indicates the number of steps away from your location it should look, higher numbers being farther.

## Accessing

Open your browser to [`http://localhost:5000`](http://localhost:5000) and keep refreshing as it loads more Pokemon (auto refresh is not implemented yet).