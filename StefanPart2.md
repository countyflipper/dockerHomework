# Part 2-1
*	PS C:\Users\sderosa\Homework1\dockerHomework> git clone -b v1 https://github.com/docker-training/node-bulletin-board
*	>> cd node-bulletin-board/bulletin-board-app
*	PS C:\Users\sderosa\Homework1\dockerHomework>
*	PS C:\Users\sderosa\Homework1\dockerHomework> cd C:\Users\sderosa\Homework1\node-bulletin-board\bulletin-board-app
*	PS C:\Users\sderosa\Homework1\node-bulletin-board\bulletin-board-app> docker image build -t bulletinboard:1.0 .
*	Sending build context to Docker daemon  46.08kB
*	Step 1/6 : FROM node:6.11.5
*	6.11.5: Pulling from library/node
*	85b1f47fba49: Pull complete
*	ba6bd283713a: Pull complete
*	817c8cd48a09: Pull complete
*	47cc0ed96dc3: Pull complete
*	8888adcbd08b: Pull complete
*	6f2de60646b9: Pull complete
*	1666693bf996: Pull complete
*	2fe410df7942: Pull complete
*	Digest: sha256:fe109b92edafd9821fbc1c80fd7587a1b4e1ff76fec3af675869e23e50bbf45b
*	Status: Downloaded newer image for node:6.11.5
*	 ---> 852391892b9f
*	Step 2/6 : WORKDIR /usr/src/app
*	 ---> Running in 6a1c0a9448b7
*	Removing intermediate container 6a1c0a9448b7
*	 ---> 1f77c1d06dad
*	Step 3/6 : COPY package.json .
*	 ---> c3ae126e40ca
*	Step 4/6 : RUN npm install
*	 ---> Running in 1c7cdc4952ac
	
*	> ejs@2.7.4 postinstall /usr/src/app/node_modules/ejs
*	> node ./postinstall.js
	
*	vue-event-bulletin@1.0.0 /usr/src/app
*	+-- body-parser@1.19.0
*	| +-- bytes@3.1.0
*	| +-- content-type@1.0.4
*	| +-- debug@2.6.9
*	| | `-- ms@2.0.0
*	| +-- depd@1.1.2
*	| +-- http-errors@1.7.2
*	| | +-- inherits@2.0.3
*	| | `-- toidentifier@1.0.0
*	| +-- iconv-lite@0.4.24
*	| | `-- safer-buffer@2.1.2
*	| +-- on-finished@2.3.0
*	| | `-- ee-first@1.1.1
*	| +-- qs@6.7.0
*	| +-- raw-body@2.4.0
*	| | `-- unpipe@1.0.0
*	| `-- type-is@1.6.18
*	|   +-- media-typer@0.3.0
*	|   `-- mime-types@2.1.26
*	|     `-- mime-db@1.43.0
*	+-- bootstrap@3.4.1
*	+-- ejs@2.7.4
*	+-- errorhandler@1.5.1
*	| +-- accepts@1.3.7
*	| | `-- negotiator@0.6.2
*	| `-- escape-html@1.0.3
*	+-- express@4.17.1
*	| +-- array-flatten@1.1.1
*	| +-- content-disposition@0.5.3
*	| +-- cookie@0.4.0
*	| +-- cookie-signature@1.0.6
*	| +-- encodeurl@1.0.2
*	| +-- etag@1.8.1
*	| +-- finalhandler@1.1.2
*	| +-- fresh@0.5.2
*	| +-- merge-descriptors@1.0.1
*	| +-- methods@1.1.2
*	| +-- parseurl@1.3.3
*	| +-- path-to-regexp@0.1.7
*	| +-- proxy-addr@2.0.5
*	| | +-- forwarded@0.1.2
*	| | `-- ipaddr.js@1.9.0
*	| +-- range-parser@1.2.1
*	| +-- safe-buffer@5.1.2
*	| +-- send@0.17.1
*	| | +-- destroy@1.0.4
*	| | +-- mime@1.6.0
*	| | `-- ms@2.1.1
*	| +-- serve-static@1.14.1
*	| +-- setprototypeof@1.1.1
*	| +-- statuses@1.5.0
*	| +-- utils-merge@1.0.1
*	| `-- vary@1.1.2
*	+-- method-override@2.3.10
*	+-- morgan@1.9.1
*	| +-- basic-auth@2.0.1
*	| `-- on-headers@1.0.2
*	+-- vue@1.0.28
*	| `-- envify@3.4.1
*	|   +-- jstransform@11.0.3
*	|   | +-- base62@1.2.8
*	|   | +-- commoner@0.10.8
*	|   | | +-- commander@2.20.3
*	|   | | +-- detective@4.7.1
*	|   | | | +-- acorn@5.7.3
*	|   | | | `-- defined@1.0.0
*	|   | | +-- glob@5.0.15
*	|   | | | +-- inflight@1.0.6
*	|   | | | | `-- wrappy@1.0.2
*	|   | | | +-- minimatch@3.0.4
*	|   | | | | `-- brace-expansion@1.1.11
*	|   | | | |   +-- balanced-match@1.0.0
*	|   | | | |   `-- concat-map@0.0.1
*	|   | | | +-- once@1.4.0
*	|   | | | `-- path-is-absolute@1.0.1
*	|   | | +-- graceful-fs@4.2.3
*	|   | | +-- mkdirp@0.5.1
*	|   | | | `-- minimist@0.0.8
*	|   | | +-- private@0.1.8
*	|   | | +-- q@1.5.1
*	|   | | `-- recast@0.11.23
*	|   | |   +-- ast-types@0.9.6
*	|   | |   +-- esprima@3.1.3
*	|   | |   `-- source-map@0.5.7
*	|   | +-- esprima-fb@15001.1.0-dev-harmony-fb
*	|   | +-- object-assign@2.1.1
*	|   | `-- source-map@0.4.4
*	|   |   `-- amdefine@1.0.1
*	|   `-- through@2.3.8
*	`-- vue-resource@0.1.17
	
*	npm WARN vue-event-bulletin@1.0.0 No repository field.
*	Removing intermediate container 1c7cdc4952ac
*	 ---> ad169dcb47d2
*	Step 5/6 : COPY . .
*	 ---> 5cced8082224
*	Step 6/6 : CMD [ "npm", "start" ]
*	 ---> Running in e11d7fd1ad20
*	Removing intermediate container e11d7fd1ad20
*	 ---> 46add4862b22
*	Successfully built 46add4862b22
*	Successfully tagged bulletinboard:1.0
*	SECURITY WARNING: You are building a Docker image from Windows against a non-Windows Docker host. All files and directories added to build context will have '-rwxr-xr-x' permissions. It is recommended to double check and reset permissions for sensitive files and directories.
*	PS C:\Users\sderosa\Homework1\node-bulletin-board\bulletin-board-app> docker container run --publish 8000:8080 --detach
*	--name bb bulletinboard:1.0
*	8327f8c4860b943a7e2ef20e3cbab9dd9abb339472a0765c66489c8b56244d36
*	PS C:\Users\sderosa\Homework1\node-bulletin-board\bulletin-board-app> docker container rm --force bb
*	bb
*	PS C:\Users\sderosa\Homework1\node-bulletin-board\bulletin-board-app>