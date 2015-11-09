# gvm-docker
Docker file for Google Managed VM for php, nginx and memcached. Works well for Laravel applications.

## Usage

Clone this repository.

To build the docker locally:

~~~~
docker build -t=ganey/gvm-docker .
~~~~

To run the docker and mount a dir into the docker VM:

~~~~
docker run --name=gvm -v /e/websites/website-name:/var/www -p 8080:8080 ganey/gvm-docker
~~~~

To auto include files, uncomment / edit the line:

~~~~
#ADD . /var/www
~~~~

To deploy to Google cloud, set your default project based on the current gcloud sdk docs (this are changing rapidly, please do this yourself)

~~~~
gcloud preview app deploy app.yaml
~~~~

The docker will then build remotely on a self terminationg compute instance, and then deploy as a Google MVM.

