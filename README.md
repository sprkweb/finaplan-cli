<p align="center">
    <img src="https://raw.githubusercontent.com/sprkweb/finaplan-cli/master/icon.svg" alt="Logo" width="150" height="150" />
</p>

<h1 align="center">FinaPlan CLI</h1>

Financial planning using modules.

Inspired by [Unix philosophy](https://en.wikipedia.org/wiki/Unix_philosophy):

- Each module does exactly one thing and does it well;
- Modules are composed together and work together in a way that is defined by user;
- Modules handle simple streams of numbers.

## Installation

    git clone https://github.com/sprkweb/finaplan-cli.git
    cd finaplan-cli
    make install

## Available modules

    Usage:
    finaplan [command]

    Available Commands:
    init        Initialize an empty plan
    add         Add a certain amount of money to your plan
    invest      Add some interest rate on top of your capital
    print       Print the given plan in a more human-friendly manner

## Usage

Let's say you want to make a financial plan for 3 years,
and you want to know how much money you will have in the end.

    $ finaplan init --intervals 36 --months | \ # plan for 3 years = 36 months
        finaplan add 1000 --each 1 | \          # save 1000$ each month
        finaplan invest 1.1 --interval 12 | \   # invest your savings at 10% per year = per 12 months
        finaplan print | tail
    Month 26 | 29994.149955678673
    Month 27 | 31233.32751947085
    Month 28 | 32482.386459173056
    Month 29 | 33741.405570264425
    Month 30 | 35010.46427655031
    Month 31 | 36289.64263517264
    Month 32 | 37579.02134166024
    Month 33 | 38878.68173501941
    Month 34 | 40188.70580286511
    Month 35 | 41509.17618659305

## Development

### Run tests

    make test

### Build

    make build
