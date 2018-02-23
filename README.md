# Form log [![Build Status](https://travis-ci.org/pagemachine/typo3-formlog.svg)](https://travis-ci.org/pagemachine/typo3-formlog) [![Latest Stable Version](https://poser.pugx.org/pagemachine/typo3-formlog/v/stable)](https://packagist.org/packages/pagemachine/typo3-formlog) [![Total Downloads](https://poser.pugx.org/pagemachine/typo3-formlog/downloads)](https://packagist.org/packages/pagemachine/typo3-formlog) [![Latest Unstable Version](https://poser.pugx.org/pagemachine/typo3-formlog/v/unstable)](https://packagist.org/packages/pagemachine/typo3-formlog) [![License](https://poser.pugx.org/pagemachine/typo3-formlog/license)](https://packagist.org/packages/pagemachine/typo3-formlog)

Form log for TYPO3

## Installation

This extension is installable from various sources:

1. Via [Composer](https://packagist.org/packages/pagemachine/typo3-formlog):

        composer require pagemachine/typo3-formlog

2. From the [TYPO3 Extension Repository](https://extensions.typo3.org/extension/formlog/)

## Start logging

Logging can be enabled for any form by adding the `LogFormData` finisher to its form definition:

```
finishers:
  - ...

  - identifier: LogFormData

  - identifier: Redirect
```

The `LogFormData` finisher should be the last finisher or right before the `Redirect` finisher if used. Logging after a redirect is not possible.

Additional variables stored in the `FinisherVariableProvider` can also be logged by using the `finisherVariables` option:

```
  - identifier: LogFormData
    options:
      finisherVariables:
        MyCustomFinisher:
          - myCustomVariable
```

The keys within `finisherVariables` are identifiers of finishers used in a form, the value of each entry is a list of finisher variable names.
