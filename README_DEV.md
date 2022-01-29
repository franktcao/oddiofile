`poetry` has trouble with installing torch so it's used to manage all other packages.

To get `torch` working, this silly workflow to was used to generate the 
`requirements.txt` with `poetry`:

1. Add all `poetry` packages *except* `torch` packages
1. Set up virtual environment
   1. Generate virtual environemnt directory:
      ```
       python -m venv .venv
      ```
   1. Activate virtual environment
      ```
      . .venv/bin/activate
      ```
1. Install `poetry` packages
   ```
   poetry install
   ```
1. `pip` install `torch`
   ```
   pip install torch torchaudio
   ```
1. Generate the `requirements.txt`
   ```
   pip freeze > requirements.txt
   ```

Now that there's the `requirements.txt`, the environment can be set up with the usual

```
pip install --upgrade pip
pip install -r requirements.txt
```

as is done in `install_venv.sh`