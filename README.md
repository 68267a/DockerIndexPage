# DockerIndexPage

Docker Index Page is a python script that attempts to do the following:

1. Connect to a docker instance
2. Discover containers and properties
    - Name
    - State: {Status, StartedAt} 
    - HostConfig: {Binds[]}
    - Mounts: [*{Source, destination,mode}]
    - Config: {ExposedPorts, Image, Volumes,}
    - Maybe more
3. This information is re-parsed and written to a json file 
4. From there we use mermaid-js/mermaid-cli to generate some visuals
5. The desired output is written to an index.html file with the mermaid images and links to the exposed ports.  
A directory of static files can also be used as input. 
6. Finally, the content is sent to an output directory that can be served via any html service such as nginx. 