# Tenhou Client
A simplified client for *Tenhou.net*(one of the most popular online mahjong services in Japan), including an AI which can easily defeat other players in *Ippan(Normal)* level games.

## How to run

### Windows

**Requirements:** Visual Studio 2015

1. Download source code.

		git clone https://github.com/zhangjk95/Tenhou-Client.git
		
2. Copy `Tenhou\App.config.example` to `Tenhou\App.config` and edit it. (Instructions are included in the example.)
3. Open the solution with Visual Studio 2015.
4. Switch the Build Configuration to **Release**. (The program may be slow in Debug mode and exceed the time limit when making dicisions.)
5. Build and Run!

#### Replays

After the game is ended, you can find the replay URLs in `Tenhou\bin\Debug\TenhouLog.txt`.

### Docker 

You can run this program in Docker on either Windows or Linux without any other requirements.

1. Download source code.

		git clone https://github.com/zhangjk95/Tenhou-Client.git
		
2. Change the working directory to the source code folder.

		cd Tenhou-Client

3. Copy `Tenhou/App.config.example` to `Tenhou/App.config` and edit it. (Instructions are included in the example.)

		cp Tenhou/App.config.example Tenhou/App.config
		vim Tenhou/App.config

4. Build Docker image.

		chmod +x build.sh
		./build.sh

5. Run.

		 docker run -it tenhou-client
		 
#### Replays

After the game is ended, you can find the replay URLs in `/usr/src/app/build/TenhouLog.txt`. You can map a file volume to it in order to save the replays outside the container.

For example:

	touch ~/TenhouLog.txt
	docker run -v ~/TenhouLog.txt:/usr/src/app/build/TenhouLog.txt -it tenhou-client