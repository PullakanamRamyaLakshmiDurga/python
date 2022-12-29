# python
jobs:
  build:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        python-version: ['2.x', '3.x']
    name: Python ${{ matrix.python-version }} sample
    steps:
      - uses: actions/checkout@v2
      - name: Setup python
        uses: actions/setup-python@v2
        with:
          python-version: ${{ matrix.python-version }}
          architecture: x64
      - run: python my_script.py
