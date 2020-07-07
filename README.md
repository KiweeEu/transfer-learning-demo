# Transfer Learning using Keras and EfficientNet

## Running locally

**Requirements:** you must have Docker and Docker Compose installed.

To run the notebook:

1. clone the repo
2. run `docker-compose up -d` in the terminal from the repo's root directory
3. open the logs `docker-compose logs` and open the last link (starts with `http://127.0.0.1:8888/`)
4. the JupyterLab IDE should appear in your browser
5. open `work/TransferLearning.ipynb` in JupyterLab

### Common issues

**Invalid credentials.** If you cannot log in to JupyterLab despite using the right token (double-check in the docker logs, a new token gets generated each time the server restarts), there is a chance that you already have an instance of Jupyter running locally, to which the requests get sent. To check it, run `sudo lsof -PiTCP:8888 -sTCP:LISTEN` to check which services use port 8888. If you have any non-docker services listed, it might be the problem. Check them using `ps -p <PID>` and `kill <PID>` if needed. In my case, it was a VS Code Python extension running another Jupyter server that caused the issue.
